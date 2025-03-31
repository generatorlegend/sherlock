# Using Proxies and Tor with Sherlock

Sherlock provides options to use proxies and Tor for making requests. This guide explains how to use these features, their use cases, and important considerations.

## Using Proxies

Sherlock allows you to route your requests through a proxy server using the `--proxy` option. This can be useful for various reasons, such as:

- Bypassing geographical restrictions
- Hiding your real IP address
- Load balancing requests across multiple IP addresses

To use a proxy with Sherlock, use the following command-line option:

```
python3 sherlock.py --proxy PROXY_URL username
```

Replace `PROXY_URL` with the URL of your proxy server. For example:

```
python3 sherlock.py --proxy socks5://127.0.0.1:9150 johndoe
```

### Proxy URL Format

The proxy URL should be in the following format:

```
protocol://ip_address:port
```

Supported protocols include:
- HTTP
- HTTPS
- SOCKS4
- SOCKS5

### Considerations

- Ensure that the proxy server is reliable and secure.
- Using a proxy may slow down the requests, increasing the overall runtime of Sherlock.
- Some websites may block or behave differently when accessed through a proxy.

## Using Tor

Sherlock offers two options for routing requests through the Tor network:

1. `--tor`: Use Tor for all requests
2. `--unique-tor`: Use a new Tor circuit for each request

### Using Tor for All Requests

To route all requests through Tor, use the following command:

```
python3 sherlock.py --tor username
```

This option will use the same Tor circuit for all requests.

### Using a New Tor Circuit for Each Request

To use a new Tor circuit for each request, use the following command:

```
python3 sherlock.py --unique-tor username
```

This option provides increased anonymity but significantly increases the runtime.

### Considerations for Tor Usage

- Tor must be installed and running on your system.
- The Tor executable must be in your system path.
- Using Tor will significantly increase the runtime of Sherlock.
- Some websites may refuse connections coming from Tor exit nodes, potentially increasing connection errors.

## Important Notes

1. You cannot use both `--proxy` and `--tor` (or `--unique-tor`) at the same time. If you attempt to do so, Sherlock will raise an exception.

2. As of the current version, the `--tor` and `--unique-tor` options are deprecated and may be removed in a future release. Users will see a warning message when using these options.

3. To use Tor functionality, you need to install the `torrequest` package. If you've installed Sherlock via pip, you can include this optional dependency by running:

   ```
   pip install 'sherlock-project[tor]'
   ```

   Alternatively, you can install it separately:

   ```
   pip install torrequest
   ```

4. When using Tor, be aware of the legal and ethical considerations in your jurisdiction.

By using these options, you can enhance your privacy and bypass certain restrictions while using Sherlock. However, always be mindful of the increased runtime and potential for connection errors when using proxies or Tor.
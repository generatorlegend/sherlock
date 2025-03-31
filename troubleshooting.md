# Troubleshooting Guide

This guide aims to help you resolve common issues you might encounter while using Sherlock. If you're experiencing problems, please check the following sections for possible solutions.

## Network-Related Issues

### Proxy Errors

If you're encountering proxy-related errors:

1. Ensure your proxy URL is correctly formatted. For example: `socks5://127.0.0.1:1080`
2. Verify that your proxy server is running and accessible.
3. Try using the `--timeout` option to increase the request timeout if your proxy is slow.

Example:
```
python3 sherlock.py username --proxy socks5://127.0.0.1:1080 --timeout 120
```

### Tor Connection Issues

If you're having trouble with Tor:

1. Make sure Tor is installed and properly configured on your system.
2. Verify that the Tor service is running.
3. If using `--tor` or `--unique-tor` options, ensure you have the `torrequest` package installed:

```
pip install 'sherlock-project[tor]'
```

Note: The `--tor` and `--unique-tor` options are deprecated and may be removed in future releases.

## False Positives/Negatives

### False Positives

If Sherlock reports a username as existing when it doesn't:

1. Check if the site has implemented new anti-bot measures.
2. Verify the site's response manually by visiting the URL.
3. Consider updating the site's detection method in the `data.json` file.

### False Negatives

If Sherlock fails to detect an existing account:

1. Ensure you're using the latest version of Sherlock.
2. Check if the site has changed its URL structure or response patterns.
3. Verify if the site is correctly listed in the `data.json` file.

## Rate Limiting and Blocking

If you're being rate-limited or blocked by websites:

1. Reduce the number of concurrent requests by using a smaller subset of sites:
   ```
   python3 sherlock.py username --site site1 site2 site3
   ```
2. Use a proxy or Tor to distribute requests across different IP addresses.
3. Increase delays between requests (This feature is not built-in, you may need to modify the code).

## Reporting Bugs

If you encounter a bug that isn't covered in this guide:

1. Check the [existing issues](https://github.com/sherlock-project/sherlock/issues) on GitHub to see if it has already been reported.
2. If not, create a new issue with the following information:
   - Sherlock version (`python3 sherlock.py --version`)
   - Python version
   - Operating system
   - Full command used to run Sherlock
   - Complete error message or description of the unexpected behavior
   - Steps to reproduce the issue

## Contributing to the Project

If you'd like to contribute to Sherlock:

1. Fork the [Sherlock repository](https://github.com/sherlock-project/sherlock) on GitHub.
2. Create a new branch for your feature or bug fix.
3. Make your changes, ensuring you follow the project's coding style.
4. Write tests for your changes if applicable.
5. Submit a pull request with a clear description of your changes.

For more detailed information on contributing, please read the [CONTRIBUTING.md](https://github.com/sherlock-project/sherlock/blob/master/CONTRIBUTING.md) file in the Sherlock repository.

## Additional Resources

- [Sherlock Documentation](https://github.com/sherlock-project/sherlock/wiki)
- [Sherlock Discussions](https://github.com/sherlock-project/sherlock/discussions)
- [Sherlock Project Website](https://sherlock-project.github.io/)

If you're still experiencing issues after consulting this troubleshooting guide, feel free to ask for help in the GitHub Discussions section of the Sherlock project.
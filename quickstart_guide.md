# Quickstart Guide

This guide will help you get started with Sherlock quickly, covering installation, basic usage, and key command-line arguments.

## Installation

1. Ensure you have Python 3.9 or higher installed on your system.

2. Install Sherlock using pip:

```bash
pip install sherlock-project
```

For the latest development version, you can install directly from GitHub:

```bash
pip install git+https://github.com/sherlock-project/sherlock.git
```

## Basic Usage

To search for a username across supported social networks:

```bash
sherlock username
```

Replace `username` with the actual username you want to search for.

## Key Command-Line Arguments

Sherlock supports various command-line arguments to customize its behavior:

- `--verbose` or `-v`: Display extra debugging information and metrics.
- `--folderoutput` or `-fo`: Specify a folder to save results when searching multiple usernames.
- `--output` or `-o`: Specify a file to save results when searching a single username.
- `--csv`: Create a CSV file with the results.
- `--site SITE_NAME`: Limit the search to specific sites. Can be used multiple times.
- `--proxy PROXY_URL`: Make requests through a proxy (e.g., `socks5://127.0.0.1:1080`).
- `--timeout TIMEOUT`: Set the timeout for requests in seconds (default is 60).
- `--print-found`: Only print found accounts (default behavior).
- `--print-all`: Print both found and not found accounts.
- `--no-color`: Disable colored terminal output.
- `--browse` or `-b`: Open found profile URLs in the default browser.

## Examples

1. Search for a single username:

```bash
sherlock johndoe
```

2. Search for multiple usernames:

```bash
sherlock johndoe janedoe
```

3. Search on specific sites only:

```bash
sherlock johndoe --site twitter --site instagram
```

4. Save results to a CSV file:

```bash
sherlock johndoe --csv
```

5. Use a proxy and set a custom timeout:

```bash
sherlock johndoe --proxy socks5://127.0.0.1:9050 --timeout 30
```

## Next Steps

- Check out the full documentation for more advanced features and options.
- Join our community on GitHub to report issues, suggest improvements, or contribute to the project.
- Stay updated with the latest releases and changes by following the project on GitHub.

Happy hunting!
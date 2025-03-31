# Site Coverage in Sherlock

Sherlock is designed to search for usernames across various social networks and online platforms. This guide explains how to view the list of supported sites, limit searches to specific sites, and request the addition of new sites to the database.

## Viewing Supported Sites

Sherlock maintains a comprehensive list of supported sites in the `data.json` file. This file contains information about each site, including the URL format, error handling, and other relevant details.

To view the list of supported sites:

1. Navigate to the `sherlock_project/resources/` directory.
2. Open the `data.json` file.

Alternatively, you can view the most up-to-date list of supported sites on the [Sherlock GitHub repository](https://github.com/sherlock-project/sherlock/blob/master/sherlock_project/resources/data.json).

## Limiting Searches to Specific Sites

Sherlock allows you to limit your search to specific sites using the `--site` option. This is useful when you want to focus your search on particular platforms.

To limit your search:

```bash
python3 sherlock.py --site twitter --site instagram username
```

You can specify multiple sites by repeating the `--site` option.

## Requesting New Site Additions

If you'd like to request the addition of a new site to Sherlock's database, follow these steps:

1. Check the existing `data.json` file to ensure the site isn't already included.
2. If the site is not present, you can request its addition by opening an issue on the [Sherlock GitHub repository](https://github.com/sherlock-project/sherlock/issues).
3. Provide the following information in your request:
   - Site name
   - Site URL
   - Username format for the site
   - Any additional relevant details (e.g., error handling specifics)

Please note that the Sherlock maintainers review each request and decide on additions based on various factors, including the site's popularity and ease of integration.

## Contributing New Sites

If you're familiar with Python and want to contribute a new site to Sherlock's database, you can submit a pull request:

1. Fork the Sherlock repository.
2. Add the new site information to the `data.json` file.
3. Test the new site integration thoroughly.
4. Submit a pull request with your changes.

For detailed contribution guidelines, please refer to the [CONTRIBUTING.md](https://github.com/sherlock-project/sherlock/blob/master/CONTRIBUTING.md) file in the Sherlock repository.

## Updating Site Information

The internet landscape is constantly changing, and sometimes site information in Sherlock's database may become outdated. If you notice any discrepancies or changes in how a site handles username checks, you can help by:

1. Opening an issue on the GitHub repository to report the change.
2. Submitting a pull request with the updated site information in the `data.json` file.

By keeping the site database up-to-date, you help ensure Sherlock remains an effective tool for username searches across various platforms.
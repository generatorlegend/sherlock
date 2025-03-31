# Output Formats

Sherlock provides multiple output formats to present the results of username searches across various social networks and websites. This document explains the different output formats available and how to use them.

## Available Output Formats

Sherlock supports the following output formats:

1. Text (.txt)
2. Comma-Separated Values (CSV)
3. Excel Spreadsheet (XLSX)

## Text Output (Default)

By default, Sherlock generates a text file for each username searched. This file contains a list of URLs where the username was found, along with a summary of the total number of websites where the username was detected.

### Usage

To generate a text output file, simply run Sherlock without any output-specific flags:

```
python3 sherlock.py username
```

This will create a file named `username.txt` in the current directory.

### Example Output

```
https://example1.com/username
https://example2.com/username
https://example3.com/username
Total Websites Username Detected On : 3
```

## CSV Output

Sherlock can generate a CSV (Comma-Separated Values) file containing detailed information about the search results.

### Usage

To generate a CSV output file, use the `--csv` flag:

```
python3 sherlock.py --csv username
```

This will create a file named `username.csv` in the current directory.

### Example Output

```csv
username,name,url_main,url_user,exists,http_status,response_time_s
username,Example1,https://example1.com,https://example1.com/username,Claimed,200,0.5
username,Example2,https://example2.com,https://example2.com/username,Claimed,200,0.7
username,Example3,https://example3.com,https://example3.com/username,Claimed,200,0.6
```

## Excel Spreadsheet (XLSX) Output

Sherlock can also generate an Excel spreadsheet (XLSX) file with the search results.

### Usage

To generate an XLSX output file, use the `--xlsx` flag:

```
python3 sherlock.py --xlsx username
```

This will create a file named `username.xlsx` in the current directory.

### Example Output

The XLSX file will contain a sheet with the following columns:

- username
- name (website name)
- url_main (main website URL)
- url_user (user profile URL)
- exists (account status)
- http_status (HTTP response status code)
- response_time_s (response time in seconds)

## Additional Options

### Folder Output

If you want to save the output files in a specific folder, use the `--folderoutput` or `-fo` option:

```
python3 sherlock.py --folderoutput /path/to/folder username
```

This will save the output files in the specified folder.

### Multiple Usernames

When searching for multiple usernames, Sherlock will create separate output files for each username:

```
python3 sherlock.py --csv username1 username2 username3
```

This will generate `username1.csv`, `username2.csv`, and `username3.csv` files.

### Printing Options

- Use `--print-found` (default) to display only the sites where the username was found.
- Use `--print-all` to display results for all sites, including those where the username was not found.

## Conclusion

Sherlock's multiple output formats provide flexibility in how you can view and analyze the results of your username searches. Choose the format that best suits your needs and workflow, whether it's a simple text file, a structured CSV for data analysis, or an Excel spreadsheet for visual representation and further manipulation.
# Command Line Options

Sherlock provides a wide range of command-line options to customize its behavior and output. This page lists all available options, organized by functionality.

## General Options

### --version
Display version information and dependencies.

Example:
```
python3 sherlock.py --version
```

### --verbose, -v, -d, --debug
Display extra debugging information and metrics.

Example:
```
python3 sherlock.py --verbose username
```

## Output Options

### --folderoutput, -fo FOLDER
If using multiple usernames, save the results to the specified folder.

Example:
```
python3 sherlock.py -fo results_folder username1 username2
```

### --output, -o FILE
If using a single username, save the result to the specified file.

Example:
```
python3 sherlock.py -o result.txt username
```

### --csv
Create a Comma-Separated Values (CSV) file with the results.

Example:
```
python3 sherlock.py --csv username
```

### --xlsx
Create a Microsoft Excel spreadsheet (XLSX) file with the results.

Example:
```
python3 sherlock.py --xlsx username
```

### --print-all
Output sites where the username was not found.

Example:
```
python3 sherlock.py --print-all username
```

### --print-found
Output sites where the username was found (default behavior).

Example:
```
python3 sherlock.py --print-found username
```

### --no-color
Don't color terminal output.

Example:
```
python3 sherlock.py --no-color username
```

### --browse, -b
Open all results on the default browser.

Example:
```
python3 sherlock.py --browse username
```

### --no-txt
Disable creation of a txt file with the results.

Example:
```
python3 sherlock.py --no-txt username
```

## Network Options

### --tor, -t
Make requests over Tor; increases runtime; requires Tor to be installed and in system path.

Example:
```
python3 sherlock.py --tor username
```

### --unique-tor, -u
Make requests over Tor with a new Tor circuit after each request; increases runtime; requires Tor to be installed and in system path.

Example:
```
python3 sherlock.py --unique-tor username
```

### --proxy, -p PROXY_URL
Make requests over a proxy. e.g., socks5://127.0.0.1:1080

Example:
```
python3 sherlock.py --proxy socks5://127.0.0.1:1080 username
```

### --timeout TIMEOUT
Time (in seconds) to wait for response to requests (Default: 60)

Example:
```
python3 sherlock.py --timeout 30 username
```

## Site Selection Options

### --site SITE_NAME
Limit analysis to just the listed sites. Add multiple options to specify more than one site.

Example:
```
python3 sherlock.py --site twitter --site facebook username
```

### --nsfw
Include checking of NSFW sites from the default list.

Example:
```
python3 sherlock.py --nsfw username
```

## Data Source Options

### --local, -l
Force the use of the local data.json file.

Example:
```
python3 sherlock.py --local username
```

### --json, -j JSON_FILE
Load data from a JSON file or an online, valid, JSON file. Upstream PR numbers also accepted.

Example:
```
python3 sherlock.py --json custom_data.json username
```

## Debugging Options

### --dump-response
Dump the HTTP response to stdout for targeted debugging.

Example:
```
python3 sherlock.py --dump-response username
```

## Usage Examples

1. Basic usage:
```
python3 sherlock.py username
```

2. Check multiple usernames and save results to a folder:
```
python3 sherlock.py -fo results_folder username1 username2 username3
```

3. Use Tor and create a CSV file:
```
python3 sherlock.py --tor --csv username
```

4. Check only specific sites with a timeout of 30 seconds:
```
python3 sherlock.py --site twitter --site instagram --timeout 30 username
```

5. Use a proxy and open results in the browser:
```
python3 sherlock.py --proxy socks5://127.0.0.1:1080 --browse username
```

Remember that you can combine multiple options to customize Sherlock's behavior according to your needs.
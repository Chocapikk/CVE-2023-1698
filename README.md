# CVE-2023-1698 WAGO Remote Exploit Tool

## Description
This script is designed to exploit a severe Remote Code Execution (RCE) vulnerability present in multiple WAGO products. Unauthenticated attackers can leverage this flaw to create new users, alter device configurations, and potentially take over the entire system. This can lead to unintended behaviors, Denial of Service (DoS), and full system compromise.

## Vulnerability Significance
**Remote Code Execution (RCE)** is among the most dangerous vulnerabilities as it allows an attacker to execute arbitrary commands on the victim system. When combined with a lack of authentication requirement, this vulnerability becomes even more critical.

## Discovery with ZoomEye
Potential targets vulnerable to this exploit can be identified using the ZoomEye search engine with the following dork:

```
title:"Web-Based Management"
```

**Note**: It is imperative to obtain the necessary permissions before scanning or exploiting any targets identified using this method.

## Severity
**CVSS 3.x Severity and Metrics:**

- **Base Score**: 9.8 (CRITICAL)
- **Vector**: CVSS:3.1/AV:N/AC:L/PR:N/UI:N/S:U/C:H/I:H/A:H

## Features
- Check individual URLs for vulnerability.
- Scan a list of URLs for potential vulnerabilities.
- Execute arbitrary commands on vulnerable URLs.
- Save vulnerable URLs in an output file for further analysis.

## Dependencies
To set up the environment for the script, install the required dependencies using:
```
pip install -r requirements.txt
```

## Usage
Execute the script using the command:
```
python exploit.py [-u <base_url> | -l <list_of_base_urls>] [-t <threads>] [-o <output_file>]
```

### Arguments:
- `-u` or `--url`: Specify the base URL for the requests.
- `-l` or `--list`: Provide a file containing a list of base URLs to scan.
- `-t` or `--threads`: Set the number of threads to use (default is 100).
- `-o` or `--output`: Designate a file to save vulnerable URLs.

## Examples
To check a single URL for vulnerability, use:
```
python exploit.py -u http://example.com
```

To scan a list of URLs, utilize:
```
python exploit.py -l list.txt -o output.txt
```

## Disclaimer
This tool is meant solely for educational and ethical purposes. Ensure that you have appropriate authorization and permissions before scanning or exploiting any targets. Misuse can lead to legal consequences.

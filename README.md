# whoavail

A simple Bash script to check domain name availability using WHOIS.

## Description:

This script may help you to query multiple domains availability status using command line interface.

You can use shell redirection to capture the output into a tab seperated text file.

If you give the first parameter the filename of a text file containing a list of domainnames (one domain in a line) all the lines in this file will be processed as a domain name.

You may also use a command like "tee -a filename.csv" with pipe to see the output on screen while capturing it into a file...

Captures the whois output in a text file named as DATE-TIME_domainname.whois_out.

## Features

- Checks one or more domain names.
- Supports reading domain lists from a text file.
- Saves WHOIS output to timestamped files.
- Detects "available" messages in WHOIS output heuristically.
- Sleeps between lookups to avoid rate-limiting.

---

## Usage

```bash
whoavail domain1.com domain2.net
whoavail filename.lst
whoavail abcdfg.{com,net,org}
whoavail domain{1,2,3}.com
whoavail {abcd,efgh,jklm}.{com,net,org}
whoavail {a..z}domain.{com,net,org} | tee -a domainavail.lst
whoavail {a..z}{a..z}{a..z}.{com,net,org} | tee -a domainavail.lst
````

* If the **first parameter** is a text file (e.g. `filename.lst`), each line in the file is treated as a domain name and checked.

---

## Example

```bash
whoavail example.com
```

Example output:

```
240704-103015	Available	example.com
```

## Requirements

* Bash
* whois command-line tool

---

## Notes

* The script saves each WHOIS response in a timestamped file in the current directory.
* WHOIS servers may rate-limit requests. The script waits 3 seconds between lookups.


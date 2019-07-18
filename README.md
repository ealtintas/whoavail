# whoavail

This script may help you to query multiple domains availability status using command line interface.

You can use shell redirection to capture the output into a tab seperated text file.

If you give the first parameter the filename of a text file containing a list of domainnames (one domain in a line) all the lines in this file will be processed as a domain name.

You may also use a command like "tee -a filename.csv" with pipe to see the output on screen while capturing it into a file...

May also capture the whois output in a text file, using the param --capture

## Usage samples:

```
  whoavail filename.lst
  whoavail domain1.com domain2.net
  whoavail abcdfg.{com,net,org}
  whoavail {abcd,efgh,jklm}.{com,net,org} >> filename.csv
  whoavail {a..z}domain{0..9}.{com,net,org} | tee -a filename.csv
  whoavail domain{a..z}.{com,net,org} | tee -a filename.csv
```

## Thanks to

* https://github.com/mrkrstphr/whoaint
* https://linuxconfig.org/check-domain-name-availability-with-bash-and-whois

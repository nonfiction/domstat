## domstat - domain monitoring and statistics tool

Gathers whois data, DNS records and server status for given domain. Report
generated in markdown.

### Install

`./install` will place files into `/usr/local`. Set a custom install location like
this: `PREFIX=/home/example ./install`.

### Usage

    domstat DOMAIN [SUBDOMAINS...]
    domstat example.com www mail

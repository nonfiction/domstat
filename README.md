## domstat - domain monitoring and statistics tool

Gathers whois data, DNS records and server status for given domain.

### Install

`./install` will place files into `/usr/local`. Set a custom install location like
this: `PREFIX=/home/example ./install`.

### Usage

    domstat DOMAIN [SUBDOMAINS...]
    domstat example.com www mail

Example script to run domstat on many domains and track changes with git:

    #!/usr/bin/env bash

    echo $(git pull 2>&1 || true) > /dev/null

    if [ ! -z "$(git status --porcelain)" ];
    then
      echo "PLEASE COMMIT YOUR CHANGES FIRST!!!"
      git status
      exit 1
    fi

    cat domains.txt | while read d; do domstat "$d"; done

    git add .
    git commit -am "Auto update $TIMESTAMP"
    git push || true

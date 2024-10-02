# Conduct Search Engine Discovery Reconnaissance for Information Leakage

1. [binsearch.info](https://binsearch.info/)
2. [Google.com](https://www.google.com/)
3. [Duckduckgo.com](https://duckduckgo.com/) => [syntax](https://duckduckgo.com/duckduckgo-help-pages/results/syntax/)
4. [WaybackMachine](https://web.archive.org/) => [WaybackUrls](https://github.com/tomnomnom/waybackurls)
5. [Shodan](https://www.shodan.io)
    All queries can be used in everywhere just view the systax but while using binsearch remove the filetype part because it's not supported there
    #### Sensitive File Searches
    - `"target.com" "config" filetype:conf`
    - `"target.com" "database" filetype:sql`
    - `"target.com" "password" filetype:txt`
    - `"target.com" "credentials" filetype:xlsx OR filetype:csv`
    - `"target.com" "log file" filetype:log`
    - `"target.com" "backup" filetype:zip OR filetype:tar`

    #### Keyword-Targeted Queries
    - `"site:target.com" "confidential" "internal"`
    - `"target.com" "API key" OR "token"`
    - `"target.com" "AWS secret key" filetype:txt OR filetype:json`
    - `"target.com" "vpn config" filetype:ovpn OR filetype:conf`
    - `"target.com" "private key" filetype:pem`
    - `"target.com" "ssh key" filetype:pem`
    - `"target.com" "private key" filetype:key`
    - `"target.com" "id_rsa" filetype:txt`
    - `"target.com" "API key" filetype:json`
    - `"target.com" "access token" filetype:yaml`
    - `"target.com" "secret key" filetype:env`


    #### Directory Listings and Backups
    - `"index of /" "target.com" "backup"`
    - `"index of" "target.com" "private"`
    - `"target.com" "site backup" filetype:bak`
    - `"target.com" "ftp" "config" "site"`
    - `intitle:"index of" "target.com" config`
    - `intitle:"index of" "target.com" backup`
    - `intitle:"index of" "target.com" logs`


    #### Database Leaks
    - `"target.com" "dump" "sql" filetype:sql`
    - `"target.com" "mysql dump" filetype:sql`
    - `"target.com" "postgresql backup" filetype:sql`
    - `"target.com" "mongodb" "backup"`
    - `"target.com" "backup" filetype:sql`
    - `"target.com" "backup" filetype:bak`
    - `"target.com" "database" filetype:db`

    #### Error Messages and Logs
    - `"target.com" "error log" filetype:log`
    - `"target.com" "stack trace" "exception"`
    - `"target.com" "debug" "log" "failed authentication"`
    - `"target.com" "log file" filetype:log`
    - `"target.com" "debug log" filetype:log`
    - `"target.com" "internal documentation" filetype:pdf`

    #### Web Application and Source Code
    - `"site:target.com" "intitle:index of" "app/config"`
    - `"target.com" "site" "development" filetype:php`
    - `"target.com" "source code" filetype:java OR filetype:py`
    - `"target.com" "admin" "portal" "password"`

    #### Publicly Accessible Buckets and Repositories
    - `"target.com" "AWS S3" "public"`
    - `"target.com" "bucket" "public" "backup"`
    - `"target.com" "gitlab" "config"`
    - `"target.com" "github" "private repo"`

    #### SSL Certificates and Keys
    - `"target.com" "ssl certificate" filetype:pem OR filetype:key`
    - `"target.com" "tls" "private key"`

    #### Employee Leaks
    - `"@target.com" "resume" filetype:pdf`
    - `"@target.com" "phone number" "contact"`
    - `"@target.com" "internal document"`
    - `"target.com" "email list" filetype:csv`
    - `"target.com" "employee list" filetype:xlsx`
    - `"target.com" "usernames" filetype:txt`


    #### Network Configuration
    - `"target.com" "network config" filetype:conf`
    - `"target.com" "vpn config" filetype:ovpn`
    - `"target.com" "router configuration" filetype:cfg`

    #### Security-Related Information
    - `"target.com" "firewall configuration" filetype:xml`
    - `"target.com" "security policy" filetype:pdf`
    - `"target.com" "incident report" filetype:docx`

    #### Source Code Leaks
    - `"target.com" "source code" filetype:zip`
    - `"target.com" "git repository" filetype:git`
    - `"target.com" "source code" filetype:java`

    #### Exposed Payment or Financial Information
    - `"target.com" "credit card details" filetype:xlsx`
    - `"target.com" "payment information" filetype:csv`
    - `"target.com" "invoice" filetype:pdf`

    #### Exploiting Misconfigured Servers
    - `"target.com" "Apache" "server-status"`
    - `"target.com" "phpinfo()" "page"`
    - `"target.com" "Tomcat" "manager"`

    #### Version Disclosure
    - `"target.com" "version" filetype:xml`
    - `"target.com" "software version" filetype:txt`
    - `"target.com" "server version" filetype:conf`

use this tool to collect metafiles [metagoofil](https://github.com/opsdisk/metagoofil)
use [Google Hacking Database](https://www.exploit-db.com/google-hacking-database) for more effective queries

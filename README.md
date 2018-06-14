Domain Expiration Check Shell Script
====================================
A simple shell script to display or notify the user via email about domain status and expiry date.

Installation:
-------------
Use the curl or wget command to grab script as follows:

```
$ wget https://raw.githubusercontent.com/mpohoda/domain-check-pro/master/domain-check-pro.sh
## [ sample domain list for testing purpose ] ##
$ wget https://raw.githubusercontent.com/mpohoda/domain-check-pro/master/domain-list.txt
## [ install it in /usr/local/bin dir ] ##
$ sudo cp -vf domain-check-pro.sh /usr/local/bin/domain-check-pro
$ sudo chmod +x /usr/local/bin/domain-check-pro.sh
```

Usage:
------
Run it as follows:
```
$ domain-check-pro -d google.com
$ domain-check-pro -d cyberciti.biz
$ domain-check-pro -f domain-list.txt
```
Sample outputs:
```
Domain                    Registrar                 Status   Expires     Days Left HTTP Status Cert Status Cert Valid  Cert D Left
------------------------- ------------------------- -------- ----------- --------- ----------- ----------- ----------- -----------
affplanet.com             Wild West Domains         Valid    19-jan-2019   219       OK        Valid       28-sep-2019 470        
beezdesk.com              PSI-USA, Inc. dba         Valid    04-may-2019   324       OK        Valid       20-dec-2018 188        
getreply.com              Wild West Domains         Valid    17-oct-2019   490       OK        Valid       28-sep-2019 470        
ladesk.com                Wild West Domains         Valid    01-may-2025   2513      OK        Valid       16-júl-2020 762        
liveagent.jp              interwork                 Expiring 30-jun-2018   16        OK        Valid       05-dec-2018 173        
liveagent.se              Ascio                     Valid    19-nov-2018   158       OK        Valid       19-mar-2019 277        
liveagent.sk              Quality Unit              Valid    30-oct-2022   1599      OK        Valid       28-sep-2019 470        
postaffiliatenetwork.com  Wild West Domains         Valid    16-feb-2019   247       OK        Valid       12-jan-2019 211        
postaffiliatepro.com      Wild West Domains         Valid    20-may-2025   2532      OK        Valid       28-sep-2019 470        
qualityunit.com           Wild West Domains         Valid    29-oct-2022   1598      OK        Valid       09-júl-2020 755        
unitminer.com             Wild West Domains         Valid    29-oct-2022   1598      OK        Valid       28-sep-2019 470        
websialive.com            Tucows Domains In         Valid    01-apr-2019   291       OK        No cert                            
websialive.com.br         WebSIA Soluções Disruptiv Valid    23-mar-2019   282       OK        Valid       21-dec-2018 189        
```
[Setup Unix/Linux cron job](https://www.cyberciti.biz/faq/how-do-i-add-jobs-to-cron-under-linux-or-unix-oses/)  as follows to get email notification to send expiration notices:

```
@daily /path/to/domain-check-pro.sh -f /path/to/your-domains.txt -e you@example.com
```
Getting help
------------
```
$ domain-check-pro.sh -h
Usage: domain-check-pro.sh [ -e email ] [ -x expir_days ] [ -q ] [ -a ] [ -h ]
          {[ -d domain_namee ]} || { -f domainfile}

  -a               : Send a warning message through email
  -d domain        : Domain to analyze (interactive mode)
  -e email address : Email address to send expiration notices
  -f domain file   : File with a list of domains
  -h               : Print this screen
  -s whois server  : Whois sever to query for information
  -q               : Don't print anything on the console
  -x days          : Domain expiration interval (eg. if domain_date < days)
```

Authors:
--------
* Origianl Authors: 
	- Matty https://github.com/Matty9191
	- nixCraft https://www.cyberciti.biz/tips/domain-check-script.html
* I added new features for domain check like web status, certificate status and add support for v .sk and .br C/TLDS.

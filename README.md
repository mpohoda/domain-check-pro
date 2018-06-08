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
Domain                              Registrar                           Status   Expires     Days Left HTTP Status Certificate Status
----------------------------------- ----------------------------------- -------- ----------- --------- ----------- ------------------
affplanet.com                       Wild West Domains                   Valid    19-jan-2019   225     200         Certificate will not expire
beezdesk.com                        PSI-USA, Inc. dba                   Valid    04-may-2019   330     200         Certificate will not expire
getreply.com                        Wild West Domains                   Valid    17-oct-2019   496     200         Certificate will not expire
ladesk.com                          Wild West Domains                   Valid    01-may-2025   2519    200         Certificate will not expire
liveagent.jp                        interwork                           Expiring 30-jun-2018   22      200         Certificate will not expire
liveagent.se                        Ascio                               Valid    19-nov-2018   164     200         Certificate will not expire
liveagent.sk                        Quality Unit                        Valid    30-oct-2022   1605    200         Certificate will not expire
postaffiliatenetwork.com            Wild West Domains                   Valid    16-feb-2019   253     200         Certificate will not expire
postaffiliatepro.com                Wild West Domains                   Valid    20-may-2025   2538    200         Certificate will not expire
qualityunit.com                     Wild West Domains                   Valid    29-oct-2022   1604    200         Certificate will not expire
unitminer.com                       Wild West Domains                   Valid    29-oct-2022   1604    200         Certificate will not expire
websialive.com                      Tucows Domains In                   Valid    01-apr-2019   297     200
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

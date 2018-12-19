# DDoS attacks via other sites execution tool
# DAVOSET v.1.3.7
# Tool for conducting of DDoS attacks on the sites via other sites
# Copyright (C) MustLive 2010-2018
# Last update: 17.12.2018
# http://websecurity.com.ua
#############################################
# Program summary
#############################################

DAVOSET - it is console (command line) tool for conducting DDoS attacks on the sites via Abuse of Functionality and XML External Entities vulnerabilities at other sites.

About such attacks you can read in my article "Using of the sites for attacks on other sites" (http://websecurity.com.ua/4322/).

Video demonstration of DAVOSET: http://www.youtube.com/watch?v=RKi35-f346I

#############################################
# Usage of the tool
#############################################

To use another site as a proxy (to access or attack one site by connecting via another site):

perl davoset.pl u=http://site l=one_server.txt

To conduct DoS attack via another site:

perl davoset.pl u=http://site/large_file l=one_server.txt

To conduct DDoS attack via a list of zombie-servers:

perl davoset.pl u=http://site l=many_servers.txt

#############################################
# Attacking on the site
#############################################

1. Start the program:

davoset.pl

2. Enter URL of the site to attack:

Site: http://site

3. Get the site attacked via your list of zombie-servers.

Or from command line:

perl davoset.pl u=http://site

To set cyclic mode:

perl davoset.pl u=http://site l=list.txt m=1 c=100

To explicitly set logging:

perl davoset.pl u=http://site l=list.txt log=1

DAVOSET uses other sites as a proxy, but you can additionally use proxy.

To use Socks proxy:

perl davoset.pl u=http://site l=list.txt p=1

To use Tor:

perl davoset.pl u=http://site l=list.txt p=2

#############################################
# Testing the botnet
#############################################

1. Start the program:

davoset.pl

2. Set test mode:

Site: test

3. Get the results of testing a list of zombie-servers in the botnet.

Or from command line:

perl davoset.pl test

perl davoset.pl u=test

To explicitly set logging:

perl davoset.pl u=test log=1

#############################################
# Format of the file with list of zombie-servers
#############################################

The format of file with list of zombie-servers is the next:

http://site/script?url=
http://site/script?url=;GET
http://site/script;POST;file-with-POST.txt
http://site/script;XML;file-with-XML.txt
http://site;WP;file-for-WordPress.txt
http://site/script?url=;BYPASS

The first parameter is URL of the zombie, the second parameter is request method (in case of GET method it can be skipped) and the third parameter is file with POST parameters (in case of GET method it can be skipped).

In case of POST method the parameters are set in the file in CGI notation:

param=value&url=

The parameter (url in this case), in which URL of the site for attack is setting, must be at the end of address of zombie-server for GET request or in the end of the file with POST parameters for POST request.

In case of XML method the format of file with XML is present in the file XML.txt. Which can be used by default for such attacks.

In case of WP method the format of file with XML for WordPress is present in the file WordPress.txt. Which can be used by default for such attacks.

In case of BYPASS method it is possible to bypass protection of web application, if it's turned on. I.e. domain restriction in Google Maps plugin for Joomla.

#############################################
# Versions history
#############################################

17.12.2018 v.1.3.7

Added verbose mode.
Added SSRF in Microsoft Forefront Unified Access Gateway 2010.
Added new services into full list of zombies.
Changed default settings.
Removed non-working services from full list of zombies.

31.08.2018 v.1.3.6

Added support of SSRF vulnerability in Splunk Enterprise.
Added new services into lists of zombies.
Removed non-working services from lists of zombies.

25.07.2017 v.1.3.5

Added new services into full list of zombies.
Added command line argument for proxy.
Changed default settings.

22.06.2017 v.1.3.4

Added support of XXE vulnerability in Qlikview.
Added new services into lists of zombies.
Removed non-working services from lists of zombies.

20.05.2017 v.1.3.3

Added support of Tor as a proxy.
Added new services into full list of zombies.
Removed non-working services from full list of zombies.

20.04.2017 v.1.3.2

Added support of XXE vulnerability in CyberPower Systems PowerPanel.
Added new services into full list of zombies.
Removed non-working services from full list of zombies.

04.04.2017 v.1.3.1

Added security bypass by using cookies at appropriate sites.
Added new services into lists of zombies.
Removed non-working services from lists of zombies.

09.03.2017 v.1.3

Extended support of SSRF and added XXE vulnerability in SAP NetWeaver AS.
Added new services into full list of zombies.
Removed non-working services from full list of zombies.

30.11.2016 v.1.2.9

Added support of XXE vulnerability in AfterLogic WebMail Pro.
Added support of XXE vulnerability in Oracle BI Publisher.
Removed non-working services from full list of zombies.

26.03.2016 v.1.2.8

Added support of XXE vulnerability in EMC Cloud Tiering Appliance.
Added new services into full list of zombies.
Removed non-working services from full list of zombies.

30.11.2015 v.1.2.7

Added support of XXE vulnerability in Geoserver.
Added new services into full list of zombies.
Removed non-working services from full list of zombies.

30.10.2015 v.1.2.6

Added support of comments in the lists.
Added support of XML requests via GET (e.g. for NetIQ Access).
Removed non-working services from full list of zombies.

30.06.2015 v.1.2.5

Added support of cache bypass at web sites.
Added new services into full list of zombies.
Removed non-working services from full list of zombies.

31.03.2015 v.1.2.4

Added support of site's engine in subfolder to WP method.
Added new services into full list of zombies.
Removed non-working services from full list of zombies.

15.11.2014 v.1.2.3

Added new services into full list of zombies.
Made a list of web sites which require "http" for target URL.
Removed non-working services from full list of zombies.

31.10.2014 v.1.2.2

Added support of https URL for target sites.
Changed default settings.
Removed non-working services from full list of zombies.

23.10.2014 v.1.2.1

Added support of attacks via WordPress (based on XML support since v.1.1.2).
Added new services into both lists of zombies.
Removed non-working services from lists of zombies.

26.04.2014 v.1.2

Added support of Socks proxy.
Added new services into full list of zombies.
Removed non-working service from full list of zombies.

29.03.2014 v.1.1.9

Added new services into both lists of zombies.
Removed non-working services from lists of zombies.
Improved TestServer function.

07.03.2014 v.1.1.8

Added support of security bypass in plugin Google Maps.
Added new services into full list of zombies.
Removed non-working services from lists of zombies.

13.02.2014 v.1.1.7

Added new services into full list of zombies.
Added support of hours in timer.
Improved support of plugin Google Maps 3.

24.01.2014 v.1.1.6

Added new services into full list of zombies.
Added support of trailing slash in URL for translate.yandex.net.
Improved algorithm of work with open files.

31.12.2013 v.1.1.5

Added error handler in GetCookie().
Added new services into lists of zombies.
Removed non-working services from lists of zombies.

03.12.2013 v.1.1.4

Added new service into full list of zombies.
Removed non-working services from lists of zombies.
Fixed bug with port in two functions.

31.08.2013 v.1.1.3

Added support of cookies.
Added support of setting ports.
Added new services into full list of zombies.

31.07.2013 v.1.1.2

Added support of XML requests for XXE vulnerabilities.
Added new services into full list of zombies.
Improved work with services which require "http://" for target site.

19.07.2013 v.1.1.1

Added new services into both lists of zombies.
Improved work with services which don't support "http://" for target site.
Improved connection with some servers.

13.07.2013 v.1.1

Added logging.
Improved connection with some servers.
Fixed traffic counting.

05.07.2013 v.1.0.9

Added support of CSRF tokens.
Added new service into full list of zombies.
Improved work with URLs without trailing forward slash.

28.06.2013 v.1.0.8

Added support of POST requests.
Added new service into both lists of zombies.
Fixed bug with input URL of a site.

21.06.2013 v.1.0.7

Added new services to both lists of zombies.
Removed non-working URLs of services from both lists.
Made program to not close at connection errors.

18.06.2013 v.1.0.6

Added new services into list_full.txt.
Improved identification of the page at sending request.
Fixed bug with iterator at testing a list.

18.07.2010 v.1.0.5

Added support for command line arguments.
The next options can be set from command line: URL, test, file with list, mode and number of cycles.
Added option to set maximum number of cycles for cyclic mode.

13.07.2010 v.1.0.4

Added encoding of '&' in URL of attacking site for correct work with zombie-servers.
Added support of cyclic mode.
Added option to set number of cycles for cyclic mode.

12.07.2010 v.1.0.3

Made list of zombie-servers in external file.
Added option to set name of file with list of zombie-servers.
Added support of skipping blank lines in file with list of zombie-servers.

11.07.2010 v.1.0.2

Added function for testing a list of zombie-servers.
Added Accept and User-Agent headers (for attack and test requests) for compatibility with some servers.
Added option to set fake User-Agent (for hiding of the attack).

10.07.2010 v.1.0.1

Added statistic with requests, time and speed of work (r/s).
Added statistic with amount of traffic and speed of work (B/s).

09.07.2010 v.1.0

First release.

# DDoS attacks via other sites execution tool
# DAVOSET v.1.2
# Tool for conducting of DDoS attacks on the sites via other sites
# Copyright (C) MustLive 2010-2014
# Last update: 26.04.2014
# http://websecurity.com.ua
#############################################
# Program summary
#############################################

DAVOSET - it is console (command line) tool for conducting DDoS attacks on the sites via Abuse of Functionality vulnerabilities at other sites.

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

perl davoset.pl u=http://site l=list.txt m=1 c=100

To explicitly set logging:

perl davoset.pl u=http://site l=list.txt log=1

#############################################
# Testing of the botnet
#############################################

1. Start the program:

davoset.pl

2. Set test mode:

Site: test

3. Get the results of testing of list of zombie-servers in the botnet.

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
http://site/script?url=;BYPASS

The first parameter is URL of the zombie, the second parameter is request method (in case of GET method it can be skipped) and the third parameter is file with POST parameters (in case of GET method it can be skipped).

In case of POST method the parameters are set in the file in CGI notation:

param=value&url=

The parameter (url in this case), in which URL of the site for attack is setting, must be at the end of address of zombie-server for GET request or in the end of the file with POST parameters for POST request.

In case of XML method the format of file with XML is present in the file XML.txt. Which can be used by default for such attacks.

In case of BYPASS method it is possible to bypass protection of web application, if it's turned on. I.e. domain restriction in Google Maps plugin for Joomla.

#############################################
# Versions history
#############################################

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
Fixed bug with iterator $i at testing list.

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

Added function for testing of list of zombie-servers.
Added Accept and User-Agent headers (for attack and test requests) for compatibility with some servers.
Added option to set fake User-Agent (for hiding of the attack).

10.07.2010 v.1.0.1

Added statistic with requests, time and speed of work (r/s).
Added statistic with amount of traffic and speed of work (B/s).

09.07.2010 v.1.0

First release.

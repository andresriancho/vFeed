vFeed & vFeed API
=================

The open source cross-linked local vulnerability database

vFeed is an open source naming scheme concept that provides extra structured detailed 3rd parties references for a CVE entry. 
While the emergence of the Open Standards helped undeniably to shape a new way to communicate about vulnerabilities1, the new vFeed is adding an intelligent structured xml feed that provides effective level of information (meta-data) related to vulnerability.


Internally, vFeedCore (not published yet) collects the basis xml feeds which are generated by reliable references and correlates it across multiple information sources. Here are examples of 3rd parties sources (just to name a few):

* Security standards

  - CVE (http://cve.mitre.org)
  - CWE (http://cwe.mitre.org)
  - CPE (http://cpe.mitre.org) 
  - OVAL (http://oval.mitre.org) 
  - CAPEC (http://capec.mitre.org) 
  - CVSS (http://www.first.org/cvss) 

* Vulnerability Assessment & Exploitation IDs (Metasploit, Saint Corporation, Nessus Scripts, ZDI, Exploit-DB, milw0rm)
* Vendors Security Alerts

  - Microsoft MS
  - Mandriva
  - Redhat
  - Cisco
  - Sun
  - Gentoo
  - Apple
  - ...


Key features
=================

* Built using open source technologies
* Fully downloadable SQLite local vulnerability database 
* Structured new XML format to describe vulnerabilities
* Based on major open standards CVE, CPE, CWE, CVSS..
* Support correlation with 3rd party security references (CVSS, OSVDB, OVAL…)
* Extended to support correlation with security assessment and patch vendors (Nessus, Exploit-DB, Redhat, Microsoft..)
* Simple & ready to use Python module with more than 15 methods

Target Audience
=================

* Penetration testers who want to analyze CVEs and gather extra information to help shape avenues to exploit vulnerabilities.
* Security auditors who want to report accurate information about findings. vFeed could be the best way to describe a CVE with attributes based on standards and 3rd party references as vendors or companies involved into standarization efforts.
* Security tools vendors / security open source developers who need to implement libraries to enumerate useful information about CVEs without wasting time to correlate and to create a proprietary database. vFeed is by far the best solution. Methods can be invoked from programs or scripts with a simple call.
* Any security hacker who is conducting researches and need a very fast and accurate way to enumerate available exploits or techniques to check a vulnerability


Changelog
=========

Beta v0.3.9
-----------

* Refactoring as a first step towards having the vfeed module in pypi.
* Bug fixes
* PEP8 compatible code (at least what autopep8 can do)
* README format is now RST

Beta v0.3.5
-----------

* Extended the checkREDHAT method

  - Added the support of Redhat OVAL ids reference. Now, vFeed reports more accurate Redhat Patchs with associated Redhat OVAL ids 
  - Added the support of Redhat Bugzilla Ids and advisory issue date

* Added the support of Debian ids. vFeed now reports DSA as patch
* Added the support of Mandriva ids.
* Extended Exploitation Checks to support Saint Corporation Exploits. If available, title, link to exploit file are reported
* To reflect the newest cross references, 3 new methods have been added 

  - checkREDHAT extended to support Redhat OVAL, Bugzilla ids more redhat patchs ids.
  - checkDEBIAN to check for debian patchs
  - checkMANDRIVA to check for mandrake patchs
  - checkSAINT to check for Saint corporation exploits 

* Fixed a small bug in checkRISK() (thanks to Ronald Bister https://github.com/savon-noir)
* Updating wiki documentation in progress
 
Beta v0.3
---------

* Rewrite vFeedApi.py as a class (added _init_db() method with sql query sanitization)
* Added a class vFeedInfo to return variables and global configuration
* Added a config.py module.
* Updated the "update.py". Now verifies if a new db is available (support of checksum)
* Renamed method checkReferences into checkREF()
* Updated the sample scripts (vFeedAPI_calls_1 and _2) to reflect the changes
* documentation update (always in progress) and will be mainly delivered via vfeed github wiki.

Beta v0.2
---------

* moved project to github
* added an updater.py to download the vFeed vulnerability database

Beta v0.1
---------
* initial release 
* read documentation


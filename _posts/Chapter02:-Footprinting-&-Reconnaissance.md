## 2.1 Footprinting Concepts

Footprinting is the collection of every possible information regarding the target and target network. This collection of information helps in identifying different possible ways to enter into the target network. The overall purpose of this phase is to keep interaction with the target to gain information without any detection or alerting.

The major objectives of Footprinting are:

1. To know security posture
2. To reduce focus area
3. Identify vulnerabilities
4. Draw network map

**Types**
- Passive/Anonymous - information gathering without revealing anything about yourself, without direct interaction.
- Pseudonymous - making someone else take the blame for your action.
- Active footprinting - gathering information about the target with direct interaction.

**Objectives**

Footprinting helps to:
- Know security posture
- Reduce focus area - reduce a big organization to a range of domain names or network blocks.
- Identify vulnerabilities
- Draw network map

## 2.2 Footprinting Methodology

- Footprinting through Search Engines
- Footprinting through Web Services
- Footprinting through Social Networking Sites
- Footprinting through Websites
- Footprinting through Email
- Footprinting through Competitive Intelligence
- Footprinting through WHOIS
- Footprinting through DNS
- Footprinting through Network
- Footprinting through Social Engineering

### <u>Footprinting through Search Engines and Advanced Google Hacking Techniques</u>

Google [advanced search](https://www.google.com/advanced_search):

  - | Operators     | Description                                            |
    | ------------- | ------------------------------------------------------ |
    | site:         | Search for the result in the given domain              |    
    | related:      | Search for Similar web pages                           |
    | cache:        | Display the web pages stored in Cache                  |
    | link:         | List the websites having a link to a specific web page |
    | allintext:    | websites containing a specific keyword                 |
    | intext:       | documents containing a specific keyword                |
    | allintitle:   | containing a specific keyword in the title             |
    | intitle:      | documents containing a specific keyword in the title   |
    | allinurl:     | websites containing a specific keyword in URL          |
    | inurl:        | documents containing a specific keyword in URL         |
    | inanchor:     | in the anchor text on links to the page                |
    | allinanchor:  | all query terms in the anchor text on links to the page|

Google dorks to find the VoIP network and device information:

  - | Google Dork | Description|
    | ------------------------------- | ----------------------------------------- |
    | inurl:/voice/advanced/ intitle:Linksys SPA configuration | Finds the Linksys VoIP router configuration page|
    | intitle:asterisk.management.portal web-access | Look for the Asterisk management portal |
    | inurl:”NetworkConfiguration” cisco | Find the Cisco phone details |
    | inurl:”ccmuser/logon.asp”	Find Cisco call manager |
    | intitle:asterisk.management.portal web-access | Finds the Asterisk web management portal |
    | inurl:8080 intitle:”login” intext:”UserLogin” “English” | VoIP login portals |
    | intitle:” SPA Configuration” | Search Linksys phones |
    
**Google Hacking Database (GHDB)**

Google Hacking was popularized by Johnny Long who categorized the queries in a database known as Google Hacking Database (GHDB). Through [exploit-db](https://www.exploit-db.com/google-hacking-database/), you can search GHDB or browse the category of GHDB. Similarly, [hackersforcharity](www.hackersforcharity.org) is also an online platform for GHDB. Google hacking database provide the updated information that is useful for exploitation such as footholds, sensitive directories, vulnerable files, error messages and much more.

Some categories are:

- footholds
- Files containing usernames
- Sensitive Directories
- Web Server Detection
- Vulnerable Files
- Vulnerable Servers
- Error messages
- Files containing Juicy Info
- Files containing passwords
- Sensitive Online shopping Info
- Network or vulnerability data
- Pages containing login portals
- Various Online Devices
- Advisories and vulnerabilities

### <u>Web services Footprinting</u>

The target organization's official website can provide information such as Software running, versions of these software’s, operating systems, Sub-directories, database, scripting information, and other details. This information can be gathered by online service as defined earlier like netcraft.com or by using software such as Burp Suite, Zaproxy, Website Informer, Firebug, and others.

**Finding the Top-Level Domains (TLDs) and subdomains**

The subdomain helps to access the private functions of an organization; most organizations use common formats for sub-domains, therefore, a hacker who knows the external URL can often discover sub-domains. There are some famous tools as:
- Netcraft
- Sublist3r

**Determining the Operating System**
One useful tool is [netcraft](https://www.netcraft.com/tools/) and also [Shodan](https://www.shodan.io)


- **Determining the Operating System** Netcraft, shodan and [Censys](https://censys.io)
- **Collect Location Information** some pupular services as: Google Earth, Google Map, Bing Map, Wikimapia, Yahoo Map...
- **People Search Online Services** Some examples are [privateeye](www.privateeye.com), [peoplesearchnow](www.peoplesearchnow.com), [AnyWho](www.anywho.com),
[intelius](www.intelius.com), [peoplefinders](www.peoplefinders.com); *Probably not working:* [publicbackgroundchecks](www.publicbackgroundchecks.com),  [4111](www.4111.com)
- **Gather Information from Financial Services** [Google finance](https://www.google.com/finance) and [Yahoo Finace](finance.yahoo.com)
- **Footprinting through Job Sites** [linkedIn](www.linkedIn.com), 
[monster](www.monster.com), [indee](www.indeed.com), [careerbuilder](www.careerbuilder.com)
- **Monitoring Target Using Alerts** [Google](https://www.google.es/alerts)
- **Information Gathering Using Groups, Forums, and Blogs**

Gathering information from linkedIn -> **InSpy**

### <u>Footprinting through Social Networking Sites</u>

Social networking sites can be great sources of information about a target. There are not barriers for attackers to access to the public pages of accounts created on the social networking sites. Hackers may create fake accounts and use social engineering to lure the victim to reveal more info.

### <u>Website Footprinting</u>

It refers to monitoring and analyzing the target organization's website for information. One of the tools more useful is Burp Suite.

**Website Footprinting using Web Spiders**
Web Spiders or Web Crawlers are the internet bots that are used to perform systematic, automated browsing on World Wide Web. This browsing is targeted to a website to gather specific information such as names, email addresses.

**Mirroring Entire Website**
Mirroring a website is the process to mirror the entire website in the local system. Downloading entire website onto the system enables the attacker to use, inspect the website, directories, structure and to find other vulnerabilities from this downloaded mirrored website copy in an offline environment. Some tools are:
- [Win HTTrack Website Copier](https://www.httrack.com/page/2/)
- [Surf offline Professional](http://www.surfoffline.com/)
- [Black Widow](http://softbytelabs.com)
- [NCollector Studio](http://www.calluna-software.com)
- [Website Ripper Copier](http://www.tensons.com)
- [Teleport Pro](http://www.tenmax.com)
- [Portable Offline Browser](http://www.metaproducts.com)
- [PageNest](http://www.pagenest.com)
- [Backstreet Browser](http://www.spadixbd.com)
- [Offline Explorer Enterprise](http://www.metaproducts.com)
- [GNU Wget](http://www.gnu.org.com)
- [Hooeey Webprint](http://www.hooeeywebprint.com)

**Extract Website Information**
[Archive](https://archive.org)  provides an archived version of websites, including Summary on MIME-type Count, Summary for TLD/HOST/Domain, a sitemap of website and dates, Calendar view and other information.

**Monitoring Web Updates**
Website-Watcher and other available tools offer website monitoring. These tools automatically check for updates and changes made to target websites. Other tools are:
- [Change Detection](http://www.changedetection.com)
- [Follow That Page](http://www.followthatpage.com)
- [Page2RSS](http://page2rss.com)
- [Watch That Page](http://www.watchthatpage.com)
- [Check4Change](https://addons.mozilla.org)
- [OnWebChange](http://onwebchange.com)
- [Infominder](http://www.infominder.com)
- [TrackedContent](http://trackedcontent.com)
- [Websnitcher](https://websnitcher.com)
- [Update Scanner](https://addons.mozilla.org)

**Metadata**

Using Metagoofil or FOCA

### <u>Email Footprinting</u>

- *Email header* - may show servers and where the location of those servers are
- *Email tracking* - services can track various bits of information including the IP address of where it was opened, where it went, etc.

Polite Mail is a tool for Email footprinting. It tracks email communication with Microsoft Outlook. Tracing an email using email header can reveal the following information:

- Destination address
- Sender's IP address
- Sender's Mail server
- Time & Date information
- Authentication system information of sender's mail server

Popular Email Tracking tools are as follows:

- Polite Mail
- Email Tracker Pro
- Email Lookup
- Yesware
- Who Read Me
- Contact Monkey
- Read Notify
- Did They Read It
- Get Notify
- Point of Mail
- Trace Email
- G-Lock Analytics


### <u>Competitive Intelligence</u>

Competitive Intelligence is a process that involves the gathering, analyzing and distribution of information about products, customers, competitors and technologies using the internet. It helps in determinig what the competitors are doing and how competitors are positionign their products and services. There are two approach the **direct** one, and the **indirect**.

To get competitive information, you should visit websites like [EDGAR](https://www.sec.gov/edgar.shtml), [LexisNexis](https://risk.lexisnexis.com), [Business Wire &](www.businesswire.com/portal/site/home/), [CNBC](www.cnbc.com) and [Hoovers](www.hoovers.com). 
[FACTIVA](https://www.dowjones.com)

These websites gather information and reports of companies including legal news, press releases, financial information, analysis reports, and upcoming projects and plans as well.

**What are the company's plans?**

- MarketWatch - tracks the pulse of markets for engaged investors
- The wall street transcipt
- Alexa
- Euromonitor
- Experian
- SEC Info
- The search monitor
- USPTO

**What expert opinions say about the company?**

- Copernic tracker
- SEMRush
- AttentionMeter
- ABI/INFORM Global
- SimilarWeb

**Monitoring Website Traffic of Target Company**
- Total visitors Clicky
- Page views Opentracker
- Bounce rate Google Analytics
- Live visitors Map [Web-stat](https://www.web-stat.com/)
- [Monitis](http://www.monitis.com/)
- Site ranking and audience [Alexa](https://www.alexa.com/)

**Tracking Online Reputation of the Target**
Online Reputation Management (ORM) offers to monitor an organization's reputation.
Tools for Tracking Online Reputation:
- [Google Alerts](https://www.google.com)
- [WhosTalkin](http://www.whostalkin.com)
- [Rankur](http://rankur.com)
- [PR Software](http://www.cision.com)
- [Social Mention](http://www.socialmention.com)
- [Reputation Defender](https://www.reputation.com)
- [Trackur](www.trackur.com)

### <u>WHOIS Footprinting</u>

It is a query and response sued for queryng databases that store the registered users or assignees fo an internet resource such as a domain name, ownership information. IP Address, Netblock data, Domain Name Servers... [Domain tools](https://whois.domaintools.com)

There are two types, *thick whois* (stores the complete whois information) and *thin whois* (only stores the name of the wois server of the regitrar of a domain)

**Regional Internet Registres (RISs)**

  - **ARIN** - North America
  - **APNIC** - Asia Pacific
  - **RIPE** - Europe, Middle East
  - **LACNIC** - Latin America
  - **AfriNIC** - Africa
  
**Finding IP Geolocation Information**

- [IP2Location](https://www.ip2location.com)


### <u>DNS Footprinting</u>

- Ports

  - Name lookup - UDP 53
  - Zone transfer - TCP 53

- Zone transfer replicates all records

- **Name resolvers** answer requests

- **Authoritative Servers** hold all records for a namespace

- **DNS Record Types**

  

  - | Name  | Description        | Purpose                                        |
    | ----- | ------------------ | ---------------------------------------------- |
    | SRV   | Service            | Points to a specific service                   |
    | SDA   | Start of Authority | Indicates the authoritative NS for a namespace |
    | PTR   | Pointer            | Maps an IP to a hostname                       |
    | NS    | Nameserver         | Lists the nameservers for a namespace          |
    | MX    | Mail Exchange      | Lists email servers                            |
    | CNAME | Canonical Name     | Maps a name to an A reccord                    |
    | A     | Address            | Maps an hostname to an IP address              |


- [DNSStuff](https://www.dnsstuff.com)
- [Domain Dossier](https://centralops.net/co/)
- [network-tools](http://network-tools.com)
- [kloth](http://www.kloth.net)
- [mydns](http://www.mydnstools.info)
- [nirsoft](http://www.nirsoft.net)
- [dnswatch](http://www.dnswatch.info)
- [ultratools](http://www.ultratools.com)
- [webmaster](http://www.webmaster-toolkit.com)

- **DNS Poisoning** - changes cache on a machine to redirect requests to a malicious server

- **DNSSEC** - helps prevent DNS poisoning by encrypting records

- **IP Address Management**


- **Nslookup** - performs DNS queries

  - nslookup [ - options ] [ hostname ]
  - interactive zone transfer
    - nslookup
    - server <IP Address>
    - set type = any
    - ls -d domainname.com

- **Dig** - unix-based command like nslookup

  - dig @server name type

### <u>Network Footprinting</u>

Information as Network address ranges, Hostnames, Exposed hosts, OS and application version information, Patch state of the host and the applications and Structure of the applications and back-end servers. Some tools:

- Whois
- Ping
- Nslookup
- Tracert

Traceroute or Tracert command results in the path information from source to destination in the hop by hop manner. The result includes all hops in between source to destination. The result also includes latency between these hops.

Path Analyzer Pro and VisualRoute are also useful.


### <u>Footprinting through Social Engineering</u>

- **Eavesdropping** - gathers information by listening to the conversation
covertly.
- **Phishing** - mail looks legitimate but no.
- **Shoulder Surfing** - gathering information by standing behind a target when he is interacting with sensitive information.
- **Dumpster Diving** - is the process of looking for treasure in trash.

## 2.3 Footprinting Tools

**Maltego**
Maltego is a data mining tools that are powered by Paterva.


**Recong0-ng**
It is a full feature Web Reconnaissance framework used for
information gathering purpose as well as network detection. This tool is
written in python, having independent modules, database interaction and
other features.

**Additional Footprinting Tools**
FOCA tool finds Metadata and other hidden information.

- [Prefix WhoIs](http://pwhois.org)
- [Netmask](http://www.phenoelit.org)
- [DNS-Digger](http://www.dnsdigger.com)
- [Email Tracking Tool](http://www.filley.com)
- [Ping-Probe](http://www.ping-probe.com)
- [Google Hacks](http://code.google.com)
- [OSRFramework](https://github.com/i3visio/osrframework)


## 2.4 Countermeasures of Footprinting

Footprinting countermeasure includes the following measures to mitigate footprinting:
- Employees on an organization must be restricted to access social
networking sites from the corporate network.
- Devices and Servers are configured to avoid data leakage.
- Provide education, training, and awareness of footprinting, impact, methodologies, and countermeasures to the employees of an organization.
- Avoid revealing sensitive information in Annual reports, Press releases,
etc.
- Prevent search engines to cache web pages.

## 2.5 Footprinting Penetration Testing

It is used to determine an organization's information; helps to prevent information leakage, social engineering attempts, DNS record retrieval form publically available servers.

### <u>Steps</u>

1. **Get proper authorization**
2. **Define the scope of the assessment**
3. Footprinting through Search Engines
4. Footprinting through Web Services
5. Footprinting through Social Networking Sites
6. Footprinting through Websites
7. Footprinting through Email
8. Footprinting through Competitive Intelligence
9. Footprinting through WHOIS
10. Footprinting through DNS
11. Footprinting through Network
12. Footprinting through Social Engineering
13. **Document all the findings**
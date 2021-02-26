# 5 Vulnerability Analysis

## 5.1 Vulnerability Assessment Concepts

### <u>Vulnerability Research</u>

It is the process of discovering vulnerabilities and design flaws that will open an OS and its apps to attack or misue. The vulnerabilities are classified based on severity level (low, medium or high) and exploit range (remote or local).

An administrator needs vulnerability research:
- To gather information about security trends, threats and attacks
- To find weaknesses, and alert the network admin
- To get information that helps prevent the security attack 
- To know how to recover from a network attack

### <u>Vulnerability Classification</u>

+ Misconfiguration
+ Default installations
+ Buffer Overflows
+ Unpatched Servers 
+ Design Flaws
+ OS flaws
+ Application flaws
+ Open services
+ Default Passwords

**Vulnerability Assessment** is an examination of the ability of a system or app, including current security procedures and controls, to withstand assault. It may be used to indentify weaknesses that could be exploited or predict the ecffectiveness of additional security measures. Vulnerability scanners are able to indentify:
- OS version.
- IP and TCP/UDP ports listening.
- Applications installed.
- Accounts with weak Passwords.
- Default services and apps.
- Files and folders with weak permissions.

**Types of Vulnerability Assessment**

- Active: network scanning
- Passive: sniff the network traffic
- External/Internal
- Host based Assessment: in a specific workstation
- Network Assessment
- Application Assessment: web infrastructure for any misconfiguration.
- Wireless Network Assessment

### <u>Vulnerability Management life Cycle</u>

It is an important process that hepls in finding and remediating security weaknesses before they are exploited. The phases involved are:
1. **Creating baseline**: critical assets are identified and prioritized. Also known as Pre-assesment pahes, it refers to the preparatory phase, which includes defining policies and standards, defining the scope of assessment, designign the appropiate information protection procedure...

2. **Vulnerability Assessment** the ultimate goal includes scanning, examining, evaluating and reporting the vulnerabilities. The steps are: examining physical security, check msiconfigurations and human errors, run vulnerability scans, indentify and prioritize, apply business and technology context to scanner results, OSINT to validate the vulnerabilities and create a scan reporting


3. **Risk Assessment** risk are identified, characterized and classified.

The next phases are the *Post Assessment Phases*

4. **Remediation** during this phase recommendations are prioritized, action plan . lessons learned, root-cause analysis, conduct awareness training

5. **Verification** dynamic analysis and attack surface review

6. **Monitor** IDS/IPS, SIEM, firewalls... continuous security monitoring.

## 5.2 Vulnerability Assessment Solutions

### <u>Comparing Approaches to Vulnerability Assessment</u>

There are four types of vulnerability assessment solutions:

+ Product-based: they are installed in the org's internal network. They are behind the firewall.
+ Service-based: offered by third parties.
+ Tree-based: different strategies for each machine.
+ Inference-based: scanning starts by building an inventory of protocols, then detect which ports are attached to services and finally it selects vulnerabilities.

### <u>Working of Vulnerability Scanning Solutions</u>

Vulnerability scanning solutions perform vulnerability penetration tests on the organization network in three steps:

- Locating nodes: discovering live hosts
- Performing service discovery on them: open ports and services
- Testing those services for known vulnerabilities

### <u>Types of Vulnerability Assessment Tools</u>

+ **Host-Based**. It finds and identifies OS running on a host and tests it for known deficiences. It also searches for common application and services.
+ **Depth Assessment Tools** are used to identify vulnerabilities to an unstable degree of depth, unknown vulnerabilities in a system. Such types of tools include fuzzers that give arbitrary input to a system's interface.
+ **Application-Layer** are directed toward webservers or databases.
+ **Scope Assessment Tools** security to the IT system by testing for vulnerabilities in the applications and SO.
+ **Active/Passive** Consuming or not network resources.
+ **Location/Data Examined Tools** network-based, agent-based, proxy and cluster.

**Characteristics of a Good Vulnerability Assessment Solution**
Ensures correct outcomes by testing the network, uses well-organized inference-based approach, updated db, reports, supports various networks, suggests proper remedies and workarounds to correct vulnerabilities and imitates the outside view of attackers.

**Choosing a Vulnerability Assessment Tool**
The criteria to be followed are as follows:
+ Types of vulnerabilities being assessed
+ Testing capability of scanning 
+ Ability to provide accurate reports
+ Efficient and accurate scanning
+ Capability to perform a smart search
+ Functionality for writing own test
+ Test run scheduling

**Best practices for selecting vulnerability assessment tools**
* Ensure that it not damage your network or system
* Understand the functionality and information to collect
* Source location of the scan
* Enable loggin every time you scan
* Scan frequently

## 5.3 Vulnerability Scoring Systems

### <u>Common Vulnerability Scoring System (CVSS)</u>

The [Common Vulnerability Scoring System](https://www.first.org/cvss/) (CVSS) provides a way to capture the principal characteristics of a vulnerability and produce a numerical score reflecting its severity. The numerical score can then be translated into a qualitative representation (such as low, medium, high, and critical) to help organizations properly assess and prioritize their vulnerability management processes. CVSS is composed of [three metric groups](https://www.first.org/cvss/specification-document):

1. The **Base metric** group represents the intrinsic characteristics of a vulnerability that are constant over time.
2. The **Temporal metric** group reflects the characteristics of a vulnerability that may change over time but not across user environments.
3. The **Environmental metric** group represents the characteristics of a vulnerability that are relevant and unique to a particular user’s environment.
  - | severity | base score range |
    | -------- | ------------------------ |
    | None | 0.0 |
    | Low | 0.1 - 3.9 |
    | Medium | 4.0 - 6.9 |
    | High | 7.0 - 8.9 |
    | Critical | 9.0 - 10.0 |

In CVSS v2 (the previous one) there where only three levels, Low0-3.9, Medium 4.0-6.9 and High 7.0-10

### <u>Common Vulnerability and Exposure (CVE)</u>

[Common Vulnerabilities and Exposures](https://cve.mitre.org/index.html) is a list of common identifiers for publicly known cybersecurity vulnerabilities.

Use of CVE Entries, which are assigned by CVE Numbering Authorities (CNAs) from around the world, ensures confidence among parties when used to discuss or share information about a unique software or firmware vulnerability, provides a baseline for tool evaluation, and enables automated data exchange.

CVE is:
- One identifier for one vulnerability or exposure
- One standardized description for each vulnerability or exposure
- A dictionary rather than a database
- How disparate databases and tools can "speak" the same language
- The way to interoperability and better security coverage
- A basis for evaluation among services, tools, and databases
- Free for public download and use
- Industry-endorsed via the CVE Numbering Authorities, CVE Board, and numerous products and services that include CVE

### <u>National Vulnerability Database (NVD)</u>

The NVD is the U.S. government repository of standards based vulnerability management data represented using the Security Content Automation Protocol (SCAP). This data enables automation of vulnerability management, security measurement, and compliance. The NVD includes databases of security checklist references, security-related software flaws, misconfigurations, product names, and impact metrics.

### <u>Resources for Vulnerability Research</u>

+ [Microsoft Vulnerability Research](https://www.microsoft.com/en-us/msrc/msvr)
+ [Exploit Database](https://www.exploit-db.com)
+ [CVE Details](https://www.cvedetails.com)
+ [Rapid7](https://www.rapid7.com/db/)
+ [Security Tracker](https://securitytracker.com)
+ [Security Focus](https://www.securityfocus.com)
+ [Help Net Security](https://www.helpnetsecurity.com)

## 5.4 Vulnerability Assessment Tools

* [Qualys](https://www.qualys.com/apps/vulnerability-management/) is a cloud-based service that gives you a global visiblity into where your IT assets are vulnerable and how to protect them.
- Agent-based detection
- Constant monitoring and alerts-
- Comprehensive coverage and visibility
- VM for the perimeter-less world
- Discover forgotten devices and organize your host assets
- Scan for vulnerabilities everywhere, accurately and efficiently
- Identify and prioritize risks
- Remediate vulnerabilities
- Custom reports

* [Nessus](https://www.tenable.com/products/nessus) is a solution for identifying vulnerabilities, configuration issues, and malware that attackers use to penetrate networks.

* [GFI LanGuard](https://www.gfi.com/products-and-solutions/network-security-solutions/gfi-languard) scans, detects, assesses and rectifies security vulnerabilities in a network and connected devices.

* [Qualys FreeScan](https://freescan.qualys.com/freescan-front/)

* [Nikto](https://cirt.net/Nikto2)

* [OpenVAS](https://www.openvas.org)

* [Retina CS](https://www.beyondtrust.com/vulnerability-management)

* [SAINT](https://www.carson-saint.com)

* [Microsoft Baseline Security Analyzer (MBSA)](https://www.microsoft.com/technet/security/tools/mbsahome.mspx)

* [AVDS Automated Vulnerability Detection System](https://beyondsecurity.com/avds.html)

There are also tools for mobile that we are not covering on this resume.

## 5.5 Vulnerability Assessment Reports

The vulnerability assesment report discloses the risk that are detected after scanning the network. The report provides details of all the possible vulnerabilities with regard to the company's security polices. It must cover the next points:

- Scan information
- Target information
- Results
- Target
    - Node
    - OS
    - Date
- Services
- Classification
- Assessment

There are two types of vulnerability assessment reports: the vulnerability assesment report and the summary.

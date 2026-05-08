# Sublist3r — Subdomain Enumeration Tool

## 1. Overview

**Sublist3r** is an OSINT and reconnaissance tool used to discover subdomains of a target domain.

It is commonly used during:

- Footprinting
- Reconnaissance
- Bug bounty hunting
- VAPT
- Attack Surface Mapping

Sublist3r automates subdomain discovery using public search engines and OSINT sources.

---

## 2. What is Subdomain Enumeration?

Subdomain Enumeration means identifying subdomains related to a target domain.

Example:
Main domain:microsoft.com

- Possible subdomains:
- support.microsoft.com
- admin.microsoft.com
- learn.microsoft.com
- api.microsoft.com

Organizations use subdomains for:

- login systems
- APIs
- support portals
- admin panels
- testing systems
- cloud services

Finding these subdomains helps understand the public attack surface.

---

## 3. Why Sublist3r Is Important

Manually finding subdomains is slow and incomplete.

Sublist3r automates this process and searches multiple public sources to discover subdomains quickly.

It helps identify:

- public services
- exposed systems
- forgotten hosts
- testing environments
- APIs
- cloud-related services

This makes it valuable in cybersecurity reconnaissance.

---

## 4. What Sublist3r Uses Internally

Sublist3r gathers subdomains from public sources such as:

- Google
- Bing
- Yahoo
- Baidu
- Ask
- Netcraft
- VirusTotal
- ThreatCrowd
- DNSdumpster

It collects publicly available information only.

---

## 5. Installing Sublist3r

### Step 1 — Open Terminal

Open terminal in Kali Linux.

### Step 2 — Clone Sublist3r

Run:
```bash
git clone https://github.com/aboul3la/Sublist3r.git
```
### Step 3 — Move into Directory
```bash
cd Sublist3r
```
![Kali Terminal](images/sublist3r/sublist3r-terminal.png)
### 6. Basic Sublist3r Syntax
Basic command:

```bash
python3 sublist3r.py -d target.com
```
#### Understanding the Command
- python3	Runs Python
- sublist3r.py	Tool script
- -d	Target domain
- target.com	Domain to enumerate
### 7. Basic Example
Example:

```bash
python3 sublist3r.py -d microsoft.com
```
What This Does
Sublist3r searches public sources for subdomains related to microsoft.com.

![Sublist3r Basic Enumeration](images/sublist3r/sublist3r-basic.png)


### 8. Saving Results to a File
Command:

```bash
python3 sublist3r.py -d microsoft.com -o microsoft_subdomains.txt
```
Understanding the
Parameter	Purpose
-o	Output file
microsoft_subdomains.txt	Save results
What This Does
Discovers subdomains

Saves results into a text file

Useful for documentation and further analysis.


![Sublist3r Save Results](images/sublist3r/sublist3r-save.png)

### 9. Viewing Saved Results
Command:

```bash
cat microsoft_subdomains.txt
```
What This Shows
Displays discovered subdomains stored in the file.


![Sublist3r View Results](images/sublist3r/sublist3r-view.png)

### 10. Using Multiple Threads
Command:

```bash
python3 sublist3r.py -d microsoft.com -t 50
```
Understanding the Parameter
Parameter	Purpose
-t	Number of threads
What This Does
Increases speed by using multiple threads.

![Sublist3r Multiple Threads](images/sublist3r/sublist3r-threads.png)

### 11. Enabling Brute Force
Command:

```bash
python3 sublist3r.py -d microsoft.com -b
```
What is Brute Force Here?
Sublist3r tries common subdomain names such as:

admin

mail

api

login

to identify additional subdomains.


![Sublist3r Brute Force](images/sublist3r/sublist3r-bruteforce.png)

### 12. Full Practical Example
Goal
Discover subdomains related to Microsoft and save them to a file.

Command Used
```bash
python3 sublist3r.py -d microsoft.com -o microsoft_subdomains.txt
```
Steps Performed
Installed Sublist3r

Opened terminal

Ran subdomain enumeration

Saved results to file

Reviewed discovered subdomains

Example Results
text
support.microsoft.com
admin.microsoft.com
learn.microsoft.com
api.microsoft.com
Security Value
This demonstrates how subdomain enumeration helps identify:

public-facing services

APIs

support systems

exposed infrastructure

Learning Outcome
Using Sublist3r helped understand:

subdomain enumeration

OSINT-based reconnaissance

attack surface mapping

automated reconnaissance

![Sublist3r Full Example](images/sublist3r/sublist3r-full-example.png)

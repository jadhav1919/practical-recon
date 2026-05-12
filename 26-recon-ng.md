# Recon-ng 
## Overview

Recon-ng is an Open Source Intelligence (OSINT) and reconnaissance framework used for automated information gathering during penetration testing and ethical hacking.

It helps security professionals gather:

- Subdomains
- Hosts
- IP addresses
- Whois data
- Contacts
- Technologies
- Open ports
- OSINT intelligence

---

# Why Recon-ng?

Recon-ng is useful for:

- Footprinting
- Reconnaissance
- Bug bounty hunting
- Red teaming
- Ethical hacking
- OSINT investigations

---

# Features

- Modular architecture
- Built-in database
- Workspace management
- API integration
- Automated reconnaissance
- Reporting support
- Web interface support
- Data correlation

---

# Architecture

```text
Recon-ng
│
├── Workspaces
├── Database
├── Modules
├── API Keys
├── Reports
└── Dashboard
```

---

# Installation

## Kali Linux Installation

```bash
sudo apt update
sudo apt install recon-ng
```

Start Recon-ng:

```bash
recon-ng
```

---

## Screenshot

![Recon-ng Installation](images/recon-ng/recon-installation.png)

---

# Manual Installation

```bash
git clone https://github.com/lanmaster53/recon-ng.git

cd recon-ng

pip3 install -r REQUIREMENTS

python3 recon-ng
```

---

# Starting Recon-ng

```bash
recon-ng
```

Expected Output:

```bash
[recon-ng][default] >
```

---

## Screenshot

![Starting Recon-ng](images/recon-ng/recon-start.png)

---

# Basic Workflow

```text
Create Workspace
        ↓
Insert Target Domain
        ↓
Install Modules
        ↓
Load Module
        ↓
Set Options
        ↓
Run Module
        ↓
View Results
        ↓
Generate Report
```

---

# Workspaces

## What is Workspace?

Workspace = Separate project environment

Stores:
- Domains
- Hosts
- Contacts
- Results
- Reports

---

# Workspace Commands

## Create Workspace

```bash
workspaces create ceh_lab
```

## List Workspaces

```bash
workspaces list
```

## Select Workspace

```bash
workspaces select ceh_lab
```

## Remove Workspace

```bash
workspaces remove ceh_lab
```

---

## Screenshot

![Workspace Commands](images/recon-ng/workspaces.png)

---

# Dashboard

Displays activity summary.

```bash
dashboard
```

Shows:
- Domains
- Hosts
- Contacts
- Vulnerabilities
- Modules used

---

## Screenshot

![Dashboard Output](images/recon-ng/dashboard.png)

---

# Database

Recon-ng stores information inside its built-in database.

---

# Database Tables

```text
companies
contacts
credentials
domains
hosts
leaks
locations
netblocks
ports
profiles
repositories
vulnerabilities
```

---

# Insert Domain

```bash
db insert domains
```

Enter:

```text
example.com
```

---

# Show Domains

```bash
show domains
```

---

# Show Hosts

```bash
show hosts
```

---

# Delete Data

```bash
db delete hosts
```

---

## Screenshot

![Database Commands](images/recon-ng/database.png)

---

# Marketplace

Marketplace contains Recon-ng modules.

---

# Search Modules

```bash
marketplace search
```

---

# Search Specific Module

```bash
marketplace search dns
```

---

# Install All Modules

```bash
marketplace install all
```

---

# Install Single Module

```bash
marketplace install recon/domains-hosts/hackertarget
```

---

# Remove Module

```bash
marketplace remove recon/domains-hosts/hackertarget
```

---

## Screenshot

![Marketplace Modules](images/recon-ng/marketplace.png)

---

# Modules

## What are Modules?

Modules automate reconnaissance tasks.

Examples:
- Subdomain enumeration
- Whois lookup
- Contact harvesting
- Technology detection

---

# View Installed Modules

```bash
modules search
```

---

# Load Module

```bash
modules load recon/domains-hosts/brute_hosts
```

---

# Module Information

```bash
info
```

Shows:
- Description
- Author
- Required options
- API dependency

---

# Show Options

```bash
show options
```

---

# Set Target

```bash
options set SOURCE example.com
```

---

# Unset Option

```bash
options unset SOURCE
```

---

# Run Module

```bash
run
```

---

## Screenshot

![Loading Modules](images/recon-ng/modules.png)

---

# Important Recon Modules

# 1. brute_hosts

Used for subdomain enumeration.

---

## Load Module

```bash
modules load recon/domains-hosts/brute_hosts
```

---

## Set Target

```bash
options set SOURCE example.com
```

---

## Run

```bash
run
```

---

## Purpose

Finds:
- admin.example.com
- mail.example.com
- vpn.example.com

---

## Screenshot

![Brute Hosts Module](images/recon-ng/brute-hosts.png)

---

# 2. Bing Domain Search

Uses search engines to discover hosts.

---

## Load Module

```bash
modules load recon/domains-hosts/bing_domain_web
```

---

## Set Target

```bash
options set SOURCE example.com
```

---

## Run

```bash
run
```

---

## Screenshot

![Bing Domain Search](images/recon-ng/bing-domain.png)

---

# 3. HackerTarget Module

Used for retrieving:
- Subdomains
- IP addresses

---

## Load Module

```bash
modules load recon/domains-hosts/hackertarget
```

---

## Set Target

```bash
options set SOURCE example.com
```

---

## Run

```bash
run
```

---

## Screenshot

![Hackertarget Module](images/recon-ng/hackertarget.png)

---

# 4. Whois Contacts

Used to gather:
- Whois contacts
- Emails
- Domain owner information

---

## Load Module

```bash
modules load recon/domains-contacts/whois_pocs
```

---

## Set Target

```bash
options set SOURCE example.com
```

---

## Run

```bash
run
```

---

## Screenshot

![Whois Contacts Module](images/recon-ng/whois-pocs.png)

---

# 5. Reverse Resolve

Converts:

```text
IP → Hostname
```

---

## Load Module

```bash
modules load recon/hosts-hosts/reverse_resolve
```

---

## Run

```bash
run
```

---

## Screenshot

![Reverse Resolve Module](images/recon-ng/reverse-resolve.png)

---

# API Keys

Some modules require APIs.

Examples:
- Shodan
- BuiltWith
- WhoisXML
- GitHub

---

# View APIs

```bash
keys list
```

---

# Add API Key

```bash
keys add shodan_api YOUR_API_KEY
```

---

# Remove API Key

```bash
keys remove shodan_api
```

---

## Screenshot

![API Keys](images/recon-ng/api-keys.png)

---

# Shodan Module Example

## Load Module

```bash
modules load recon/domains-hosts/shodan_hostname
```

---

## Set Target

```bash
options set SOURCE example.com
```

---

## Run

```bash
run
```

---

## Screenshot

![Shodan Module](images/recon-ng/shodan-module.png)

---

# Reporting

Recon-ng supports automatic report generation.

---

# HTML Report

## Load Module

```bash
modules load reporting/html
```

---

## Set Filename

```bash
options set FILENAME /home/kali/Desktop/report.html
```

---

## Set Creator

```bash
options set CREATOR Jadhav
```

---

## Run

```bash
run
```

---

## Screenshot

![HTML Report Generation](images/recon-ng/reporting.png)

---

# Export Results

## CSV Export

```bash
export csv /home/kali/Desktop/results.csv
```

---

## Screenshot

![Export Results](images/recon-ng/export-results.png)

---

# Real Practical Workflow

## Step 1 — Start Recon-ng

```bash
recon-ng
```

---

## Step 2 — Create Workspace

```bash
workspaces create bugbounty
```

---

## Step 3 — Insert Domain

```bash
db insert domains
```

Enter:

```text
example.com
```

---

## Step 4 — Install Modules

```bash
marketplace install all
```

---

## Step 5 — Enumerate Subdomains

```bash
modules load recon/domains-hosts/brute_hosts

options set SOURCE example.com

run
```

---

## Step 6 — Search Engine Discovery

```bash
modules load recon/domains-hosts/bing_domain_web

options set SOURCE example.com

run
```

---

## Step 7 — Gather Whois Information

```bash
modules load recon/domains-contacts/whois_pocs

options set SOURCE example.com

run
```

---

## Step 8 — View Results

```bash
show hosts

show contacts

show domains
```

---

## Step 9 — Generate Report

```bash
modules load reporting/html

options set FILENAME /home/kali/Desktop/report.html

run
```

---

# Common Commands Cheat Sheet

```bash
recon-ng

help

dashboard

marketplace search

marketplace install all

modules search

modules load recon/domains-hosts/brute_hosts

info

show options

options set SOURCE example.com

run

show hosts

show contacts

show domains

keys list

keys add shodan_api API_KEY

modules load reporting/html

run
```

---

# Common Mistakes

## Forgetting Workspace

Always create workspace before starting.

---

## Forgetting SOURCE

Most modules require:

```bash
options set SOURCE target.com
```

---

## Forgetting run

Always execute:

```bash
run
```

---

## Missing API Keys

Some modules fail without APIs.

---

# Recon-ng vs Other Tools

| Tool | Purpose |
|---|---|
| Recon-ng | OSINT automation |
| Maltego | Visual OSINT |
| theHarvester | Email harvesting |
| SpiderFoot | Automated recon |
| Amass | Subdomain enumeration |
| Nmap | Port scanning |
| Metasploit | Exploitation |

---

# Final Understanding

Recon-ng is useful for:

- Footprinting
- OSINT
- Reconnaissance
- Subdomain enumeration
- Contact harvesting
- Automated intelligence gathering

---

# References

- Official Recon-ng GitHub
- CEH Labs
- Recon-ng OSINT articles

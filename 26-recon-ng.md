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
workspaces create test_lab
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
iiitkottayam.ac.in
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


---

# Important Recon Modules

# 1. brute_hosts Module

The `brute_hosts` module is used for subdomain enumeration.

It helps discover hidden or common subdomains related to a target domain.

---

# Objective

Target Domain:

```text
iiitkottayam.ac.in
```

Goal:
- Discover subdomains
- Identify exposed hosts
- Expand attack surface

---

# Step 1 — Start Recon-ng

Run:

```bash
recon-ng
```

---

# Step 2 — Create Workspace

Workspaces help organize reconnaissance projects.

---

```bash
workspaces create iiitk
```

---

## Verify Workspace

```bash
workspaces list
```

---


# Step 3 — Insert Target Domain

Add the target domain into the Recon-ng database.

---
```bash
db insert domains
```

---

## Enter Domain

```text
iiitkottayam.ac.in
```

---

## Verify Domain

```bash
show domains
```
---

# Step 4 — Search Modules

Search available Recon-ng modules.

---

## Command

```bash
modules search brute
```
---

# Step 5 — Load brute_hosts Module

Load the subdomain enumeration module.

---

```bash
modules load recon/domains-hosts/brute_hosts
```

---
# Step 6 — View Module Information

Display module information and required options.

---

## Command

```bash
info
```

---

## Expected Information

- Module description
- Required options
- Author
- Source requirement

---

# Step 7 — Show Module Options

Display configurable options.

---

## Command

```bash
show options
```

---

# Step 8 — Set Target Domain

Set the target domain for enumeration.

---

```bash
options set SOURCE iiitkottayam.ac.in
```

---

## Verify Options

```bash
show options
```
---

# Step 9 — Run Module

Execute the brute_hosts module.

---

```bash
run
```

---

## Purpose

The module attempts to discover:
- mail servers
- VPN portals
- admin panels
- hidden subdomains

---

## Screenshot

![Run brute_hosts](images/recon-ng/brute-hosts-run.png)

---

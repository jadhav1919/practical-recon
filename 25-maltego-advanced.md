# Maltego – Complete Beginner to Advanced Guide for Footprinting & OSINT

Maltego is one of the most powerful OSINT and reconnaissance tools used in cybersecurity. It helps investigators visualize relationships between domains, IPs, people, emails, organizations, infrastructure, and social media accounts using graphical analysis.


---

## 1. Overview

**Maltego** is an automated OSINT (Open Source Intelligence) tool used to gather and visualize information about a target.

Unlike normal tools that show only text results, Maltego creates:

- relationship graphs
- infrastructure maps
- connection analysis

It is mainly used during:

- Footprinting
- Reconnaissance
- Threat Intelligence
- OSINT Investigations
- Social Media Investigations


---
## 2. Official Website
https://www.maltego.com

---

## 3. Why Security Researchers Use Maltego

Maltego helps researchers:

- Discover subdomains
- Gather email addresses
- Find DNS records
- Analyze internet infrastructure
- Investigate organizations
- Map relationships
- Track digital footprints
- Visualize OSINT data
- Automate reconnaissance


---

## 4. Types of Reconnaissance in Maltego

According to Maltego documentation and OSINT usage, Maltego supports two main reconnaissance types:

### A. Infrastructure Reconnaissance

Focuses on:

- domains
- DNS
- subdomains
- IP addresses
- mail servers
- hosting infrastructure

### B. Personal Reconnaissance

Focuses on:

- people
- phone numbers
- social media
- email addresses
- organizations


---

## 5. Maltego Versions

| Version | Description |
|---------|-------------|
| Maltego CE | Free Community Edition |
| Maltego Classic | Professional Edition |
| Maltego XL | Large-scale investigations |
| CaseFile | Offline graph analysis |

**For learning: Use Maltego CE**


---

## 6. Important Concepts

Before using Maltego, understand these two concepts.

---

## A. What is an Entity?

Everything in Maltego is called an **Entity**.

Examples:

- Domain
- Email
- Website
- Person
- Company
- Phone Number
- IP Address

You drag entities into the graph workspace.

---

## B. What is a Transform?

**Transforms** are automated actions.

Example:
Domain → Find Subdomains
Domain → Find DNS Records
Email → Find Social Accounts


Transforms automatically gather information.

---

## 7. Information That Can Be Gathered

| Information | Example |
|-------------|---------|
| Domains | microsoft.com |
| Emails | admin@microsoft.com |
| IP Addresses | 13.x.x.x |
| DNS Records | MX, NS, TXT |
| Subdomains | login.microsoft.com |
| WHOIS Data | Domain ownership |
| Organizations | Microsoft |
| Social Media | LinkedIn accounts |
| Phone Numbers | Public contacts |


---

## 8. Installation

### Kali Linux Installation

Maltego is usually pre-installed in Kali Linux.

Check:

```bash
maltego
```
If not installed:

```bash
sudo apt update
sudo apt install maltego
```
Windows/Linux/Mac Download
- Download from:  https://www.maltego.com/downloads
  ---
![Maltego Installation](images/maltego/maltego-install.png)
## 9. Starting Maltego
Run:

``` bash
maltego
```
OR open from:

Applications → Information Gathering → Maltego
---
# Maltego Installation & Setup Guide

## 1. Run Installer

![Maltego Startup](images/maltego/maltego-startup.png)

> Click **"Next"** to continue.

---

## 2. Activation Method

![Activation Option](images/maltego/activation-option1.png)

- Select **"Default Online Activation"**
- Click **"Next"**

---

## 3. License Agreement

![License Agreement](images/maltego/license-agreement.png)

- Accept the terms and conditions
- Click **"Next"**

---

## 4. Login to Maltego

![Login Prompt](images/maltego/login-prompt.png)

- Click **"Browser Login"**

---

## 5. Browser Login Page

![Browser Login](images/maltego/browser-login-page.png)

- Click **"Create ID"** if you do not already have an account

---

## 6. Account Creation Form

![Create Account](images/maltego/create-account-form.png)

- Enter your email address
- Enter your first and last name
- Click **"Continue"**

---

## 7. Email Verification / Password Setup

![Email Verification](images/maltego/email-verification.png)

- Create a strong password
- Click **"Continue"**

---

## 8. OTP Verification

![OTP Verification](images/maltego/otp-verification.png)

- Check your email for the OTP code
- Enter the verification code
- Click **"Verify"**

---

## 9. Log in to Maltego

![Login](images/maltego/login1.png)

- Log in using your registered email and password

---

## 10. Country and Phone Number

![Country Phone](images/maltego/country-phone1.png)

- Select your country
- Enter your phone number
- Click **"Continue"**

---

## 11. Additional Questions

![Additional Questions](images/maltego/additional1.png)

- Fill in the optional questions as preferred
- These questions do not affect activation
- Submit the form
- Close the browser and return to Maltego

---

## 12. Configuration Successful

![Configuration](images/maltego/configuration.png)

- This confirms that browser login was successful
- Click **"Next"**

---

## 13. Maltego ID Activation

![Activation](images/maltego/activatio1.png)

- Click **"Next"**

---

## 14. Select Data Sources

![Data Sources](images/maltego/data.png)

- The Utilities package is already selected by default
- Click **"Next"**

---

## 15. Download Data Sources

![Download Sources](images/maltego/source.png)

- This installs the basic transforms required for investigations
- Click **"Next"**

---

## 16. Data Sources Terms & Conditions

![Terms and Conditions](images/maltego/tc.png)

- Accept the terms and conditions
- Click **"Next"**

---

## 17. Install Data Sources

![Install Data Sources](images/maltego/DS.png)

- Wait for installation to complete
- Click **"Next"**

---

## 18. Help Improve Maltego

![Help Improve Maltego](images/maltego/mg.png)

- Choose your preferred option
- Click **"Next"**

---

## 19. Web Browser Options

![Browser Options](images/maltego/Bo.png)

- Select your preferred web browser
- Click **"Next"**

---

## 20. Privacy Mode

![Privacy Mode](images/maltego/PM1.png)

- Select **"Normal Mode"**

> **Why Normal Mode?**  
> Stealth mode hides IP exposure but may limit some investigations.  
> Normal mode provides full functionality.

- Click **"Next"**

---

## 21. Finish Installation

![Finish Installation](images/maltego/FI.png)

- Click **"Finish"**
- Maltego opens with a blank graph workspace

---

## 22. Privacy Policy Notice

![Privacy Policy](images/maltego/pp.png)

- Click **"Acknowledge"**

---

## 23. Maltego Interface

![Maltego Interface](images/maltego/MI.png)

### Interface Overview

- **Left Panel:** Entity Palette
- Used to drag and drop entities into the graph workspace
- Ready to start investigations


## 10. Understanding the Interface
#### Section	Purpose
- Entity Palette	Contains entities
- Graph Area	Workspace
- Transform Menu	Runs transforms
- Output Window	Shows results
- Property Panel	Entity information

## 12. Basic Workflow of Maltego
This is the MOST IMPORTANT section.

Maltego works like this:

Add Entity
      ↓
Run Transform
      ↓
Get Related Information
      ↓
Run More Transforms
      ↓
Build Intelligence Graph

## 13. Creating Your First Investigation
### Step 1 – Create New Graph
Click: New Graph

This creates a blank workspace.

### Step 2 – Add Domain Entity
From left side: Entity Palette

Search: Domain

Drag it into graph workspace.

### Step 3 – Set Target Domain
Double click entity.

Replace paterva.com with:

microsoft.com
OR

tesla.com
### Step 4 – Run Transforms
Right click: Domain Entity

Select: Run All Transforms

OR choose specific transforms.

### Step 5 – Wait for Results
Maltego now gathers:

- DNS records

- emails

- IP addresses

- subdomains

- organizations

- servers

- Graph expands automatically.

![First Investigation](images/maltego/maltego-first-investigation.png)

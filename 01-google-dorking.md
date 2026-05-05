# Footprinting Using Search Engines (Google Dorking)

## 1. Overview

Search engines are one of the easiest ways to collect public information about a target organization.

This process is called **Footprinting through Search Engines**.

It means using search engines like Google to gather information such as:

- Company websites
- Employee details
- Login pages
- Public documents
- Contact information
- Technology used by the company
- Hidden or forgotten pages
- Exposed files

This helps a security professional understand what information is publicly visible about a target.

![Search Engine Footprinting](images/google-dorking/search-engine-footprinting.png)

---

## 2. What is Google Hacking / Google Dorking?

**Google Hacking** (also called **Google Dorking**) means using advanced Google search operators to find specific information more accurately.

Instead of doing a normal search, special operators are used to:

- filter results
- narrow results
- find exact information
- locate exposed data
- identify publicly visible sensitive resources

It is commonly used in:

- OSINT
- Footprinting
- Reconnaissance
- Security assessments
- Exposure checking

---

## 3. Why It Is Used

Google Dorking helps security professionals find:

- Publicly exposed documents
- Login portals
- Open directories
- Misconfigured servers
- Cached pages
- Old/deleted indexed pages
- Public employee information
- Technology details

This is useful for:

- identifying exposure
- checking public risk
- understanding attack surface
- security auditing

---

## 4. Basic Syntax

Google advanced search uses this format: operator:search_term


**Rule:**  
Do not put spaces between the operator and the search term.

| ✅ Correct | ❌ Wrong |
|-----------|----------|
| `site:example.com` | `site: example.com` |
| `inurl:login` | `inurl: login` |
| `filetype:pdf` | `filetype: pdf` |

---

## 5. Common Google Search Operators

### 5.1 `site:`
Search only inside a specific website or domain.

| Item | Value |
|------|-------|
| **Syntax** | `site:domain` |
| **Example** | `site:microsoft.com` |
| **Use** | Shows only pages from Microsoft's website |
| **Security Use** | Useful for checking what pages of a target are indexed publicly |

![Site Operator Example](images/google-dorking/site-operator.png)

---

### 5.2 `allinurl:`
Shows pages where all words appear in the URL.

| Item | Value |
|------|-------|
| **Syntax** | `allinurl:word1 word2` |
| **Example** | `allinurl:google career` |
| **Use** | Shows pages that contain both words in the URL |
| **Security Use** | Useful for finding admin panels, portals, dashboards |

![Allinurl Operator Example](images/google-dorking/allinurl-operator.png)

---

### 5.3 `inurl:`
Shows pages where a specific word appears in the URL.

| Item | Value |
|------|-------|
| **Syntax** | `inurl:keyword` |
| **Example** | `inurl:login` |
| **Use** | Finds pages with "login" in the URL |
| **Security Use** | Useful for finding login portals and admin pages |

![Inurl Operator Example](images/google-dorking/inurl-operator.png)

---

### 5.4 `intext:`
Searches for a word inside the page content.

| Item | Value |
|------|-------|
| **Syntax** | `intext:keyword` |
| **Example** | `intext:"vpn configuration"` |
| **Use** | Finds pages containing the exact phrase |
| **Security Use** | Useful for finding exposed configuration content |

![Intext Operator Example](images/google-dorking/intext-operator.png)

---

### 5.5 `allintitle:`
Shows pages where all words appear in the page title.

| Item | Value |
|------|-------|
| **Syntax** | `allintitle:word1 word2` |
| **Example** | `allintitle:detect malware` |
| **Use** | Shows pages with both words in title |
| **Security Use** | Useful for finding targeted documents or security-related pages |

![Allintitle Operator Example](images/google-dorking/allintitle-operator.png)

---

### 5.6 `intitle:`
Searches pages where a word appears in the title.

| Item | Value |
|------|-------|
| **Syntax** | `intitle:keyword` |
| **Example** | `intitle:login` |
| **Use** | Finds pages with "login" in title |
| **Security Use** | Useful for finding login portals and admin dashboards |

![Intitle Operator Example](images/google-dorking/intitle-operator.png)

---

### 5.7 `inanchor:`
Finds pages where the keyword appears in link anchor text.

| Item | Value |
|------|-------|
| **Syntax** | `inanchor:keyword` |
| **Example** | `inanchor:Norton` |
| **Use** | Finds pages linked using that word |
| **Security Use** | Useful for identifying linked references and related pages |

![Inanchor Operator Example](images/google-dorking/inanchor-operator.png)

---

### 5.8 `allinanchor:`
Shows pages where all words appear in anchor text.

| Item | Value |
|------|-------|
| **Syntax** | `allinanchor:word1 word2` |
| **Example** | `allinanchor:best cloud service provider` |
| **Use** | Finds pages where all terms appear in anchor text |
| **Security Use** | Useful for finding highly referenced resources |

![Allinanchor Operator Example](images/google-dorking/allinanchor-operator.png)

---

### 5.9 `cache:`
Shows Google's cached copy of a page.

| Item | Value |
|------|-------|
| **Syntax** | `cache:url` |
| **Example** | `cache:example.com` |
| **Use** | Displays stored Google copy of page |
| **Security Use** | Useful for viewing removed or changed content |

![Cache Operator Example](images/google-dorking/cache-operator.png)

---

### 5.10 `link:`
Shows pages linking to a specific page.

| Item | Value |
|------|-------|
| **Syntax** | `link:url` |
| **Example** | `link:example.com` |
| **Use** | Shows backlinks to a page |
| **Security Use** | Useful for identifying linked resources |

![Link Operator Example](images/google-dorking/link-operator.png)

---

### 5.11 `related:`
Finds websites similar to the target site.

| Item | Value |
|------|-------|
| **Syntax** | `related:url` |
| **Example** | `related:microsoft.com` |
| **Use** | Shows similar websites |
| **Security Use** | Useful for identifying related assets or competitors |

![Related Operator Example](images/google-dorking/related-operator.png)

---

### 5.12 `info:`
Shows information Google knows about a page.

| Item | Value |
|------|-------|
| **Syntax** | `info:url` |
| **Example** | `info:example.com` |
| **Use** | Shows indexed info about the page |
| **Security Use** | Useful for basic search engine metadata |

![Info Operator Example](images/google-dorking/info-operator.png)

---

### 5.13 `filetype:`
Finds files of a specific type.

| Item | Value |
|------|-------|
| **Syntax** | `filetype:extension keyword` |
| **Example** | `filetype:pdf cybersecurity` |
| **Use** | Finds PDF files related to cybersecurity |
| **Security Use** | Useful for finding public documents, reports, manuals |

![Filetype Operator Example](images/google-dorking/filetype-operator.png)

---

### 5.14 `source:`
Searches news from a specific source.

| Item | Value |
|------|-------|
| **Syntax** | `source:name` |
| **Example** | `source:"Hacker News" malware` |
| **Use** | Shows malware-related articles from Hacker News |

![Source Operator Example](images/google-dorking/source-operator.png)

---

### 5.15 `before:`
Finds results published before a specific date.

| Item | Value |
|------|-------|
| **Syntax** | `keyword before:YYYY-MM-DD` |
| **Example** | `ransomware before:2020-06-29` |
| **Use** | Shows older indexed content |

![Before Operator Example](images/google-dorking/before-operator.png)

---

### 5.16 `after:`
Finds results published after a specific date.

| Item | Value |
|------|-------|
| **Syntax** | `keyword after:YYYY-MM-DD` |
| **Example** | `artificial intelligence after:2023-01-01` |
| **Use** | Shows newer content only |

![After Operator Example](images/google-dorking/after-operator.png)

---

## 6. What Can Be Found Using Google Dorking

Google Dorking can help identify publicly visible:

| Category | Examples |
|----------|----------|
| Login pages | admin login, user portal |
| Admin panels | dashboard, control panel |
| Open directories | index of /, folder listing |
| Public documents | PDFs, DOCs, XLS files |
| Error messages | debug info, stack traces |
| Old cached pages | historical data |
| Technology details | server versions, CMS info |
| Public configs | config files, backups |
| Employee details | names, emails, roles |
| Public reports | annual reports, audits |
| Software version details | version.txt, changelog |
| Hidden indexed pages | forgotten pages |
| Misconfigured resources | open S3 buckets, exposed APIs |

![Google Dorking Results](images/google-dorking/dorking-results.png)

---


# 7. Advanced Multi-Operator Examples

Combining multiple operators makes Google Dorking much more effective. Here are real examples:

## Example 1: Find Login Portals
intitle:"login" OR intitle:"sign in" inurl:login site:example.com

Use case: Find all login pages on a specific target website.

![Login Portal Example](images/google-dorking/login-portal.png)

## Example 2: Find Exposed Documents
site:example.com filetype:pdf intitle:"confidential" OR intitle:"internal"

Use case: Identify publicly available confidential documents.

![Exposed Documents Example](images/google-dorking/exposed-docs.png)

## Example 3: Find Admin Panels
intitle:"admin panel" OR intitle:"administrator" inurl:admin filetype:php

Use case: Locate admin dashboard login pages.

![Admin Panel Example](images/google-dorking/admin-panel.png)

## Example 4: Find Database Exports
filetype:sql intitle:"dump" OR intitle:"backup" intext:"INSERT INTO"

Use case: Find exposed SQL database backups.

![Database Exports Example](images/google-dorking/database-exports.png)

## Example 5: Find Configuration Files
filetype:env "DB_PASSWORD" OR "SECRET_KEY" intext:"localhost"

Use case: Identify exposed environment config files with credentials.

![Config Files Example](images/google-dorking/config-files.png)

## Example 6: Find Open Directories
intitle:"index of" AND (inurl:/backup OR inurl:/config OR inurl:/database)

Use case: Locate open directory listings containing sensitive folders.

![Open Directories Example](images/google-dorking/open-directories.png)

## Example 7: Find Employee Information
site:company.com filetype:xlsx intitle:"employee" OR intitle:"salary"

Use case: Find employee spreadsheets or salary data.

![Employee Info Example](images/google-dorking/employee-info.png)

## Example 8: Find Vulnerable Parameters
inurl:?id= intitle:"error" OR intext:"warning" filetype:php

Use case: Identify PHP pages with ID parameters showing errors (possible SQLi).

![Vulnerable Parameters Example](images/google-dorking/vulnerable-params.png)

## Example 9: Find WordPress Vulnerabilities
inurl:/wp-content intext:"warning" OR intext:"error" filetype:log

Use case: Find WordPress error logs exposed.

![WordPress Vulnerabilities Example](images/google-dorking/wordpress-vulns.png)

## Example 10: Find API Keys
filetype:json intext:"api_key" OR intext:"API_KEY" intitle:"config"

Use case: Locate JSON config files containing API keys.

![API Keys Example](images/google-dorking/api-keys.png)

## Example 11: Find CV/Resume Exposure
filetype:pdf intitle:"resume" OR intitle:"CV" intext:"@gmail.com" AND "phone"

Use case: Find public resumes with personal contact info.

![CV Exposure Example](images/google-dorking/cv-exposure.png)

## Example 12: Find Network Device Configs
intitle:"router" OR intitle:"switch" inurl:config filetype:cfg

Use case: Find router or switch configuration files.

![Network Configs Example](images/google-dorking/network-configs.png)

## Example 13: Find Backup Files
filetype:bak OR filetype:old OR filetype:backup intitle:"backup" inurl:backup

Use case: Find old backup files exposed.

![Backup Files Example](images/google-dorking/backup-files.png)

## Example 14: Find Email Lists
filetype:xlsx intitle:"email" OR intitle:"mailing" intext:"@example.com"

Use case: Find email distribution lists.

![Email Lists Example](images/google-dorking/email-lists.png)

## Example 15: Find Security Audit Reports
filetype:pdf intitle:"security audit" OR intitle:"penetration test"

Use case: Find public security assessment reports.

![Audit Reports Example](images/google-dorking/audit-reports.png)

## Example 16: Find phpMyAdmin Panels
intitle:"phpMyAdmin" AND (inurl:main.php OR inurl:index.php)

Use case: Find exposed phpMyAdmin database management panels.

![phpMyAdmin Example](images/google-dorking/phpmyadmin.png)

## Example 17: Find Log Files
filetype:log intitle:"error log" OR intext:"stack trace" inurl:logs

Use case: Find server error logs with debugging info.

![Log Files Example](images/google-dorking/log-files.png)

## Example 18: Find Webcam Streams
intitle:"Live View" AND (inurl:axis-cgi OR inurl:view/view.shtml)

Use case: Find unsecured webcam streams.

![Webcam Streams Example](images/google-dorking/webcam-streams.png)

## Example 19: Find IoT Device Panels
intitle:"system administration" inurl:8080 OR inurl:8443

Use case: Find IoT or router admin panels on non-standard ports.

![IoT Panels Example](images/google-dorking/iot-panels.png)

## Example 20: Find Git Exposed Folders
intitle:"index of" ".git" OR inurl:/.git/config

Use case: Find exposed Git repositories.

![Git Exposed Example](images/google-dorking/git-exposed.png)

```markdown

# OWASP ZAP Web Application Security Lab

## Project Overview
This repository documents a hands-on web application security assessment performed using **OWASP ZAP**.  
The assessment focused on identifying common web application vulnerabilities through an **automated scan**.

The exercise demonstrates:
- Use of OWASP ZAP automated scanning
- Analysis of discovered security alerts
- Basic understanding of web application vulnerabilities

---

## Target Application
- **Application:** Damn Vulnerable Web Application (DVWA)
- **Access Method:** HTTP
- **Target URL:** `http://172.17.0.2/dvwa/login.php`
- **Testing Scope:** Local lab environment

---

## Tool Used
- **OWASP ZAP v2.13.0**

---

## Scan Methodology

### Automated Scan
The OWASP ZAP **Automated Scan** feature was used with the following configuration:
- Traditional spider enabled
- Passive scanning enabled by default
- Active scanning enabled

The scan was initiated by entering the target URL and launching the automated attack process.

---

## Scan Results Summary

OWASP ZAP identified multiple security alerts during the scan, categorized by risk level.

### Alerts Observed:
- Remote Code Execution (CVE-2012-1823)
- Source Code Disclosure (CVE-2012-1823)
- Absence of Anti-CSRF Tokens
- Content Security Policy (CSP) Header Not Set
- Hidden File Found
- Missing Anti-clickjacking Header

---

## Example High-Risk Finding

### Remote Code Execution – CVE-2012-1823
- **Risk Level:** High
- **Confidence:** Medium
- **Affected URL:** `/dvwa/index.php`
- **Description:**
  The application is vulnerable to remote code execution due to improper handling of PHP CGI parameters.
- **Evidence:**
  Injected PHP payload was reflected in the HTTP response, confirming execution.

Screenshots of the alert and evidence are included in the `screenshots/` directory.

---

## Remediation
General remediation guidance is provided based on the identified alerts, including:
- Secure PHP configuration
- Input validation
- Use of security headers
- Implementation of CSRF protection mechanisms

Detailed notes are available in the `remediation/` directory.

---

## References
- OWASP ZAP
- OWASP Web Security Testing Guide (WSTG)

# Vulnerability Assessment Report for a Live Website

## Project Overview
This repository contains a professional Vulnerability Assessment Report evaluating the web server response headers of the target application against industry-standard security baselines. Implementing proper HTTP security headers is a critical defense-in-depth measure to mitigate client-side risks such as Cross-Site Scripting (XSS), Clickjacking, side-channel leaks, and data sniffing.

- **Target Scope:** OWASP Juice Shop Web Application
- **Target URL:** https://owasp.org/www-project-juice-shop/
---

## Security & Analysis Tools Used
To align with professional security assessment standards, the methodology combined both automated reconnaissance baselines and precise manual verification:

1. **Browser DevTools (Network Architecture Subsystem)**
   - **Purpose:** Used as the primary tool for definitive verification of server-side response headers.
   - **Output:** Captured raw HTTP response parameters live during page initialization. This served as the definitive "Proof of Absence" for the missing security directives (HSTS, CSP, CORP, COOP, Permissions-Policy).

2. **OWASP ZAP (Passive Scan Mode)**
   - **Purpose:** Utilized to analyze the application's traffic passively without injecting attacks or altering data.
   - **Output:** Flagged missing defense-in-depth headers and anti-clickjacking parameters (X-Frame-Options, X-Content-Type-Options), which were then manually isolated and cross-verified via the Browser DevTools console.

3. **Nmap (Port & Exposure Analysis)**
   - **Purpose:** Conducted basic infrastructure exposure checks to ensure port bindings over standard web interfaces (Port 80/443) were properly aligned before diving into application-layer header analysis.

---

## Key Security Vulnerabilities Documented
* **Vulnerability #1:** Missing Strict-Transport-Security (HSTS) Header (Medium Risk)
* **Vulnerability #2:** Missing X-Content-Type-Options Header (Low to Medium Risk)
* **Vulnerability #3:** Missing X-Frame-Options Header (Low Risk)
* **Vulnerability #4:** Missing Content-Security-Policy (CSP) Directives (Medium Risk)
* **Vulnerability #5:** Missing Cross-Origin Resource Policy (CORP) Header (Low to Medium Risk)
* **Vulnerability #6:** Missing Cross-Origin Opener Policy (COOP) Header (Low to Medium Risk)
* **Vulnerability #7:** Missing Permissions-Policy Header (Low Risk)
* **Vulnerability #8:** Server Information Disclosure Guardrails (Informational)

---

##  Repository Deliverables
* `VULNERABILITY ASSESSMENT REPORT.pdf` - The client-ready audit presentation including proof-of-concept visual evidence matching response headers against hardening baselines.

[kali_lab_files_week 2.zip](https://github.com/user-attachments/files/34630745/kali_lab_files_week.2.zip)

# Week-2-Cybersecurity-Internship-Footprinting-Reconnaissance-Network-Scanning
Week 2 Cybersecurity Internship Projects – Footprinting, Reconnaissance and Network Scanning.

# Footprinting and Reconnaissance Report

## Target
- Domain: `networkwalks.com`
- Date of assessment: 2026-11-10
- Scope: Passive footprinting and reconnaissance based on publicly available data

## Executive Summary
The target domain `networkwalks.com` resolves to the public IP address `192.232.216.135` and is hosting a WordPress-based website. The site redirects from HTTP to HTTPS, uses Apache as its web server, and appears to be protected by a Web Application Firewall (WAF), specifically ModSecurity from SpiderLabs. The domain is registered with GoDaddy and has its registrant information privacy-protected. Based on the available evidence, the target appears to be a public-facing educational website or academy platform.

## 1. Domain Registration Details
WHOIS data revealed the following:
- Domain name: `networkwalks.com`
- Registrar: GoDaddy.com, LLC
- Creation date: 2019-11-06
- Registration expiration date: 2027-11-06
- Name servers:
  - `NS6135.HOSTGATOR.COM`
  - `NS6136.HOSTGATOR.COM`
  - `NS29.DOMAINCONTROL.COM`
  - `NS30.DOMAINCONTROL.COM`
- Registrant details were masked through privacy protection (Domains By Proxy), which is common for public websites.

### Observations
- The domain is active and not expired.
- The domain is managed through a major registrar and a standard hosting infrastructure.
- The ownership information is intentionally hidden, which is a common operational practice for commercial domains.

## 2. DNS and Host Resolution
The NSLOOKUP output showed:
- Server: `8.8.8.8`
- Resolved host: `networkwalks.com`
- IP address: `192.232.216.135`

### Findings
- The target resolves successfully in DNS.
- The domain maps to a public IPv4 address, confirming it is live and reachable.
- A single A record indicates a fairly straightforward network footprint, likely hosted on a conventional server or shared hosting environment.

## 3. HTTP and Web Server Analysis
The HTTP header data revealed the following:
- HTTP request to `http://networkwalks.com` returned `301 Moved Permanently`
- Redirect target: `https://networkwalks.com/`
- HTTPS endpoint returned `200 OK`
- Server banner: `Apache`
- Content-Type: `text/html; charset=UTF-8`
- Cookie observed: `__wpdm_client`
- Other headers included `permissions-policy`, `referrer-policy`, `link`, and `x-nginx-cache`

### Findings
- The site enforces HTTPS redirection, which is a positive security practice.
- The web server is Apache, which is commonly used in public hosting environments.
- The presence of the `__wpdm_client` cookie suggests a plugin or download-related feature in use.

## 4. Technology Stack Identification
WhatWeb reported the following technologies:
- Platform: WordPress 7.1.4
- Download manager: WordPress Download Manager 3.3.76
- Front-end technologies:
  - Bootstrap 7.1.4
  - jQuery 3.7.1
- Site title: `Networkwalks Academy`
- Country: United States (US)
- Detected metadata: Open Graph, HTML5, Google Tag Manager

### Interpretation
- The site is built on WordPress, which makes it susceptible to plugin and CMS-related vulnerabilities if not maintained.
- The use of Bootstrap and jQuery indicates a modern front-end interface.
- The title “Networkwalks Academy” suggests the site is an educational or learning platform.

## 5. WAF Fingerprinting
The WAF detection tool reported:
- WAF identified: `ModSecurity (SpiderLabs)`
- Result: The target is behind a ModSecurity WAF.

### Significance
- This means the website is actively protected at the application layer.
- Basic probing and attack attempts may be filtered or blocked.
- WAF presence indicates the infrastructure is designed with some level of security hardening.

## 6. Security Posture Summary
From the collected evidence, the target demonstrates several foundational security controls:
- HTTPS enforcement
- Apache web server in a public environment
- WAF protection via ModSecurity
- Modern front-end stack

However, the following risks should be considered:
- WordPress and plugin versions may need ongoing patching.
- Download manager plugins are often a common target if not updated.
- Public-facing applications should regularly be checked for outdated components and weak configurations.

## 7. Final Assessment
`networkwalks.com` is an active website that appears to be a WordPress-based educational portal. It is publicly reachable, uses Apache, redirects to HTTPS, and is protected by the ModSecurity WAF. While the site shows standard security practices, it should still be evaluated regularly for WordPress plugin security, server hardening, and vulnerability management.

## 8. Conclusion
This footprinting exercise successfully identified the target’s public exposure, technologies in use, DNS resolution, hosting setup, and security controls. These findings align with a typical reconnaissance workflow used during penetration testing and cybersecurity analysis.

---

This report was prepared from public reconnaissance data collected for the target `networkwalks.com` as part of the Week 2 cybersecurity internship task.

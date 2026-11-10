# Week 2 Cybersecurity Internship: Footprinting, Reconnaissance and Network Scanning

## Project Overview

This repository documents a practical cybersecurity internship exercise focused on passive footprinting and reconnaissance. The project was designed to explore how public information about a target can be gathered using legitimate, non-invasive reconnaissance techniques. The assessment emphasizes structured data collection, evidence documentation, and interpretation of publicly available network and web metadata.

The target of this exercise was `networkwalks.com`, a public-facing website. Using information gathered from WHOIS records, DNS queries, HTTP headers, WAF detection, and technology fingerprinting, the exercise demonstrates how security investigators can build a profile of an external target without exploiting vulnerabilities or performing intrusive testing.

This report presents the methodology, evidence, and conclusions collected during the assessment. The repository also includes supporting screenshots and output files from each stage of the analysis.

## Objectives

The primary objectives of this internship task were to:

- identify the target domain and its public exposure;
- gather domain registration and DNS information;
- analyze HTTP and web server behavior;
- detect technologies used by the target website;
- evaluate the presence of protective infrastructure such as a WAF;
- document findings in a professional and academically structured manner.

## Scope and Methodology

The assessment was limited to passive reconnaissance and public information gathering. It did not include exploitation, credential attacks, unauthorized access, or any destructive action. The tools and evidence used in this exercise are representative of common reconnaissance techniques used in ethical security assessments.

The approach followed a standard security workflow:

1. Domain and WHOIS review
2. DNS and host resolution analysis
3. HTTP response and server fingerprinting
4. Technology identification using web scanners
5. WAF detection and pattern analysis
6. Documentation of findings and evidence

## Summary of Findings

The collected evidence indicates that `networkwalks.com` is a live domain associated with a public website. The domain resolves to the IP address `192.232.216.135` and appears to be hosted in a conventional public environment. The reconnaissance results show that the site redirects from HTTP to HTTPS and exposes a WordPress-based platform with supporting front-end libraries.

The site also showed signs of application-layer protection, with a WAF detection identifying ModSecurity. The target appears to implement basic security hygiene, but the use of a CMS and associated plugins means that patching and configuration management remain important considerations. These findings are consistent with a public-facing educational or information website using common web technologies and defensive controls.

## Evidence and Technical Observations

### 1. Domain Registration and WHOIS Data

WHOIS analysis revealed that the domain is active and registered through a major registrar. The data also indicated that ownership details were masked, which is common for public-facing commercial websites. This is a normal privacy-preserving practice and does not necessarily indicate malicious behavior.

![WHOIS reconnaissance screenshot](./WHOIS_Screenshot.png)

- Registrar: GoDaddy.com, LLC
- Domain status: active
- Registrant details: privacy protected
- Nameservers: multiple standard hosting nameservers identified

Relevant output: [whois_output.txt](./whois_output.txt)

### 2. DNS Resolution and Host Discovery

The DNS and host-resolution phase established that the target domain resolves successfully to a public IPv4 address. This confirms the domain is live and reachable over the internet.

![NSLOOKUP screenshot](./NSLookup_Screenshot.png)

![DNSRecon screenshot](./DNSRecon_Screenshot.png)

The DNS evidence shows the site resolves to:

- Domain: `networkwalks.com`
- Resolved IP: `192.232.216.135`
- Evidence source: `nslookup_output.txt` and `dnsrecon_output.txt`

Relevant output: [nslookup_output.txt](./nslookup_output.txt) and [dnsrecon_output.txt](./dnsrecon_output.txt)

### 3. HTTP Headers and Server Fingerprinting

HTTP analysis indicated that the site responds to HTTP requests with a redirect to HTTPS. The HTTPS response returned a successful status, and the server banner identified Apache. This supports the conclusion that the site is publicly accessible and properly configured with secure transport on the primary endpoint.

![Curl headers screenshot](./Curl_Headers_Screenshot.png)

Observed technical indicators:

- HTTP redirect to HTTPS
- Server banner: Apache
- Content-Type: text/html
- Evidence of plugin-related cookie activity
- HTTPS enforcement present

Relevant output: [curl_headers.txt](./curl_headers.txt)

### 4. Technology Stack Identification

WhatWeb identified the target as a WordPress site with supporting technologies including Bootstrap and jQuery. This indicates a content management system architecture and a standard web application stack commonly used in public websites.

![WhatWeb screenshot](./WhatWeb_Screenshot.png)

Detected technologies include:

- WordPress 7.1.4
- WordPress Download Manager 3.3.76
- Bootstrap
- jQuery
- Open Graph metadata and HTML5 structure

Relevant output: [whatweb_output.txt](./whatweb_output.txt)

### 5. WAF Identification

The WAF detection phase identified ModSecurity, suggesting that the website is protected at the application layer by a web application firewall. This is a significant security control because it can filter malicious requests and reduce exposure to common web attacks.

![WAF detection screenshot](./WAF_Screenshot.png)

Relevant output: [waf_output.txt](./waf_output.txt)

### 6. Network Scanning and Zenmap Evidence

The repository also contains Zenmap-related outputs documenting network scanning procedures and graphical evidence of host and service discovery. These materials reinforce the practical nature of the internship task and demonstrate the use of network reconnaissance tools in ethical assessments.

![Zenmap screenshot 1](./Zenmap%201%20(1).png)

![Zenmap screenshot 2](./zenmap2.png)

Supporting material: [Nmap - Zenmap GUI.pdf](./Nmap%20-%20Zenmap%20GUI.pdf)

## Security Insights

This exercise highlights several important concepts in cybersecurity and reconnaissance:

- Public information is often sufficient to build a meaningful profile of a target.
- DNS records, WHOIS data, and HTTP headers can reveal significant operational details without direct exploitation.
- Web technology fingerprinting can identify platform and plugin exposure, which is essential for risk assessment.
- WAF detection demonstrates the importance of layered security in web environments.
- Even modest reconnaissance can reveal risks associated with CMS platforms, outdated components, and plugin ecosystems.

From a broader security perspective, the target’s public-facing infrastructure demonstrates the need for: 

- regular patching of CMS and plugins;
- secure and consistent HTTPS configuration;
- monitoring of public-facing services;
- active review of website technology stacks;
- proactive security configuration to reduce exposure to common web threats.

While the observed controls indicate a degree of security hardening, the report must be interpreted as a reconnaissance summary rather than a full vulnerability assessment. Technology detection alone does not prove exploitation risk; it provides a basis for further analysis.

## Project Significance

This repository demonstrates a foundational understanding of ethical cybersecurity practice. It shows how reconnaissance can be used responsibly to gather public intelligence, document evidence, and interpret the digital footprint of a target. The project reflects the standards expected in an internship environment: structured methodology, reproducible evidence, and clear professional reporting.

## Supporting Files

The repository contains the following supporting materials:

- [README.md](./README.md)
- [whois_output.txt](./whois_output.txt)
- [nslookup_output.txt](./nslookup_output.txt)
- [dnsrecon_output.txt](./dnsrecon_output.txt)
- [curl_headers.txt](./curl_headers.txt)
- [whatweb_output.txt](./whatweb_output.txt)
- [waf_output.txt](./waf_output.txt)
- [Nmap - Zenmap GUI.pdf](./Nmap%20-%20Zenmap%20GUI.pdf)
- [W2-PM-FINAL - Sample Report v2.docx](./W2-PM-FINAL%20-%20Sample%20Report%20v2.docx)
- [kali_lab_files_week 2.zip](https://github.com/user-attachments/files/34630745/kali_lab_files_week.2.zip)

## Conclusion

This repository presents a clear and well-documented record of a passive reconnaissance assessment of `networkwalks.com`. The findings confirm that the target is an active public website with DNS resolution, HTTP redirect behavior, WordPress-based architecture, and application-layer protection via ModSecurity.

The project successfully demonstrates the process of evidence-based security analysis and serves as a strong example of a cybersecurity internship task focused on footprinting, reconnaissance, and structured reporting. It is useful both as a learning artifact and as a practical reference for ethical external reconnaissance workflows.

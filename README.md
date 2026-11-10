# Week 2 Cybersecurity Internship: Footprinting, Reconnaissance and Network Scanning

## Executive Summary

This project presents a professional, evidence-based passive reconnaissance assessment of `networkwalks.com`, a public-facing website used as the target for a cybersecurity internship exercise. The objective was to evaluate publicly available information and identify the digital footprint of an external target without engaging in intrusive or unauthorized activity.

The assessment incorporated domain analysis, DNS resolution, web technology fingerprinting, HTTP header inspection, WAF detection, and supporting evidence documentation. The findings show that the target is a live and reachable website, uses a WordPress-based architecture, redirects HTTP to HTTPS, and appears to be protected by ModSecurity.

Although the exercise does not constitute a full vulnerability assessment, it demonstrates the value of ethical reconnaissance in understanding a target’s public exposure, operational posture, and security controls. The evidence was captured, documented, and organized in a clear, professional report that reflects sound investigative practice and cybersecurity awareness.

## Project Overview

This repository documents a structured cybersecurity task focused on footprinting and network reconnaissance. The project environment simulates a realistic scenario in which a security analyst is expected to gather and interpret publicly visible information about a target system.

The task is designed to build practical skills in identifying:

- domain registration traits;
- internet-facing service behavior;
- DNS and host exposure;
- web server and framework indicators;
- security protections such as WAFs;
- the broader digital footprint of a target.

The repo is intentionally centered on evidence, documentation, and professional reporting rather than exploit development or malicious testing. From a learning perspective, it provides a strong example of how ethical and responsible reconnaissance can support organizational risk awareness and decision-making.

## Objectives

This project was designed to achieve the following objectives:

1. Identify and characterize a public target domain.
2. Gather and interpret WHOIS and DNS information.
3. Analyze HTTP behavior and server responses.
4. Identify the target’s technology stack and platform indicators.
5. Detect signs of defensive infrastructure such as a WAF.
6. Present the findings in a professional, readable, and security-focused format.

## Scope and Methodology

The assessment was intentionally limited to passive reconnaissance methods and public-facing information. No exploitation, credential theft, brute-force activity, or unauthorized penetration testing was carried out.

The methodology followed a standard defensive security workflow:

- Domain and WHOIS review
- DNS and host resolution analysis
- HTTP response inspection
- Web framework and plugin detection
- WAF identification and interpretation
- Documentation and reporting of evidence

## Target Profile

- Domain: `networkwalks.com`
- Assessment date: 2026-11-10
- Resolved IP address: `192.232.216.135`
- Observed platform: WordPress-based website
- Observed server: Apache
- Observed transport behavior: HTTP redirection to HTTPS
- Observed web protection: ModSecurity WAF

## Findings and Evidence

### 1. Domain Registration and WHOIS Analysis

WHOIS data confirmed that the target domain is active and registered through a major registrar. The domain registration record was consistent with a standard business or commercial website, and ownership details were intentionally masked through privacy protection. This is common in public-facing environments and is not inherently suspicious.

Key observations:

- Domain is active and not expired.
- Registration is managed through a public registrar.
- Privacy protection is in place for identity masking.
- Registrant identity was not publicly exposed.

![WHOIS reconnaissance screenshot](./WHOIS_Screenshot.png)

Relevant output: [whois_output.txt](./whois_output.txt)

### 2. DNS Resolution and Host Discovery

DNS analysis showed that `networkwalks.com` resolves correctly to a public IPv4 address. This confirms that the domain is live and reachable over the internet. A successful A record resolution is a foundational indicator in external reconnaissance because it validates the presence and reachability of a public-facing target.

Key observations:

- Domain resolves successfully.
- Public IPv4 address identified: `192.232.216.135`.
- Host is reachable and public.
- The domain footprint is consistent with a normal public website.

![NSLOOKUP screenshot](./NSLookup_Screenshot.png)

![DNSRecon screenshot](./DNSRecon_Screenshot.png)

Relevant output: [nslookup_output.txt](./nslookup_output.txt) and [dnsrecon_output.txt](./dnsrecon_output.txt)

### 3. HTTP Headers and Web Server Behavior

HTTP analysis revealed a redirect from HTTP to HTTPS. This indicates that the site enforces encrypted transport on the primary endpoint and is aligned with a standard secure web configuration practice. The HTTP response also exposed Apache as the server banner, which is consistent with a common hosting environment.

Key observations:

- HTTP request returned a redirect to HTTPS.
- HTTPS endpoint returned a successful response.
- The server banner indicates Apache.
- Content type and headers suggest a conventional web application stack.
- Cookie metadata indicates the presence of plugin or extension-driven functionality.

![Curl headers screenshot](./Curl_Headers_Screenshot.png)

Relevant output: [curl_headers.txt](./curl_headers.txt)

### 4. Technology Stack Identification

Web fingerprinting identified the site as WordPress-based and surfaced supporting technologies such as Bootstrap and jQuery. The discovery of a CMS and front-end libraries is a major insight because it highlights both functionality and potential security maintenance requirements. WordPress environments are common targets for plugin-related risk when they are not patched or securely configured.

Key observations:

- Platform identified: WordPress 7.1.4
- Download manager identified: WordPress Download Manager 3.3.76
- Front-end libraries: Bootstrap and jQuery
- Site metadata indicates a modern educational/public-facing website

![WhatWeb screenshot](./WhatWeb_Screenshot.png)

Relevant output: [whatweb_output.txt](./whatweb_output.txt)

### 5. WAF Fingerprinting

The WAF detection results identified ModSecurity, indicating that the target is protected by an application-layer firewall. While this is a positive indicator of defensive posture, it is important to note that WAF presence does not guarantee complete security. It does, however, demonstrate that the environment is configured with an additional layer of traffic filtering and attack mitigation.

Key observations:

- WAF identified: ModSecurity (SpiderLabs)
- Application layer protection is present
- Obfuscation and filtering may reduce the impact of basic enumeration and attack attempts

![WAF detection screenshot](./WAF_Screenshot.png)

Relevant output: [waf_output.txt](./waf_output.txt)

### 6. Network Scan and Reconnaissance Evidence

The repository also includes Zenmap-related materials and screenshots showing the use of network scanning tools in the reconnaissance flow. These artifacts provide additional support for the project’s practical scope and demonstrate the structured nature of the investigation.

![Zenmap screenshot 1](./Zenmap%201%20(1).png)

![Zenmap screenshot 2](./zenmap2.png)

Supporting document: [Nmap - Zenmap GUI.pdf](./Nmap%20-%20Zenmap%20GUI.pdf)

## Security Insights

This project provides several important insights into professional cybersecurity practice:

- Publicly accessible information can reveal a meaningful operational picture of a target.
- DNS, WHOIS, and HTTP metadata create a strong foundation for threat intelligence and risk analysis.
- Web technology fingerprinting is valuable for identifying platform exposure and software lifecycle risks.
- WAF detection is an important signal of defensive capability but not proof of complete resilience.
- CMS-based systems require ongoing updates, patch management, and configuration review.

The overall posture suggests a public website that is reachable, uses standard web infrastructure, and is protected by a basic application security layer. The environment is not necessarily vulnerable based solely on the evidence observed, but it does present a security profile that merits ongoing vigilance, especially if the WordPress platform or plugins are not maintained.

## Business and Strategic Relevance

From a broader security standpoint, this project reinforces the importance of proactive digital defense. Organizations that expose public-facing infrastructure must manage not only the technical controls on their servers but also the visibility created by DNS, platform detection, and web technologies. Even passive reconnaissance can reveal critical information about a system’s environment, which can inform risk prioritization, awareness, and mitigations.

This type of assessment is particularly valuable because it emphasizes prevention and awareness rather than reaction after compromise. In cybersecurity leadership terms, the project demonstrates how public reconnaissance and defensive analysis contribute to:

- stronger asset visibility;
- better exposure awareness;
- improved patching discipline;
- more informed security planning;
- reduced risk of preventable compromise.

## Supporting Materials

The repository includes all relevant work products for the internship task:

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

This project reflects a strong understanding of ethical computer security practices and the value of passive reconnaissance in real-world cybersecurity analysis. Through careful collection of WHOIS, DNS, network, and web fingerprinting evidence, the project demonstrates how an external target can be assessed responsibly and professionally.

The target domain, `networkwalks.com`, presents as a live WordPress-based public website that enforces HTTPS and appears to be protected by ModSecurity. While these are not proof of exploitation or vulnerability, they are meaningful indicators of exposure and defensive posture. The repository therefore serves as both a practical internship deliverable and a useful demonstration of how structured reconnaissance supports digital security awareness and operational decision-making.

This work demonstrates professional documentation, technical proficiency, and a clear understanding of modern security assessment principles. It is a strong representation of a disciplined and evidence-backed cybersecurity internship exercise.

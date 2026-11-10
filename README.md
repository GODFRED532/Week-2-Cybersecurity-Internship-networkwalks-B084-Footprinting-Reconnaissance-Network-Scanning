# Week 2 Cybersecurity Internship

## Footprinting, Reconnaissance & Network Scanning

A documented **passive reconnaissance exercise** using publicly available information. The repository includes the findings, command outputs, screenshots, and supporting materials from the assessment.

> **Scope and authorization:** The report describes passive checks against `networkwalks.com`. Only assess systems you own or have explicit permission to assess. This repository does not include exploit activity.

## At a glance

| Item | Details |
|---|---|
| Target | `networkwalks.com` |
| Assessment date | 2026-11-10 |
| Scope | Passive footprinting and reconnaissance using public information |
| Resolved IPv4 address | `192.232.216.135` |
| Observed web platform | WordPress (as reported by WhatWeb) |

## Summary of observations

- DNS lookup resolved the domain to a public IPv4 address.
- HTTP traffic redirected to HTTPS; the HTTPS endpoint returned a successful response in the captured results.
- The collected output identified Apache and WordPress, plus front-end and plugin-related technologies. Fingerprinting results are point-in-time observations and may not always be definitive.
- The WAF detection output identified ModSecurity.
- Public DNS, registration, and HTTP metadata provide useful context, but do not by themselves establish that a system is vulnerable.

## Findings and evidence

### Domain registration — WHOIS

The report records GoDaddy.com, LLC as the registrar and notes that registrant details are privacy-protected.

![WHOIS reconnaissance screenshot](./WHOIS_Screenshot.png)

[View the WHOIS output](./whois_output.txt)

### DNS and host resolution

The captured lookup resolved `networkwalks.com` to `192.232.216.135`.

![NSLOOKUP screenshot](./NSLookup_Screenshot.png)

[View the NSLOOKUP output](./nslookup_output.txt) · [View the DNSRecon output](./dnsrecon_output.txt)

![DNSRecon screenshot](./DNSRecon_Screenshot.png)

### HTTP headers and HTTPS behavior

The collected headers show an HTTP-to-HTTPS redirect and include server and response metadata. Header values can change over time and should be treated as observations from the assessment date.

![Curl headers screenshot](./Curl_Headers_Screenshot.png)

[View the captured headers](./curl_headers.txt)

### Web technology identification

WhatWeb identified WordPress and other technologies in its scan output. Technology fingerprinting is indicative, not proof of exact versions or patch status.

![WhatWeb screenshot](./WhatWeb_Screenshot.png)

[View the WhatWeb output](./whatweb_output.txt)

### WAF identification

The captured WAF-detection result identified ModSecurity. A detection result does not establish how the WAF is configured or how effective it is.

![WAF detection screenshot](./WAF_Screenshot.png)

[View the WAF output](./waf_output.txt)

### Network scanning materials

The repository also includes Zenmap screenshots and a short GUI reference document.

![Zenmap screenshot 1](./Zenmap%201%20(1).png)

![Zenmap screenshot 2](./zenmap2.png)

[Open the Nmap / Zenmap GUI PDF](./Nmap%20-%20Zenmap%20GUI.pdf)

## Assessment notes

The evidence suggests a publicly reachable website that redirects to HTTPS and has a WAF detection result. These are useful observations, but they are not a full security audit. The collected artifacts do not verify whether software is fully patched, whether security controls are correctly configured, or whether vulnerabilities are present.

## Repository contents

- **Screenshots:** WHOIS, DNS/NSLOOKUP, WhatWeb, WAF, HTTP headers, and Zenmap evidence (displayed above).
- **Text outputs:** captured WHOIS, DNS, HTTP header, WAF, and WhatWeb results (linked in each section).
- **Supporting documents:** [Nmap / Zenmap GUI PDF](./Nmap%20-%20Zenmap%20GUI.pdf) and [sample report DOCX](./W2-PM-FINAL%20-%20Sample%20Report%20v2.docx).
- **Lab archive:** [kali_lab_files_week 2.zip](https://github.com/user-attachments/files/34630745/kali_lab_files_week.2.zip).

## Conclusion

This project demonstrates a basic, evidence-backed workflow for passive footprinting and reconnaissance. The screenshots are embedded here for easier viewing, while the raw outputs and supporting materials remain available through the links above.

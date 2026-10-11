# SWYNEX Technologies — Security Assessment Report

## 1. Project Overview

This project documents a defensive security assessment conducted as part of cybersecurity internship tasks at SWYNEX Technologies.

## 2. Objectives

- Analyze network traffic in an authorized lab environment.
- Review a web application in a local security testing environment.
- Document observations, potential security risks, and remediation recommendations.
- Promote secure network and web application practices.

## 3. Scope

- Network traffic analysis using Wireshark.
- Local web application testing using OWASP Juice Shop.
- Documentation of observed results and security recommendations.

## 4. Tools Used

- Wireshark
- OWASP Juice Shop
- Browser Developer Tools
- Docker

## 5. Assessment Methodology

Testing was performed in a controlled environment using authorized tools and a local training application. Findings will be documented based on observed evidence and verified results.

### 6. Security Assessment Findings

#### 6.1 Network Traffic Analysis — Task 2

**Tool:** Wireshark

Network traffic was inspected in a controlled environment. The analysis included DNS, TCP, UDP, QUIC, TLS 1.2/1.3, TCP SYN packets, duplicate acknowledgements, and fast retransmissions.

These observations helped demonstrate protocol identification and basic network troubleshooting. The presence of these packet types alone does not establish malicious activity. No unverified security incident is claimed in this report.

#### 6.2 Web Application Review — Task 3

**Application:** OWASP Juice Shop  
**Environment:** Local training application (`localhost:3000`)  
**Tools:** Browser Developer Tools — Network panel

**Observed results:**
- A product search API request used the `GET` method and returned HTTP `200 OK`.
- The response contained JSON product data.
- `X-Content-Type-Options: nosniff` was observed.
- `X-Frame-Options: SAMEORIGIN` was observed.
- `Content-Security-Policy` and `Strict-Transport-Security` were not observed in the inspected response.

**Assessment notes:**

The successful API response and JSON product data were normal observations and do not independently demonstrate a vulnerability. The absence of a Content-Security-Policy header in the inspected response is a potential security-hardening concern that requires further verification across relevant application responses. The absence of Strict-Transport-Security on the inspected local HTTP response is not, by itself, evidence of a vulnerability.

No confirmed exploitable web vulnerability is claimed based on these checks alone.

#### 6.3 Recommendations

- Review security headers across relevant application responses.
- Configure an appropriate Content Security Policy after testing application compatibility.
- Use HTTPS in production and configure HSTS where applicable.
- Avoid exposing authentication tokens, cookies, or other sensitive request data in public reports.
- Continue testing only within authorized lab environments and document evidence for each confirmed finding.

## 7. Supporting Evidence

- **Network Security Analysis (Task 2):** [View Wireshark Analysis Report](https://github.com/solanki30/SWYNEX-Network-Security-Analysis/blob/main/SWYNEX_Network_Security_Analysis_Report.pdf))
- **Web Security Review (Task 3):** Conducted in a local OWASP Juice Shop environment. Observations and recommendations are documented in this report.

## 8. Conclusion

This assessment provided practical experience in network traffic analysis and web application security review using authorized educational tools. The report records observed results and recommends further verification where the available evidence is insufficient to confirm a vulnerability.

## Disclaimer

All testing was intended for authorized educational purposes in a controlled lab environment.

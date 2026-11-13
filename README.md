# <p align="center">🛡️ PENETRATION TESTING REPORT</p>
<p align="center"><b>FOOTPRINTING & NETWORK SCANNING PHASES</b></p>
<p align="center"><code>W2-PM-FINAL | CYBERSECURITY | NETWORKWALKS</code></p>

---

## 📋 Engagement Details

| Field | Detail |
| :--- | :--- |
| **Pentester Name (Cybersecurity Professional)** | Oludaiye Elijah Micheal |
| **Program/Batch** | B082-Networkwalks |
| **Date** | 13 November 2026 |
| **Modules completed** | W2-PM1 (Multiple Kali Tools)<br>W2-PM5 (Zenmap Scanning) |
| **Client/Target** | 1. Networkwalks (`networkwalks.com` — written permission secured)<br>2. My own local LAN Network |
| **Permission secured from client?** | Yes |
| **Phases covered** | **Phase 1:** Reconnaissance & Footprinting<br>**Phase 2:** Scanning & Network Discovery<br>**Phase 3-5:** In Progress |

---

## 1. Liability Disclaimer
> **⚠️ LEGAL NOTICE:** I have performed these activities only on the systems and devices where I had secured written permission or on the devices and systems that I own myself. All these materials are for educational and research purposes only. Do not use anything from this report to break the law. The instructor, the authors, and Networkwalks are not responsible for what anyone does with this knowledge. Every action you take is your own responsibility. Misuse can lead to criminal charges, heavy fines, loss of employment, and a permanent criminal record[cite: 1]. In most jurisdictions, unauthorized access is a crime even when no damage occurs[cite: 1].

---

## 2. Introduction
This report covers footprinting the `networkwalks.com` domain using multiple Kali Linux reconnaissance utilities (**W2-PM1**) and scanning my local area network using Zenmap (**W2-PM5**)[cite: 1]. Together, these two modules demonstrate how a penetration tester progresses from passive and semi-passive open-source intelligence gathering to active host discovery on a network segment[cite: 1]. This assessment represents the Week 2 deliverable of my ongoing Cybersecurity & Ethical Hacking internship program at Networkwalks[cite: 1].

All footprinting commands were executed within a Kali Linux environment, while local network discovery was performed using Zenmap (Nmap GUI) and Windows Command Prompt[cite: 1]. Every activity documented below details the exact command executed, the empirical results observed, terminal evidence screenshots, and an assessment of the security implications from an attacker's perspective[cite: 1].

---

## 3. Tools Used

| Tool / Platform | Purpose |
| :--- | :--- |
| **Kali Linux & Windows** | Primary operating environments used to execute reconnaissance and network scanning utilities[cite: 1]. |
| **WHOIS** | Query domain registration databases to retrieve registrar details, creation/expiration dates, and authoritative name servers[cite: 1]. |
| **WhatWeb** | Fingerprint web technologies including web server software, CMS versions, plugins, cookies, and HTTP headers[cite: 1]. |
| **nslookup** | Query DNS resolvers to resolve the target domain name into its corresponding IPv4 address[cite: 1]. |
| **curl -I** | Send HTTP HEAD requests to inspect raw server response headers, caching behavior, and exposed API endpoints[cite: 1]. |
| **wafw00f** | Identify and fingerprint Web Application Firewalls (WAF) protecting the target web application[cite: 1]. |
| **dnsrecon** | Perform comprehensive DNS enumeration across SOA, NS, MX, A, TXT/SPF, and SRV records[cite: 1]. |
| **Zenmap (Nmap GUI)** | Conduct host discovery (Ping Scan) on the local subnet to enumerate active hosts, IP addresses, MAC addresses, and network topology[cite: 1]. |
| **Windows CMD (ipconfig)** | Identify local host IPv4 configuration, subnet mask, and default gateway prior to scanning[cite: 1]. |

---

## 4. Activities Performed

### 4.1 Footprinting & Reconnaissance (W2-PM1)
Reconnaissance was conducted against `networkwalks.com` using six command-line utilities in Kali Linux to gather domain registration, web technology stack, HTTP header, WAF, and DNS infrastructure details[cite: 1]:

#### 1. WHOIS Domain Lookup
* **Command Executed:** `whois networkwalks.com`[cite: 1]
* **Empirical Results:** The WHOIS query revealed that `networkwalks.com` is registered through GoDaddy.com, LLC (IANA ID: 146)[cite: 1]. The domain was created on `2019-11-06`, last updated on `2025-11-12`, and is set to expire on `2027-11-06`[cite: 1]. Registrant and technical contact details are masked via Domains By Proxy, LLC (Tempe, Arizona)[cite: 1]. Domain status flags include `clientDeleteProhibited`, `clientRenewProhibited`, `clientTransferProhibited`, and `clientUpdateProhibited`[cite: 1]. Authoritative name servers listed are `NS6135.HOSTGATOR.COM`, `NS6136.HOSTGATOR.COM`, `NS29.DOMAINCONTROL.COM`, and `NS30.DOMAINCONTROL.COM`, and DNSSEC is reported as `unsigned`[cite: 1].
```bash
$ whois networkwalks.com
Domain Name: NETWORKWALKS.COM | Registrar: GoDaddy.com, LLC | Creation Date: 2019-11-06 | Expiry: 2027-11-06
Registrant Org: Domains By Proxy, LLC | Name Servers: NS6135.HOSTGATOR.COM, NS6136.HOSTGATOR.COM | DNSSEC: unsigned

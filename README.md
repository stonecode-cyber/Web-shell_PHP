# Web-shell_PHP\
# WORDPRESS-WEB-SHELL-INVESTIGATION
### Incident Response & Log Analysis: Detecting Web Shell Compromise

---

## Table of Contents
1. [Project Overview](#project-overview)
2. [Investigation Objectives & Indicators](#investigation-objectives--indicators)
3. [Lab Walkthrough & Documentation](#lab-walkthrough--documentation)
4. [Tools & Technologies Used](#tools--technologies-used)
5. [Conclusion](#conclusion)

---

## 1. Project Overview
<a id="project-overview"></a>

This project documents a hands-on incident response and log analysis investigation focusing on a compromised WordPress site. By analyzing Apache web access logs, tracking suspicious request patterns, and inspecting uploaded files via SSH, this lab identifies indicators of web shell deployment, enumeration commands, and privilege escalation enumeration scripts (`linpeas.sh`).

---

## 2. Investigation Objectives & Indicators
<a id="investigation-objectives--indicators"></a>

When analyzing web server logs for potential web shell activity, key indicators of compromise (IoCs) include:
* **Repeated or Suspicious Requests:** High-frequency probing or requests targeting specific `.php` files.
* **Strange Request Patterns:** Unusual HTTP response codes (e.g., repeated `404` errors followed by successful `200` responses).
* **Unusual User-Agents:** Non-standard or automated tools (`curl`, custom scripts).

---

## 3. 📑 Lab Walkthrough & Documentation
<a id="lab-walkthrough--documentation"></a>

The complete step-by-step investigation, including SSH remote access commands, log parsing syntax, attacker IP identification, file upload analysis, and flag recovery, has been organized into a dedicated file:

👉 **[Read the Full Step-by-Step Investigation Walkthrough](./Web-Shell-Investigation-Walkthrough.md)**

---

## 4. Tools & Technologies Used
<a id="tools--technologies"></a>
* **SSH** (Remote server investigation and shell access)
* **Linux Terminal & Log Parsing** (`cat`, `grep`)
* **Apache Access Logs** (`/var/log/apache2/access.log`)
* **Web Shell Artifact Analysis** (`shadyshell.php`)

---

## 5. Conclusion
<a id="conclusion"></a>

> **Log analysis and web server log parsing are vital first responders' skills for identifying initial access vectors, tracking attacker directory enumeration, and locating malicious web shells planted during a compromise.**

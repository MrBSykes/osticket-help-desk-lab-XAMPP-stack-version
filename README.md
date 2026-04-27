# 🎫 osTicket Help Desk Lab

> **A fully configured IT help desk environment built from scratch — simulating real-world enterprise ticketing workflows, automation, and SLA enforcement.**

---

## 📌 Project Overview

This project deploys and configures **osTicket**, an open-source help desk ticketing platform, on a local XAMPP stack (Apache + PHP + MySQL). The goal was to simulate a production-grade helpdesk environment complete with departments, tiered agents, SLA plans, automation rules, and end-to-end ticket lifecycle management.

This is **Phase 1** of a two-part project. Phase 2 will migrate the deployment to an Ubuntu Server VM using a manually configured Linux LAMP stack.

---

## 🛠️ Tech Stack

| Component | Details |
|---|---|
| **Web Server** | Apache (via XAMPP 8.1.x) |
| **Database** | MySQL 8.x (via XAMPP) |
| **Language Runtime** | PHP 8.1 |
| **Ticketing Platform** | osTicket v1.18.x |
| **DB Management** | phpMyAdmin |
| **Host OS** | Windows 10/11 |
| **Deployment Type** | Local (localhost) |

---

## 🔧 What Was Built

### Organizational Structure
- **4 Departments** — IT Support, Systems Administration, Network Operations, Security
- **3 Teams** — Tier 1 Support, Tier 2 Support, Incident Response
- **4 Agents** — Mapped across departments and teams
- **4 End Users** — Simulating an employee base submitting tickets

### SLA Plans
| Plan | Grace Period | Schedule |
|---|---|---|
| SEV-A (Critical) | 1 hour | 24/7 |
| SEV-B (High) | 4 hours | 24/7 |
| SEV-C (Normal) | 8 hours | Mon–Fri 8am–5pm |

### Help Topics (6)
- Business Critical Outage *(SEV-A / Emergency)*
- Security Incident *(SEV-A / Emergency)*
- Password Reset *(SEV-B / High)*
- Network Connectivity Issue *(SEV-B / High)*
- Personal Computer Issues *(SEV-C / Normal)*
- Equipment Request *(SEV-C / Low)*

### Automation Filters (4)
Ticket filters that auto-route based on help topic — assigning department, team, priority, and SLA without manual intervention:
- Security Incident Auto-Route
- Network Issue Auto-Route
- Password Reset Auto-Assign
- Critical Outage Escalation

---

## 🎟️ Ticket Workflow Simulations

Four end-to-end scenarios were executed to validate the full system:

| # | Scenario | Submitted By | Priority | SLA | Assigned To |
|---|---|---|---|---|---|
| 1 | Password Reset | Kayla Jefferies | High | SEV-B | Alex Turner |
| 2 | Security Incident | Derek Walsh | Emergency | SEV-A | Sarah Barker |
| 3 | Network Connectivity Issue | Yvette Cheatham | High | SEV-B | Sam Rivera |
| 4 | Business Critical Outage | James Carter | Emergency | SEV-A | Lindsey Matthews |

Each scenario validated:
- ✅ Automated routing (department, team, priority, SLA — no manual triage)
- ✅ Due date auto-calculation from SLA grace period
- ✅ Audit trail with full timestamped action log
- ✅ Internal notes and user-facing replies

---

## 🐛 Troubleshooting Log

Real issues encountered and independently resolved during installation:

| Issue | Root Cause | Resolution |
|---|---|---|
| 404 on `/osticket/setup/` | `upload\` folder copied as-is instead of its contents | Moved contents of `upload\` directly into `htdocs\osticket\` |
| HTTP 500 / PHP Fatal Error | Database hostname entered as `port80` instead of `localhost` | Corrected hostname field in installer |
| Installer blocked on blank password | osTicket v1.18.x requires a non-empty MySQL password | Set root password via `mysqladmin` CLI |
| phpMyAdmin access denied | `config.inc.php` still referenced blank password after MySQL change | Updated `$cfg['Servers'][$i]['password']` in phpMyAdmin config |

---

## 📂 Documentation

Full setup and configuration documentation (including screenshots) is available in [`osTicket_Lab_Documentation.docx`](./osTicket_Lab_Documentation.docx).

---

## 🗺️ Roadmap

- [x] Phase 1 — Local XAMPP deployment with full configuration and workflow simulation
- [ ] Phase 2 — Ubuntu Server VM deployment (VirtualBox, manual LAMP stack via CLI)
- [ ] Phase 2 documentation and comparative write-up

---

## 💡 Skills Demonstrated

`Help Desk Administration` `Ticketing Systems` `SLA Management` `Workflow Automation` `MySQL` `phpMyAdmin` `Apache` `PHP` `XAMPP` `Linux (Phase 2)` `Technical Documentation` `Troubleshooting`

---

## 👤 Author

**Bryan Sykes**  
IT Support | Systems Administration | Cybersecurity  
📍 Northern Virginia / DC Metro  
🔗 [LinkedIn](https://www.linkedin.com/in/bryansykes) | 🐦 [@SecuredByBryan](https://x.com/SecuredByBryan)

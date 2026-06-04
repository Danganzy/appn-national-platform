[README_appn_platform.md](https://github.com/user-attachments/files/28596184/README_appn_platform.md)
# APPN National Digital Platform

> Full-stack institutional platform for the Association of Private Polytechnics in Nigeria — public website, secure members portal, e-voting, private forum, dues management, and governance tools. Built and deployed under a formal commercial contract via KDCS Limited.

**Live:** [appnigeria.org](https://appnigeria.org) &nbsp;|&nbsp; **Client:** Association of Private Polytechnics in Nigeria (RC 157986)

![HTML5](https://img.shields.io/badge/HTML5-E34F26?logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-ES6-F7DF1E?logo=javascript&logoColor=black)
![PHP](https://img.shields.io/badge/PHP-8.2-777BB4?logo=php&logoColor=white)
![MySQL](https://img.shields.io/badge/MySQL-8.0-4479A1?logo=mysql&logoColor=white)

---

## Overview

APPN is the national body representing all private polytechnic and monotechnic institutions across Nigeria. Before this project, the association had zero digital presence — all governance, communications, and member administration happened via phone and WhatsApp.

I scoped, proposed, and built a two-phase national digital headquarters: a credible public-facing website and a fully functional governance platform for 30+ member institutions.

**Contract value:** ₦425,000 development + ₦90,000/year infrastructure  
**Engagement type:** Formal commercial contract via KDCS Limited (RC 1948680)

---

## Platform Architecture

```
┌──────────────────────────────────────────────────────────────┐
│                     PUBLIC WEBSITE                           │
│  Home · Member Directory · Advocacy & News · Resources       │
│  Meet the Excos · Constitution · Accreditation Tracker       │
│  Contact · Membership Application Form                       │
└──────────────────────────────┬───────────────────────────────┘
                               │
                    ┌──────────▼──────────┐
                    │   Portal Login       │
                    │  (PHP/MySQL auth)    │
                    └──────────┬──────────┘
                               │
        ┌──────────────────────┼───────────────────────┐
        ▼                      ▼                       ▼
┌──────────────┐    ┌──────────────────┐    ┌─────────────────┐
│  Discussion  │    │   E-Voting        │    │  Dues & Members │
│  Forum       │    │   System          │    │  Administration │
│              │    │                  │    │                 │
│ Threaded     │    │ Authenticated     │    │ Payment history │
│ EXCO pinning │    │ 1 vote/institution│    │ Certificates    │
│ Role-based   │    │ Audit trail       │    │ AGM records     │
│ moderation   │    │ Tamper-proof      │    │ Profile editing │
└──────────────┘    └──────────────────┘    └─────────────────┘
        │
        ▼
┌─────────────────────────────────────────────────────────────┐
│              Document Repository                             │
│  EXCO uploads · Member downloads · Secured from public      │
│  Constitution · Accreditation timelines · Correspondence     │
└─────────────────────────────────────────────────────────────┘
```

---

## Public Website — Key Features

### Member Directory (School Finder)
The flagship public feature. Prospective students filter by:
- **State** (all 36 states + FCT)
- **Programme / Course** (Accountancy, Engineering, Mass Comm, etc.)

Each institution listing shows accredited courses, HOD direct line, Admissions Officer contact, and a link to the school's own application portal. Data cross-referenced against FME and NBTE databases, validated against 21 institutional submission files.

### Advocacy & News
Secretariat-managed CMS section: formal correspondence to JAMB and NBTE, meeting reports, policy updates, and event announcements — giving APPN a documented public advocacy voice for the first time.

### Institutional Credibility Pages
- APPN Constitution (publicly visible)
- Accreditation Status Tracker
- Annual General Meeting (AGM) section with notices, minutes, and attendance records

---

## Members Portal — Key Technical Decisions

### E-Voting System
Built for APPN's executive election and resolution cycles. Key design constraints:
- Each member institution has exactly one authenticated vote — enforced at the database level, not just the UI
- Votes are timestamped, logged, and immutable once cast
- Results visible to EXCO only while polls are open; published to all members on close
- Deliberately designed without over-engineering — APPN elections are not daily events; the system is reliable for the use case it actually serves

### Discussion Forum Access Control
Three-tier role model:
1. **Public** — no access, forum is invisible
2. **Member institutions** — read and post in all threads
3. **EXCO members** — moderation privileges + pinned announcement capability

### Dues & Membership Administration
- Annual dues: ₦50,000/institution/year
- Members view full payment history and outstanding balance
- Membership certificates generated for compliant institutions
- New institutions apply digitally (form + document upload) — replaces the previous paper/WhatsApp process

---

## Infrastructure

| Item | Detail |
|------|--------|
| Hosting | Dedicated cPanel account, Qservers VPS (WHM) |
| Nameservers | ns1/ns2.kingspolyonline.com.ng |
| Primary domain | appn.org.ng (Whogohost) |
| Secondary domain | appn.ng |
| Email domain | appnigeria.org |
| SSL | AutoSSL |
| DNS propagation | Managed via Whogohost registrar |

---

## Data Foundation

Real institutional data incorporated throughout:
- 7 elected executive council members (elected 17 June 2023): President, VP, Secretary, Asst. Secretary, PRO/Media, Treasurer, Financial Secretary
- 30+ member institutions verified against FME/NBTE records
- All contact emails use the appnigeria.org domain

---

## Stack

- **Frontend:** HTML5, CSS3, Vanilla JavaScript (no framework — intentional for long-term maintainability)
- **Portal backend:** PHP 8.2, MySQL
- **Typography:** Merriweather (headings), Inter (body)
- **Brand palette:** Green `#1A6B2F`, Navy `#1A5276`, Crimson `#C0392B`
- **Infrastructure:** WHM/cPanel, AutoSSL, Whogohost DNS
- **Phase 2 (in pipeline):** Full PHP/MySQL server-side authentication and database-driven membership management

---

## Commercial Structure

This project demonstrates a complete client engagement cycle:
1. Requirements gathering and scoping with association leadership
2. Formal written proposal on KDCS Limited letterhead
3. Commercial negotiation (development fee + annual infrastructure + optional retainer)
4. Phased delivery: public site → secured portal → Phase 2 backend
5. Domain registration, DNS management, VPS provisioning, and handover documentation

---

## Screenshots

> _Available on request — see live site at appnigeria.org_

---

## About

Built by **Oluwafemi Ganzallo** via **KDCS Limited** (RC 1948680), Ikeja, Lagos.  
Role on project: Sole developer, solutions architect, and account manager.  
ORCID: [0009-0008-6198-7044](https://orcid.org/0009-0008-6198-7044)

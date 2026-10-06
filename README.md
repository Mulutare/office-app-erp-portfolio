# OfficeApp ERP

A modular enterprise resource planning platform designed for internal business operations, workflow automation, reporting, and controlled integration between departments.

> **Portfolio case study**
>
> The production source code, database, infrastructure configuration, credentials, and business data are private.
> This repository contains only sanitized documentation, architecture information, diagrams, and selected screenshots.

---

## Overview

OfficeApp ERP centralizes major operational workflows within one controlled platform.

The system includes modules for:

- Sales and distribution
- Inventory and warehouse management
- Human resources
- Attendance and workforce scheduling
- Recruitment and applicant management
- Public Careers Portal integration
- Role-based access control
- Business integrations
- Notifications and background processing
- Power BI reporting and historical analysis

The application is designed around modular business services, company-scoped access control, controlled database migrations, background workers, auditability, and production-safe deployment procedures.
<img width="938" height="433" alt="image" src="https://github.com/user-attachments/assets/a7b740ee-299c-4530-af15-55f9bf301dc8" />


---

## Technology Stack

| Area | Technology |
|---|---|
| Backend | PHP 8.1 |
| Database | MySQL |
| Frontend | HTML, CSS, JavaScript |
| Authentication | Session-based authentication |
| Authorization | Role-Based Access Control |
| Reporting | Power BI |
| Background Processing | Linux cron + PHP CLI workers |
| Integrations | REST-style HTTP integrations |
| Hosting | Linux / cPanel |
| Source Control | Git / GitHub |

---

## Major Modules

### Sales

Supports controlled sales operations and integration with inventory and reporting processes.

### Inventory & Warehousing

Handles warehouse structures, stock movement, inventory balances, transfers, and downstream business integration.

### Human Resources

Maintains employee and organizational information used by other ERP modules.

### Attendance

Supports employee work schedules, attendance records, reminders, holidays, calendars, and notification workflows.

### Recruitment

Centralizes applicant records, private documents, vacancies, review workflows, application statuses, and recruitment operations.

### Careers Portal

A separate public-facing Careers application integrates securely with the private ERP.

Public applicants never receive direct access to the ERP.

The integration supports:

- vacancy publication
- job-specific screening questions
- applicant submission
- private document handling
- secure synchronization
- duplicate protection
- application import into Recruitment

### Reporting & Power BI

Provides structured reporting views and historical reporting support for business intelligence and management analysis.

---<img width="1493" height="887" alt="image" src="https://github.com/user-attachments/assets/27058f05-c710-45ff-bbf4-23e4da1c1971" />


## High-Level Architecture

```text
                         ┌─────────────────────┐
                         │     ERP Users       │
                         │ HR / Sales / Admin  │
                         └──────────┬──────────┘
                                    │
                                    ▼
                         ┌─────────────────────┐
                         │    OfficeApp ERP    │
                         │                     │
                         │ Authentication      │
                         │ RBAC                │
                         │ Sales               │
                         │ Inventory           │
                         │ HR                  │
                         │ Attendance          │
                         │ Recruitment         │
                         │ Integrations        │
                         └───────┬───────┬─────┘
                                 │       │
                     ┌───────────┘       └───────────┐
                     ▼                               ▼
              ┌─────────────┐                 ┌─────────────┐
              │    MySQL    │                 │  Power BI   │
              │  Database   │                 │  Reporting  │
              └─────────────┘                 └─────────────┘


 Applicants
     │
     ▼
┌───────────────────┐
│  Careers Website  │
│ Public Application│
└─────────┬─────────┘
          │
          │ Secure signed integration
          ▼
┌───────────────────┐
│ Recruitment Module│
│   Private ERP     │
└───────────────────┘
```

---

## Background Processing

OfficeApp ERP uses server-side background workers for operations that should not depend on browser requests.

Production workloads include:

- internal ERP integration processing
- attendance reminder processing
- recruitment mailbox synchronization
- Careers Portal synchronization
- security metadata maintenance

Workers use scheduled execution, locking, bounded workloads, and execution tracking.

---

## Security Architecture

The platform was designed around separation of responsibilities and restricted access.

Key controls include:

- company-scoped role-based access control
- permission checks for business operations
- CSRF protection
- private document storage
- audit trails
- secure Careers Portal integration
- replay protection and request signing
- rate limiting
- duplicate submission protection
- controlled production configuration

The public Careers Portal does not expose the private ERP application to applicants.

---

## Recruitment & Careers Workflow

```text
HR creates vacancy
        │
        ▼
Internal review / opening
        │
        ▼
Authorized publication
        │
        ▼
Careers Portal
        │
        ▼
Applicant submission
        │
        ▼
Secure synchronization
        │
        ▼
ERP Recruitment Inbox
        │
        ▼
Screening and human review
        │
        ▼
Interview / evaluation
        │
        ▼
Final recruitment decision
```

---

## Production Engineering

The project also includes operational engineering for:

- Linux / cPanel production deployment
- MySQL migration management
- background cron processing
- task execution monitoring
- production backups
- rollback procedures
- database diagnostics
- integration troubleshooting
- recovery documentation

Detailed production configuration is intentionally excluded from this public repository.

---

## Engineering Areas Demonstrated

This project demonstrates experience with:

- ERP system architecture
- PHP backend development
- relational database design
- transactional business logic
- role-based authorization
- modular application design
- background processing
- external system integration
- secure file handling
- business intelligence integration
- production deployment
- Linux server administration
- troubleshooting and recovery

---

## Screenshots

Sanitized screenshots of selected modules will be added here:

- Dashboard
- Sales
- Inventory & Warehousing
- Human Resources
- Attendance
- Recruitment
- Careers Portal
- Reporting

> All screenshots are sanitized to exclude credentials, personal information, confidential business information, and production infrastructure details.

---

## Source Code Notice

The complete OfficeApp ERP source code is maintained in a private repository.

This public repository is a portfolio and technical case study only. It does not contain production source code, database dumps, credentials, API secrets, private documents, employee records, applicant records, or infrastructure configuration.

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

---

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

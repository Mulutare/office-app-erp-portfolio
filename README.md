# OfficeApp ERP

**ERP Systems Integration • API Integration • Linux & MySQL Operations**

OfficeApp ERP is a modular PHP/MySQL platform that connects business operations, a public Careers Portal, background processing and Power BI reporting. This case study highlights the application integration and production operations behind the system.

**Project contributor:** Muluneh Tarekegn  
**Organization:** Passion Technologies PLC  
**Scope:** ERP development and customization, systems integration, deployment, database support and ongoing maintenance.

> This is a public technical case study. Production source code, databases, credentials, private documents and infrastructure configuration are maintained privately.

## Business context

Sales, inventory, people operations and recruitment need consistent information and controlled access across departments. OfficeApp ERP brings these workflows into one platform while allowing applicants to use a separate public Careers Portal without direct access to the private ERP.

## My contribution

- Developed, customized, deployed and maintain OfficeApp ERP using PHP and MySQL.
- Connected ERP workflows and external applications through REST-style HTTP integrations and scheduled processing.
- Implemented and maintained role-based access, background jobs and reporting integration.
- Supported Linux/cPanel hosting, MySQL diagnostics and migrations, production backups, rollback procedures and service recovery.
- Troubleshot application, database and integration issues and maintained operational documentation.

## System at a glance

| Area | Documented capabilities |
|---|---|
| Business operations | Sales and distribution, procurement, inventory, warehouses and assets |
| People operations | HR, attendance, workforce schedules and recruitment |
| External integration | Public Careers Portal, vacancy publication and applicant synchronization |
| Data and reporting | MySQL, structured reporting views, Power BI and historical analysis |
| Access and controls | Company-scoped RBAC, permission checks, audit trails and private document storage |
| Production operations | Linux/cPanel, cron workers, migrations, backups, rollback and diagnostics |

## Integration architecture

The following map shows logical components and data flows, without production hostnames or configuration.


| From | Connection | To |
|---|---|---|
| Internal ERP users | Authenticated, role-controlled access | OfficeApp ERP modules |
| OfficeApp ERP | Business transactions and queries | MySQL |
| MySQL reporting views | Structured reporting data | Power BI |
| Linux cron / PHP CLI workers | Scheduled processing | ERP integration and notification workloads |
| Public applicants | Vacancy browsing and submissions | Public Careers Portal |
| ERP recruitment | Authorized vacancy publication | Careers Portal |
| Careers Portal | Signed HTTP integration | Private ERP Recruitment module |

## Careers Portal and recruitment integration

The public Careers Portal and the private ERP remain separate. The integration supports vacancy publication, job-specific screening questions, applicant submissions, document handling and import into the ERP Recruitment module.

Documented controls include signed requests, replay protection, rate limiting, duplicate submission protection and permission checks. Private applicant documents remain subject to controlled access.

1. HR creates a vacancy.
2. Internal review authorizes publication.
3. The Careers Portal presents the vacancy and screening questions.
4. Applicants submit their applications through the public portal.
5. Controlled synchronization imports applications into the ERP Recruitment inbox.
6. Authorized staff perform screening, interviews and evaluation.
7. A human recruitment decision completes the workflow.

## Background processing

Linux cron and PHP CLI workers handle operations independently of browser requests:

- Internal ERP integration processing.
- Attendance reminders and notification workflows.
- Recruitment mailbox synchronization.
- Careers Portal synchronization.
- Security metadata maintenance.

Workers use scheduled execution, locking, bounded workloads and execution tracking to make processing observable and controlled.

## System administration and database operations

Production work covers Linux/cPanel application deployment, MySQL migration management, database diagnostics, task monitoring and integration troubleshooting. Backups, rollback procedures and recovery documentation support maintenance and incident response.

Operational configuration, credentials and production data are excluded from this repository.

## Access and application security

Documented application controls include:

- Session-based authentication and company-scoped role-based access control.
- Permission checks for business operations and CSRF protection.
- Private document storage and audit trails.
- Request signing, replay protection, rate limiting and duplicate protection for external integration.
- Controlled production configuration and separation of the public portal from the private ERP.

## Technology stack

| Area | Technology |
|---|---|
| Backend | PHP 8.1 |
| Database | MySQL |
| Frontend | HTML, CSS, JavaScript |
| Authentication and authorization | Sessions and role-based access control |
| Integration | REST-style HTTP integrations |
| Background processing | Linux cron and PHP CLI workers |
| Reporting | Power BI |
| Hosting | Linux / cPanel |
| Version control | Git / GitHub |

## Reporting interface

The following visual shows the ERP reporting interface and navigation. It is interface evidence, rather than a claim about measured business results.

<img width="1493" height="887" alt="OfficeApp ERP reporting interface and report navigation" src="https://github.com/user-attachments/assets/27058f05-c710-45ff-bbf4-23e4da1c1971" />

## Skills demonstrated

ERP customization, API and systems integration, PHP backend development, relational database support, role-based authorization, background processing, Linux administration, production deployment, troubleshooting and recovery.

## Evidence and scope

This repository presents project documentation, logical architecture and a selected interface visual. It does not include a runnable public demo or production source code. Quantified performance or business-impact claims are omitted because supporting measurements are not included.

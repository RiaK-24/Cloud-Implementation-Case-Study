# System Architecture Overview – PeopleSoft to Workday Migration

## Objective
Migrate recruitment data and workflows from Oracle PeopleSoft to Workday, while maintaining integrations with downstream systems (e.g., payroll, background checks, identity management).

---

## Legacy Architecture (Before Migration)
- PeopleSoft HRMS v9.2 as the core recruitment system
- Oracle DB backend
- Integrations with:
  - Active Directory (for user provisioning)
  - Payroll (via custom SFTP jobs)
  - Background Check Vendor (via SOAP API)
  - Document Management System (resumes & offer letters)
  - Internal Reporting Tool (via custom SQL extracts)

---

## Target Architecture (After Migration to Workday)
- Workday as system of record for recruitment
- Workday’s native APIs for integrations
- Use of Workday Studio for complex data transformations
- Scheduled data extracts to legacy systems during transitional period
- New integration via Workday Web Services (WWS) for background checks, IDP, and offer workflows

---

## Key Changes & TPM Role
| Area                    | Key Change                                  | Program Manager Tasks |
|-------------------------|------------------------------------------|----------------|
| Data Migration          | 50K+ candidate profiles migrated         | Led mapping sessions, managed vendors, signed off on test plans |
| Integration Strategy    | Replaced custom SFTP jobs with WWS APIs | Facilitated design workshops with Workday & internal teams |
| Access Management       | Shifted to SAML-based SSO                | Worked with Security & HRIS to align on user flows |
| Reporting Transition    | Built interim reporting bridge           | Defined interim architecture for analytics team |

---

## Risks Addressed
- **Data integrity issues** in historical resume records
- **Timing misalignment** with payroll integration
- **Regulatory compliance** with GDPR (data deletion policies)

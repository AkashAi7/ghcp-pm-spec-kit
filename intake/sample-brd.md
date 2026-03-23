# Business Requirement Document (BRD)
## Project: Smart Expense & Financial Analytics Platform

**Version:** 1.0  
**Date:** March 2026  
**Prepared by:** Product Management Team  
**Status:** Draft — For Workshop Use

---

## 1. Executive Summary

Contoso Financial Services requires a cloud-hosted **Expense Management and Financial Analytics Platform** that allows employees to submit, approve, and track expense claims, while giving finance managers real-time visibility into spending trends via Power BI dashboards.

The current process is entirely manual (Excel + email), resulting in a 3-week reimbursement cycle, frequent data entry errors, and no consolidated spending view for leadership.

---

## 2. Business Objectives

1. Reduce the expense reimbursement cycle from **21 days to under 5 days**
2. Eliminate manual data entry errors by automating receipt digitisation using OCR
3. Provide finance managers with a real-time spend analytics dashboard
4. Enforce company spending policies automatically (e.g., meal limits, category caps)
5. Ensure full audit trail for compliance and external audits
6. Integrate with the existing **SAP HR system** for employee data
7. Deploy to **Microsoft Azure** with enterprise security standards

---

## 3. Stakeholders

| Role | Name / Team | Interest |
|------|-------------|----------|
| Project Sponsor | CFO — Sarah Mitchell | ROI, compliance, cost reduction |
| Primary Users | All 2,500 employees | Easy expense submission |
| Finance Managers | Finance Dept (45 people) | Approval workflow, dashboards |
| IT / Security | Cloud Platform Team | Azure deployment, security |
| External Auditors | KPMG | Audit trail, data export |

---

## 4. Scope

### In Scope
- Web application (desktop + mobile-responsive)
- Employee expense submission (manual entry + receipt photo upload)
- OCR-based receipt scanning (extract vendor, date, amount)
- Multi-level approval workflow (Line Manager → Finance Controller)
- Push/email notifications for submission, approval, rejection, payment
- Company policy engine (flag/reject expenses violating limits)
- Finance Manager approval dashboard
- Power BI analytics (spend by category, department, period)
- Azure Data Factory pipeline for SAP HR integration
- Microsoft Entra ID (Azure AD) Single Sign-On
- Export to CSV/Excel for payroll processing
- Full audit log of all actions

### Out of Scope
- Mobile native app (iOS/Android) — Phase 2
- Integration with accounting software (SAP FI) — Phase 2
- Multi-currency support — Phase 2
- Travel booking integration — Future consideration

---

## 5. Functional Requirements

| ID | Requirement | Description | Priority |
|----|-------------|-------------|----------|
| FR-01 | Employee Authentication | Login via Microsoft Entra ID SSO. No local passwords. | High |
| FR-02 | Expense Submission | Employee fills a form: expense type, date, amount, currency (GBP default), description, receipt upload (JPEG/PNG/PDF, max 5MB). | High |
| FR-03 | OCR Receipt Scanning | On receipt upload, auto-extract: vendor name, transaction date, total amount. Pre-fill the form fields. Confidence score shown. | High |
| FR-04 | Policy Engine | Before submission, validate against rules: (a) Meals ≤ £50/day, (b) Hotel ≤ £200/night, (c) Electronics require pre-approval. Flag violations; block if hard limit exceeded. | High |
| FR-05 | Submission Confirmation | After submit, employee gets email + in-app confirmation with a unique claim reference (e.g., EXP-2026-00123). | Medium |
| FR-06 | Manager Approval | Line Manager sees pending expenses in their queue. Can Approve, Reject (with mandatory reason), or Request More Info. | High |
| FR-07 | Finance Controller Review | After manager approval, Finance Controller does final review before marking as "Approved for Payment". | High |
| FR-08 | Payment Processing | Finance exports approved claims as CSV for payroll. System marks records as "Paid" on confirmation. | High |
| FR-09 | Notifications | Email + in-app notifications for: (a) submission received, (b) approved, (c) rejected (with reason), (d) paid. | Medium |
| FR-10 | Audit Trail | Every action (submit, view, approve, reject, edit, delete) is logged with: user, timestamp, previous value, new value. Immutable. | High |
| FR-11 | Employee Dashboard | Employee sees their submissions: status, amount, date submitted, expected payment date. Filter by status and date range. | Medium |
| FR-12 | Finance Analytics Dashboard | Power BI embedded report showing: total spend by category, department, period; top 10 spenders; policy violations; pending approvals count. | High |
| FR-13 | SAP HR Integration | Daily sync of employee data (name, department, manager hierarchy, cost centre) from SAP via Azure Data Factory pipeline. | High |
| FR-14 | Role-Based Access | Roles: Employee, Line Manager, Finance Controller, Finance Admin, System Admin. Each role sees and can do different things. | High |
| FR-15 | Receipt Storage | Receipts stored in Azure Blob Storage. Accessible only by the submitting employee, their approvers, and Finance Admin. | High |
| FR-16 | Data Export | Any table/list in the system can be exported to CSV or Excel by authorised users. | Low |
| FR-17 | System Administration | Admin can configure: expense categories, policy rules (amounts, limits), notification templates, approval chain configuration. | Medium |

---

## 6. Non-Functional Requirements

| ID | Category | Requirement |
|----|----------|-------------|
| NFR-01 | Performance | Page load < 2 seconds on 10 Mbps connection. API response < 500ms for 95th percentile. |
| NFR-02 | Scalability | Support 2,500 concurrent users. Scale to 10,000 with no architectural changes. |
| NFR-03 | Availability | 99.9% uptime SLA. Planned maintenance outside 08:00–18:00 BST. |
| NFR-04 | Security | OWASP Top 10 compliance. Data encrypted at rest (AES-256) and in transit (TLS 1.2+). |
| NFR-05 | Compliance | GDPR compliant. Data residency in UK South Azure region. Audit logs retained 7 years. |
| NFR-06 | Accessibility | WCAG 2.1 AA compliant web application. |
| NFR-07 | Browser Support | Chrome 120+, Edge 120+, Firefox 115+, Safari 17+. |
| NFR-08 | Mobile | Fully responsive layout working on screens ≥ 375px width. |

---

## 7. Constraints & Assumptions

**Constraints:**
- Budget: £450,000 total (including Azure infrastructure)
- Timeline: Must be live within 6 months
- All data must remain within UK Azure regions
- Must use Microsoft Entra ID (existing enterprise licence)
- Team size: 8 engineers (2 FE, 3 BE, 1 Data, 1 SRE, 1 QA + 1 PM)

**Assumptions:**
- SAP HR system exposes a REST API or SFTP feed for data sync
- OCR will be implemented using Azure AI Document Intelligence (Form Recognizer)
- Power BI Premium licence is available for embedded reports
- Employees have access to Microsoft Outlook for email notifications

---

## 8. Success Metrics

| Metric | Baseline | Target |
|--------|----------|--------|
| Expense cycle time | 21 days | ≤ 5 days |
| Data entry errors | ~12% of submissions | < 1% |
| Employee satisfaction (survey) | Not measured | ≥ 80% satisfied |
| Finance team time on expense processing | 40 hrs/week | ≤ 10 hrs/week |
| System availability | N/A | ≥ 99.9% |
| Audit finding related to expenses | 3 in last audit | 0 |

---

## 9. High-Level Timeline Expectations

| Phase | Duration |
|-------|----------|
| Discovery & Design | 4 weeks |
| Development Sprint 1–4 | 8 weeks |
| Testing & UAT | 3 weeks |
| Deployment & Go-Live | 1 week |
| Hypercare | 2 weeks |
| **Total** | **~18 weeks** |

---

*This document is a sample BRD provided for workshop purposes.*  
*Replace with your actual BRD before running the Copilot pipeline.*

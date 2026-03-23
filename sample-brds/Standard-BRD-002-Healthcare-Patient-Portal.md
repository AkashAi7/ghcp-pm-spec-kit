# Business Requirements Document (Standard)
## BRD-002-S: Healthcare Patient Management Portal

| Field | Value |
|-------|-------|
| **Document ID** | BRD-002-S |
| **Version** | 1.0 |
| **Status** | Approved |
| **Date Created** | 2026-03-22 |
| **Last Revised** | 2026-03-22 |
| **Project Code** | HEALTH-2026 |
| **Business Sponsor** | Chief Medical Officer |
| **Document Owner** | Healthcare Product Management |
| **Review Cycle** | Quarterly / After Regulatory Changes |

---

## Document Control

| Version | Date | Author | Changes |
|---------|------|--------|---------|
| 0.1 | 2026-01-10 | Business Analyst | Initial draft |
| 0.8 | 2026-02-20 | Business Analyst | Clinical stakeholder review |
| 1.0 | 2026-03-22 | Product Manager | Final approval |

---

## Table of Contents

1. Executive Summary  
2. Business Context & Problem Statement  
3. Business Objectives & Success Criteria  
4. Stakeholders  
5. Current State Analysis  
6. Future State Vision  
7. Business Requirements  
8. Functional Requirements  
9. Non-Functional Requirements  
10. Assumptions  
11. Constraints  
12. Dependencies  
13. Risks & Mitigations  
14. Glossary  
15. Approval & Sign-off  

---

## 1. Executive Summary

The healthcare organization operates across seven clinic locations and currently lacks a unified digital platform for managing patient registration, appointment scheduling, medical records access, and care team communication. Patient administrative work is primarily paper-based or managed through three incompatible legacy systems, resulting in data silos, scheduling errors, and significant staff overhead.

This project will deliver a HIPAA-compliant, cloud-hosted Patient Management Portal that empowers patients to manage their own healthcare journey — booking appointments, viewing test results, messaging their care team, and accessing their medical history — while enabling clinical and administrative staff to serve patients more efficiently from a single, secure platform.

The portal is expected to reduce administrative overhead by 35%, increase patient self-service adoption to 70%, and deliver measurable improvements in patient experience scores (target: HCAHPS score improvement of 12 points) within the first 12 months post-launch.

---

## 2. Business Context & Problem Statement

### 2.1 Background

The organization operates seven clinic sites supporting approximately 45,000 active patients. Appointments are managed through a scheduling system that does not communicate with the electronic health record (EHR) system. Patient intake requires physical paper forms. Test results are telephoned or mailed to patients. Between-visit communication is handled by phone only, creating bottlenecks at front desk and contributing to staff burnout.

### 2.2 Problem Statement

**The healthcare organization lacks a unified digital patient engagement platform, resulting in fragmented care coordination, excessive administrative burden on clinical staff, and a poor patient experience that does not meet current healthcare consumer expectations.**

### 2.3 Business Drivers

| Driver | Description |
|--------|-------------|
| Patient Experience | HCAHPS scores 14% below national average; patient complaints rising 8% YoY |
| Staff Efficiency | Administrative staff spending 60% of time on phone-based scheduling and record requests |
| Regulatory Readiness | CMS promoting patient data access via 21st Century Cures Act requirements |
| Competitive Positioning | Three regional competitors have launched patient portals in the last 18 months |
| Cost Reduction | Paper-based intake and results delivery costs estimated at $180,000/year |

---

## 3. Business Objectives & Success Criteria

### 3.1 Business Objectives

| ID | Objective | Priority |
|----|-----------|----------|
| BO-01 | Enable patients to self-schedule, reschedule, and cancel appointments online | High |
| BO-02 | Allow patients to access their medical records, test results, and visit summaries digitally | High |
| BO-03 | Reduce paper-based patient intake by replacing physical forms with digital equivalents | High |
| BO-04 | Provide a secure, HIPAA-compliant messaging channel between patients and care teams | High |
| BO-05 | Increase staff efficiency by consolidating patient management into a single platform | Medium |
| BO-06 | Enable clinical leadership to track operational metrics and patient experience KPIs | Medium |

### 3.2 Success Criteria (KPIs)

| Objective | KPI | Baseline | Target (12 months) |
|-----------|-----|----------|--------------------|
| BO-01 | % of appointments booked online | 8% | 60% |
| BO-02 | Patient portal active users (registered + logged in last 30 days) | 0 | 35,000 |
| BO-03 | Paper intake forms eliminated | 0% | 80% |
| BO-04 | Avg. response time to patient messages | Phone call only | ≤ 24 business hours |
| BO-05 | Admin staff time spent on scheduling calls | 60% of daily hours | ≤ 30% |
| BO-06 | HCAHPS overall satisfaction score | Baseline (current avg) | +12 points |

---

## 4. Stakeholders

### 4.1 Stakeholder Register

| Stakeholder | Role | Organization | Interest | Influence | Engagement |
|-------------|------|--------------|----------|-----------|------------|
| Chief Medical Officer | Executive Sponsor | Internal | Clinical quality, patient outcomes | High | Approver |
| Chief Information Officer | Technical Sponsor | Internal | Platform security, integration, infrastructure | High | Approver |
| Chief Compliance Officer | Stakeholder | Internal | HIPAA, 21st Century Cures Act compliance | High | Approver |
| Clinic Operations Director | Business Owner | Internal | Staff efficiency, workflow improvement | High | Consulted |
| Primary Care Physicians | End User (Clinical) | Internal | Ease of use, clinical accuracy, notifications | High | Consulted |
| Nurses / Medical Assistants | End User (Clinical) | Internal | Workflow support, communication tools | High | Consulted |
| Front Desk / Admin Staff | End User (Admin) | Internal | Scheduling, intake, communications management | High | Consulted |
| Patients | End User | External | Access to records, convenience, privacy | High | User testing |
| IT Security Team | Stakeholder | Internal | PHI protection, access controls | High | Reviewed |
| Legal Counsel | Stakeholder | Internal | HIPAA, BAAs, liability | Medium | Consulted |

### 4.2 Approval Authority

| Decision | Approval Authority |
|----------|-------------------|
| BRD approval | CMO, CIO, Chief Compliance Officer |
| Scope changes | CMO + Steering Committee |
| Go-live readiness | CMO + CIO + Compliance Officer |
| HIPAA compliance certification | Chief Compliance Officer + Legal |

---

## 5. Current State Analysis

### 5.1 Current Process: Appointment Booking

```
[Patient calls clinic front desk]
         ↓
[Admin staff manually checks provider availability in scheduling system]
         ↓
[Appointment booked verbally — confirmation mailed or called back]
         ↓
[Patient arrives — paper intake forms completed in waiting room]
         ↓
[Admin staff manually enters form data into EHR]
```

### 5.2 Current State Pain Points

| Pain Point | Business Impact |
|------------|----------------|
| No 24/7 appointment booking channel | Lost appointments after hours; 18% of calls unanswered |
| Paper intake forms | 8–12 minutes per patient for data re-entry; transcription errors |
| Test results delivered by phone/mail only | 3–7 day delay in results access; patient anxiety |
| No digital messaging | Front desk receives 200+ non-urgent calls/day; staff burnout |
| Multiple disconnected systems | Staff must toggle between 3 systems to complete one patient interaction |
| No patient-visible visit history | 25% of visits include re-telling medical history already on file |

### 5.3 Compliance Gaps in Current State

| Compliance Requirement | Current Status |
|------------------------|---------------|
| 21st Century Cures Act — patient data access within 24 hours | Non-compliant: results take 3–7 days |
| HIPAA audit logging | Partial: EHR has logs, scheduling system does not |
| Patient right to correct records | Manual process; no digital mechanism |

---

## 6. Future State Vision

### 6.1 Vision Statement

> *"A consumer-grade digital health experience that puts patients in control of their care while freeing clinical staff to focus on what matters most — patient health outcomes."*

### 6.2 Future State: Patient Journey

```
[Patient registers via portal (one-time — identity verified)]
         ↓
[Patient books appointment online — real-time provider availability]
         ↓
[Patient completes digital intake forms before visit]
         ↓
[Patient receives automated appointment reminders]
         ↓
[Post-visit: test results available in portal within 24 hours]
         ↓
[Patient messages care team with non-urgent questions]
         ↓
[Care team responds via secure portal within 24 business hours]
         ↓
[Patient and clinician review visit summary and care plan online]
```

---

## 7. Business Requirements

### 7.1 Patient Self-Service

| ID | Business Requirement | Priority | Source |
|----|----------------------|----------|--------|
| BR-PS-01 | The business shall allow patients to create a verified digital identity on the portal | Must Have | CMO / Compliance |
| BR-PS-02 | The business shall allow patients to book, reschedule, and cancel appointments with available providers at any time | Must Have | Clinic Operations |
| BR-PS-03 | The business shall allow patients to view their medical history, diagnoses, medications, allergies, and immunizations | Must Have | 21st Century Cures Act |
| BR-PS-04 | The business shall allow patients to view laboratory results and diagnostic reports within 24 hours of release by a clinician | Must Have | 21st Century Cures Act |
| BR-PS-05 | The business shall allow patients to download and share their medical records in a standard digital format | Must Have | 21st Century Cures Act |
| BR-PS-06 | The business shall allow patients to complete pre-visit intake forms digitally before their appointment | Must Have | Clinic Operations |
| BR-PS-07 | The business shall send patients automated reminders for upcoming appointments at configurable intervals | Should Have | Clinic Operations |

### 7.2 Care Team Tools

| ID | Business Requirement | Priority | Source |
|----|----------------------|----------|--------|
| BR-CT-01 | The business shall allow authorized clinical staff to view a consolidated patient record within the portal | Must Have | Physicians |
| BR-CT-02 | The business shall allow care teams to send and receive secure messages with patients | Must Have | Nurses / MAs |
| BR-CT-03 | The business shall allow clinicians to release test results to the patient portal with an optional clinician note | Must Have | 21st Century Cures Act |
| BR-CT-04 | The business shall notify care team members when a patient sends a new message | Must Have | Clinic Operations |
| BR-CT-05 | The business shall allow clinical staff to create and share after-visit summaries and care plans with patients | Should Have | Physicians |

### 7.3 Administration & Operations

| ID | Business Requirement | Priority | Source |
|----|----------------------|----------|--------|
| BR-AO-01 | The business shall provide administrative staff with a scheduling dashboard showing daily appointments across all providers | Must Have | Clinic Operations |
| BR-AO-02 | The business shall enable administrative staff to manage patient registrations and resolve identity verification issues | Must Have | Clinic Operations |
| BR-AO-03 | The business shall provide clinic directors with dashboards showing appointment volumes, no-show rates, and patient satisfaction scores | Should Have | CMO |
| BR-AO-04 | The business shall produce automated no-show reports and enable staff to send follow-up outreach to patients who missed appointments | Could Have | Clinic Operations |

### 7.4 Compliance & Privacy

| ID | Business Requirement | Priority | Source |
|----|----------------------|----------|--------|
| BR-CP-01 | The business shall ensure all patient health information (PHI) is stored and transmitted in compliance with HIPAA | Must Have | Compliance Officer |
| BR-CP-02 | The business shall maintain a complete, auditable log of all access to patient health information | Must Have | Compliance Officer |
| BR-CP-03 | The business shall allow patients to request corrections to their medical records per HIPAA rights | Must Have | Legal / Compliance |
| BR-CP-04 | The business shall obtain and record patient consent for the terms of portal data use prior to portal activation | Must Have | Legal |
| BR-CP-05 | The business shall support the patient's right to restrict sharing of their information with specific providers | Should Have | Legal / Compliance |

---

## 8. Functional Requirements

### 8.1 Patient Registration & Identity

| ID | Functional Requirement | Linked BR | Priority |
|----|------------------------|-----------|----------|
| FR-PI-01 | The system shall present a patient registration flow collecting name, date of birth, contact details, and insurance information | BR-PS-01 | Must Have |
| FR-PI-02 | The system shall verify patient identity by cross-referencing registration data against EHR records | BR-PS-01 | Must Have |
| FR-PI-03 | The system shall support multi-factor authentication for all patient logins | BR-PS-01, BR-CP-01 | Must Have |
| FR-PI-04 | The system shall allow patients to designate an authorized representative (e.g., parent, guardian, caregiver) | BR-PS-01 | Should Have |

### 8.2 Appointment Management

| ID | Functional Requirement | Linked BR | Priority |
|----|------------------------|-----------|----------|
| FR-AM-01 | The system shall display real-time provider availability and allow patients to select a date, time, and appointment type | BR-PS-02 | Must Have |
| FR-AM-02 | The system shall confirm bookings instantly and send a confirmation to the patient via email and/or SMS | BR-PS-02 | Must Have |
| FR-AM-03 | The system shall send automated reminders at 48 hours and 2 hours before appointment | BR-PS-07 | Should Have |
| FR-AM-04 | The system shall allow patients to cancel or reschedule up to 2 hours before the appointment | BR-PS-02 | Must Have |
| FR-AM-05 | The system shall display an admin scheduling view by provider, location, and date | BR-AO-01 | Must Have |

### 8.3 Medical Records Access

| ID | Functional Requirement | Linked BR | Priority |
|----|------------------------|-----------|----------|
| FR-MR-01 | The system shall display a patient's FHIR-structured health summary including conditions, medications, allergies, and immunizations | BR-PS-03 | Must Have |
| FR-MR-02 | The system shall display released lab results with result values, reference ranges, and optional clinician commentary | BR-PS-04 | Must Have |
| FR-MR-03 | The system shall allow patients to download their health records in FHIR R4 JSON or PDF format | BR-PS-05 | Must Have |
| FR-MR-04 | The system shall allow patients to submit a formal amendment request for review by the clinical team | BR-CP-03 | Must Have |

### 8.4 Secure Messaging

| ID | Functional Requirement | Linked BR | Priority |
|----|------------------------|-----------|----------|
| FR-SM-01 | The system shall provide an asynchronous, end-to-end encrypted messaging thread between patient and care team | BR-PS-02 (implied), BR-CT-02 | Must Have |
| FR-SM-02 | The system shall display a message triage queue for nursing staff, with the ability to assign messages to providers | BR-CT-02, BR-CT-04 | Must Have |
| FR-SM-03 | The system shall not be used for urgent clinical communications — the system shall display a persistent notice directing emergencies to 911 | Safety | Must Have |

---

## 9. Non-Functional Requirements

| Category | ID | Requirement | Target |
|----------|----|-------------|--------|
| **Security** | NFR-SE-01 | All PHI must be encrypted at rest and in transit using FIPS 140-2 validated cryptography | FIPS 140-2 compliant |
| **Security** | NFR-SE-02 | All access to PHI must require authenticated sessions with automatic timeout after inactivity | 15-minute session timeout |
| **Security** | NFR-SE-03 | Annual third-party penetration testing shall be conducted on the platform | Annual pen test |
| **Compliance** | NFR-C-01 | Platform must comply with HIPAA Privacy and Security Rules | HIPAA compliant |
| **Compliance** | NFR-C-02 | Platform must comply with the 21st Century Cures Act patient data access requirements | 21CC compliant |
| **Compliance** | NFR-C-03 | All Business Associate Agreements (BAAs) must be in place with all third-party vendors who access PHI | BAAs executed |
| **Availability** | NFR-A-01 | Portal shall be available to patients 24/7 | ≥ 99.9% monthly |
| **Availability** | NFR-A-02 | Planned maintenance shall be scheduled outside of 6 AM–10 PM local time | Off-hours maintenance |
| **Performance** | NFR-P-01 | Patient portal pages shall load fully within 3 seconds on standard broadband | < 3s p95 |
| **Performance** | NFR-P-02 | Appointment booking shall complete (search to confirmation) within 5 seconds | < 5s p95 |
| **Scalability** | NFR-S-01 | Platform shall support 50,000 simultaneous users without performance degradation | 50,000 concurrent |
| **Usability** | NFR-U-01 | Portal shall be accessible per WCAG 2.1 Level AA | WCAG 2.1 AA |
| **Usability** | NFR-U-02 | Portal shall be usable on smartphones without requiring an app download | Mobile browser |
| **Auditability** | NFR-AU-01 | All PHI access events shall be logged with user identity, record accessed, and timestamp | 100% PHI access logged |
| **Auditability** | NFR-AU-02 | Audit logs shall be retained for a minimum of 6 years per HIPAA requirements | ≥ 6-year log retention |
| **Recoverability** | NFR-R-01 | System shall recover to full operation within 4 hours of major failure | RTO ≤ 4 hours |
| **Recoverability** | NFR-R-02 | Maximum data loss in any failure scenario shall not exceed 1 hour | RPO ≤ 1 hour |

---

## 10. Assumptions

| ID | Assumption |
|----|------------|
| ASM-01 | The existing EHR system exposes a standards-based API (HL7 FHIR R4) for patient data read access |
| ASM-02 | All clinicians and staff will receive training on the portal prior to go-live |
| ASM-03 | Patients have access to internet-connected devices (smartphones or computers) |
| ASM-04 | The organization will notify all active patients of the portal launch through existing communication channels |
| ASM-05 | Legal counsel will provide guidance on state-specific consent laws that may affect portal access |
| ASM-06 | Insurance eligibility verification integration with payers is out of scope for Phase 1 |
| ASM-07 | Telemedicine (video visit) capability is out of scope for Phase 1 |

---

## 11. Constraints

| ID | Constraint | Impact |
|----|------------|--------|
| CON-01 | Platform must go live within 9 months from project approval | Phased rollout may be required |
| CON-02 | Total project budget is $900,000 | Feature prioritization required |
| CON-03 | All PHI must reside within US data centers | Restricts hosting provider and region |
| CON-04 | EHR integration must use existing FHIR APIs only — no direct database access allowed | Limits data write-back capability |
| CON-05 | Platform must be accessible via the organization's existing patient identity framework | Constrains identity provider selection |
| CON-06 | Phase 1 must cover all 7 clinic locations simultaneously | No phased rollout by location |
| CON-07 | All third-party vendors processing PHI must sign a Business Associate Agreement prior to integration | Vendor selection may be restricted |

---

## 12. Dependencies

| ID | Dependency | Type | Owner | Due Date |
|----|-----------|------|-------|----------|
| DEP-01 | EHR vendor provides FHIR R4 sandbox API access | External | IT / EHR Vendor | Week 2 |
| DEP-02 | HIPAA Security Risk Assessment completed | Internal | Compliance | Week 4 |
| DEP-03 | Business Associate Agreements signed with all cloud and third-party vendors | Internal | Legal | Week 6 |
| DEP-04 | Patient communication plan approved for portal launch notification | Internal | Marketing | Week 8 |
| DEP-05 | Staff training curriculum developed and delivered | Internal | HR / Clinic Ops | Week 14 |
| DEP-06 | Identity verification methodology approved by Compliance and Legal | Internal | Compliance | Week 3 |

---

## 13. Risks & Mitigations

| ID | Risk | Probability | Impact | Level | Mitigation |
|----|------|-------------|--------|-------|-----------|
| RSK-01 | Low patient portal adoption — patients prefer calling | High | High | High | Run portal awareness campaign; incentivize first login; train staff to promote portal during visits |
| RSK-02 | EHR integration fails or produces inaccurate clinical data | Medium | Critical | Critical | Engage EHR vendor's integration team; validate all data against source EHR in UAT |
| RSK-03 | HIPAA breach due to unauthorized PHI access | Low | Critical | High | Implement zero-trust access, MFA, PHI audit logging, annual pen testing |
| RSK-04 | Clinician resistance to new workflow | Medium | High | High | Involve physician champions in design; pilot with 1 willing provider team |
| RSK-05 | Messaging channel misused for urgent clinical communications | Medium | High | High | Display prominent emergency redirect warning; exclude triage functionality |
| RSK-06 | Scope creep from EHR vendor feature requests | High | Medium | High | Enforce scope boundary at BRD sign-off; formal change request process |
| RSK-07 | 21st Century Cures Act compliance missed at launch | Low | Critical | High | Engage compliance consultant; validate information-blocking requirements in UAT |

---

## 14. Glossary

| Term | Definition |
|------|-----------|
| **PHI** | Protected Health Information — individually identifiable health data covered by HIPAA |
| **HIPAA** | Health Insurance Portability and Accountability Act — US federal law protecting patient health information |
| **EHR** | Electronic Health Record — clinician-managed digital health record system |
| **FHIR** | Fast Healthcare Interoperability Resources — HL7 standard for exchanging healthcare information electronically |
| **MFA** | Multi-Factor Authentication — security practice requiring two or more verification factors |
| **BAA** | Business Associate Agreement — HIPAA-mandated contract between covered entities and vendors accessing PHI |
| **HCAHPS** | Hospital Consumer Assessment of Healthcare Providers and Systems — standardized patient satisfaction survey |
| **21st Century Cures Act** | US law requiring healthcare organizations to provide patients timely access to their complete health records |
| **Information Blocking** | Practice of interfering with patient access to health records — prohibited under 21st Century Cures Act |
| **Care Team** | Physicians, nurses, medical assistants, and other clinical staff directly involved in patient care |
| **UAT** | User Acceptance Testing — validation by clinical and admin staff that the system meets requirements |

---

## 15. Approval & Sign-off

| Role | Name | Signature | Date |
|------|------|-----------|------|
| Chief Medical Officer (Sponsor) | | | |
| Chief Information Officer | | | |
| Chief Compliance Officer | | | |
| Clinic Operations Director | | | |
| IT Security Lead | | | |
| Legal Counsel | | | |

---

*This document is subject to change control. Changes after approval require a formal Change Request approved by the CMO and Compliance Officer.*

*Companion Technical Document: [BRD-002-Healthcare-Patient-Portal.md](BRD-002-Healthcare-Patient-Portal.md)*

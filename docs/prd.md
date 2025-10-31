# Product Requirements Document (PRD)
# Non-Expert Insider Threat Demo Platform

**Version**: 1.0
**Date**: 2025-10-31
**Status**: Draft - Ready for Review
**Owner**: Product Management
**Stakeholders**: Engineering, Design, Sales, Marketing, Executive Team

---

## Document Control

| Version | Date | Author | Changes |
|---------|------|--------|---------|
| 1.0 | 2025-10-31 | Mary (Business Analyst) | Initial PRD from co-elicitation session |

---

## Executive Summary

### Product Vision

Build a demo and educational platform that guides organizations through establishing insider threat programs from zero to operational maturity, providing value through program development metrics rather than requiring historical incident data.

### Problem Statement

Organizations recognize insider threat risks but cannot establish programs due to a chicken-and-egg problem: traditional tools require incident data to demonstrate value, but organizations cannot generate meaningful data without established programs. This leaves 10,000+ organizations unable to justify or implement insider threat capabilities.

### Solution Overview

An adaptive platform that evolves with program maturity, providing:
- **Month 0-4**: Program approval tools, policy analysis, quick wins (zero-incident value)
- **Month 4-7**: DLP integration, first incident logging, early detection metrics
- **Month 8-12**: Full KPI dashboard, trend analysis, mature program capabilities

### Success Metrics

**Business Goals**:
- 100-500 customers Year 1 (conservative to aggressive)
- $1.2M-$9M ARR
- >75% retention rate
- >40% demo-to-engagement conversion

**User Goals**:
- >70% program approval within 30 days
- >80% DLP deployment on schedule (Month 4)
- >80% training completion
- <7 months to first incident detection

---

## Product Overview

### Product Type

**Hybrid Platform**: Demo + Educational + SaaS Product
- **Demo**: Flexible demonstration modes for sales enablement
- **Educational**: Guided journey with best practices and templates
- **Product**: Production-capable insider threat program management

### Target Users

#### Primary Personas

**Persona 1: The New CISO**
- **Profile**: Recently appointed, inheriting security program with gaps
- **Goals**: Quick program justification, realistic timeline, budget approval
- **Pain Points**: No incident history, board asking questions, limited time
- **Success Metric**: Board approval within 30 days

**Persona 2: The Risk Officer**
- **Profile**: Compliance-focused, identifies insider risk gap during audit
- **Goals**: Business case development, regulatory mapping, ROI projections
- **Pain Points**: No technical background, needs credible data
- **Success Metric**: Executive buy-in and budget allocation

**Persona 3: The IT Manager**
- **Profile**: Wearing security hat, no dedicated team, limited budget
- **Goals**: Quick wins, leverage existing tools (Purview), simple deployment
- **Pain Points**: Limited time and resources, DIY approach required
- **Success Metric**: Something operational in 90 days

#### Secondary Personas

**Persona 4: Board Member**
- **Profile**: Executive oversight, approves budgets
- **Goals**: Understand risk, see ROI, ensure compliance
- **Pain Points**: Technical complexity, unclear value
- **Success Metric**: Clear dashboard showing program maturity

**Persona 5: Security Analyst**
- **Profile**: Day-to-day operator, investigates incidents
- **Goals**: Easy incident logging, clear workflows, actionable alerts
- **Pain Points**: Too many false positives, unclear procedures
- **Success Metric**: MTTD and MTTR improving over time

### User Journey Map

```
Discovery → Evaluation → Approval → Onboarding → Quick Wins → DLP Deploy → Maturation
(Week 0)   (Week 1-2)   (Week 2-4)  (Week 4)     (Week 4-8)   (Month 4)    (Month 4-12)

├─ Problem awareness
├─ Demo request
├─ Priority Picker
├─ PPTX generation
├─ Board presentation
├─ Budget approval
├─ Account creation
├─ AI policy analysis
├─ Deploy human channels
├─ Launch training
├─ DLP vendor selection
├─ DLP configuration
├─ DLP deployment
├─ First incidents logged
└─ Full program operational
```

---

## Market Analysis

### Market Opportunity

**Total Addressable Market (TAM)**:
- 50,000+ US organizations with 100+ employees lacking insider threat programs
- Average willingness to pay: $10k-$50k/year
- TAM Size: $500M-$2.5B annually

**Serviceable Addressable Market (SAM)**:
- 10,000+ organizations actively seeking security improvements
- Realistic penetration: 10-20% over 3 years
- SAM Size: $100M-$500M

**Serviceable Obtainable Market (SOM)**:
- Year 1: 100-500 customers = $1.2M-$9M ARR
- Year 2: 600 customers = $9M ARR
- Year 3: 1,100 customers = $16.65M ARR

### Competitive Landscape

**Direct Competitors** (Mature program focus):
1. **Splunk Enterprise Security** - $150k+/year, requires 100s of incidents
2. **Exabeam (UEBA)** - $100k+/year, behavioral analytics focus
3. **Securonix** - $120k+/year, cloud-native SIEM with insider threat module
4. **Forcepoint Insider Threat** - $80k+/year, DLP + behavioral monitoring
5. **ObserveIT (Proofpoint)** - $60k+/year, user activity monitoring

**Indirect Competitors** (Adjacent tools):
- Microsoft Defender for Cloud Apps - $5-10/user/month (part of E5)
- Varonis - $50k+/year (data security platform)
- Code42 Incydr - $40k+/year (data risk management)

**Our Competitive Advantages**:
1. ✅ **Zero-incident focus** - Value without historical data
2. ✅ **AI Policy Gap Analysis** - Unique, immediate value (60 seconds)
3. ✅ **Program Approval Tools** - PPTX generator, Priority Picker (no competitor has this)
4. ✅ **Purview Detection** - Identify free/cheap DLP (saves $15k-$25k)
5. ✅ **Educational Journey** - Guided implementation, not just a tool
6. ✅ **SMB-Friendly Pricing** - $6k-$36k/year vs. $60k-$150k+
7. ✅ **Quick Time-to-Value** - Days for quick wins vs. months for traditional tools

### Market Validation

**Assumptions to Validate** (MVP Phase):
1. Organizations struggle to justify insider threat programs without data ✅ (from co-elicitation)
2. PPTX generator saves 2+ weeks of manual work ⚠️ (needs validation)
3. AI policy analysis is 85%+ accurate ⚠️ (needs validation)
4. Many orgs don't know they have Purview ✅ (industry observation)
5. >70% of demos lead to engagement ⚠️ (needs validation)

**Validation Plan**:
- Interview 20 target users (10 CISOs, 5 Risk Officers, 5 IT Managers)
- Demo Priority Picker + PPTX concept to 10 prospects
- Pilot AI policy analysis with 5 real policy sets
- Track demo-to-engagement rate in first 3 months

---

## Product Requirements

### Functional Requirements

#### Epic 1: User Onboarding & Discovery (Priority: P0)

**FR-1.1: Priority Picker**
- **Description**: Interactive 10-question decision tree that triages users and collects organizational data
- **Acceptance Criteria**:
  - [ ] Presents 10 questions in logical order
  - [ ] Supports Yes/No, Multiple Choice, Range inputs
  - [ ] Calculates sophistication tier (Basic/Intermediate/Advanced)
  - [ ] Recommends starting path (Policy Dev, Risk Assessment, Quick Win)
  - [ ] Detects Purview availability (if M365 E5/A5)
  - [ ] Triggers PPTX generation with collected data
  - [ ] Saves responses for later reference
- **User Stories**: US-1.1 through US-1.7 (see Epic details)

**FR-1.2: Program Approval PPTX Generator**
- **Description**: Auto-generates customized 8-slide board presentation
- **Acceptance Criteria**:
  - [ ] Generates all 8 slides with no placeholders
  - [ ] Customizes budget estimates based on org size and tier
  - [ ] Highlights Purview if E5/A5 detected (cost = $0)
  - [ ] Includes industry-specific risk scenarios
  - [ ] Exports as editable .pptx file
  - [ ] Completes generation in <5 seconds
- **User Stories**: US-1.8 through US-1.12

**FR-1.3: Account Creation & Setup**
- **Description**: User registration, team setup, initial configuration
- **Acceptance Criteria**:
  - [ ] Email/password or SSO authentication
  - [ ] Organization profile creation
  - [ ] Team member invitations (role-based)
  - [ ] Industry selection (for content customization)
  - [ ] Email verification
- **User Stories**: US-1.13 through US-1.15

---

#### Epic 2: Quick Wins - Pre-DLP Value (Priority: P0)

**FR-2.1: AI Policy Gap Analysis Tool**
- **Description**: Upload policies, get AI-powered insider threat gap analysis in 60 seconds
- **Acceptance Criteria**:
  - [ ] Accepts PDF, Word (.docx), text files (up to 10 files)
  - [ ] Extracts text from PDFs (OCR if needed)
  - [ ] Analyzes 4 categories: Data Handling, Access Controls, Monitoring, Behavioral/Cultural
  - [ ] Generates 5-section report: Executive Summary, Coverage Heatmap, Detailed Findings, Prioritized Recommendations, Policy Templates
  - [ ] Completes analysis in <60 seconds for 100 pages
  - [ ] Exports report to PDF and Word
  - [ ] Provides downloadable policy templates for gaps
  - [ ] Achieves >85% accuracy (validated against SME reviews)
- **User Stories**: US-2.1 through US-2.6

**FR-2.2: Policy Violation Self-Reporting Portal**
- **Description**: Employee-facing web form for safe concern reporting
- **Acceptance Criteria**:
  - [ ] Anonymous submission option
  - [ ] Authenticated submission option (with identity)
  - [ ] Captures: concern type, description (min 50 chars), date/time, affected person/dept, evidence upload
  - [ ] Generates unique ticket ID
  - [ ] Sends confirmation to submitter (if not anonymous)
  - [ ] Notifies security team
  - [ ] Integrates with incident logging system
- **User Stories**: US-2.7 through US-2.10

**FR-2.3: Manager Concern Submission Form**
- **Description**: Manager-only form for flagging risky employee behaviors
- **Acceptance Criteria**:
  - [ ] Requires manager authentication
  - [ ] Captures: employee name/ID, concern type, description (min 100 chars), duration, actions taken, urgency
  - [ ] Routes high urgency to security immediately
  - [ ] Routes medium urgency within 24 hours
  - [ ] Creates case in incident system
  - [ ] Notifies HR for performance-related concerns
- **User Stories**: US-2.11 through US-2.14

**FR-2.4: Automated HR Flag Triggers**
- **Description**: HRIS integration that auto-flags terminations, PIPs, disciplinary actions
- **Acceptance Criteria**:
  - [ ] Integrates with HRIS API or receives webhooks
  - [ ] Triggers on: terminations (voluntary/involuntary), PIPs, disciplinary actions, resignation notices, role changes
  - [ ] Creates incident ticket automatically
  - [ ] Assigns severity (Involuntary termination=High, Voluntary=Medium, PIP=Medium, Role change=Low)
  - [ ] Suggests actions (e.g., "Review access logs for past 30 days")
  - [ ] Restricts access to authorized personnel only
  - [ ] Logs all access to HR data
- **User Stories**: US-2.15 through US-2.18

---

#### Epic 3: Dashboard & Metrics - Adaptive (Priority: P0)

**FR-3.1: Zero-Incident Dashboard (Months 0-4)**
- **Description**: Dashboard showing program maturity without requiring incidents
- **Acceptance Criteria**:
  - [ ] Displays 7 core metrics: Program Maturity Score (0-100%), Policy Coverage %, Training Completion %, Compliance Checklist Progress, Risk Reduction Targets, Quick Win Channel Activity, DLP Deployment Readiness
  - [ ] Program Maturity Score calculates from phase completion
  - [ ] Visual gauge with color coding (Red <25%, Yellow 25-70%, Green >70%)
  - [ ] Updates in real-time as data changes
  - [ ] Responsive design (desktop, tablet, mobile)
- **User Stories**: US-3.1 through US-3.7

**FR-3.2: Early Detection Dashboard (Months 4-7)**
- **Description**: Adds incident tracking when DLP deployed
- **Acceptance Criteria**:
  - [ ] Displays incident count (cumulative and current month)
  - [ ] Shows incident source breakdown (pie/bar chart): % from DLP alerts, employee reports, manager escalations, HR referrals, IT security alerts
  - [ ] Displays early MTTD/MTTR (Mean Time To Detect/Respond in days)
  - [ ] Shows alert volume trends
  - [ ] Shows false positive rate
- **User Stories**: US-3.8 through US-3.12

**FR-3.3: Mature Dashboard (Months 8-12)**
- **Description**: Full KPI dashboard with all 10 metrics from Barclays PoC
- **Acceptance Criteria**:
  - [ ] Displays all 10 KPIs: MTTD, MTTR, Training Completion %, False Positive Rate, Risk Reduction %, Detection Rate, NDR, Program Cost, Role Risk Score, Overall Security Posture
  - [ ] Shows incident trends over time (line charts)
  - [ ] Includes behavioral analytics (if UEBA deployed)
  - [ ] Shows predictive insights
  - [ ] Demonstrates ROI
- **User Stories**: US-3.13 through US-3.17

**FR-3.4: Dashboard Filtering & Export**
- **Description**: Filter and export dashboard data
- **Acceptance Criteria**:
  - [ ] Date range selection
  - [ ] Filter by department, role, severity
  - [ ] Export dashboard to PDF/image
  - [ ] Create custom views
  - [ ] Save favorite views
- **User Stories**: US-3.18 through US-3.20

---

#### Epic 4: Five-Phase Rollout Planner (Priority: P1)

**FR-4.1: Phase Management**
- **Description**: Interactive roadmap with 5 phases, task checklists, progress tracking
- **Acceptance Criteria**:
  - [ ] Displays all 5 phases: Foundation (Month 0), Scoping (Months 0-2), Prevention/Awareness (Months 2-4), Detection (Months 4-7), Governance (Months 8-12)
  - [ ] Shows current phase prominently
  - [ ] Displays task checklist for current phase
  - [ ] Allows marking tasks complete
  - [ ] Calculates phase completion %
  - [ ] Warns if falling behind schedule
  - [ ] Suggests next actions
- **User Stories**: US-4.1 through US-4.6

**FR-4.2: Timeline Visualization**
- **Description**: Gantt-style timeline showing 12-month roadmap
- **Acceptance Criteria**:
  - [ ] Displays 12-month timeline
  - [ ] Shows phase boundaries clearly
  - [ ] Highlights current position
  - [ ] Shows key milestones as markers
  - [ ] Allows zooming in/out
  - [ ] Exports to PDF
- **User Stories**: US-4.7 through US-4.9

---

#### Epic 5: Training & Awareness Module (Priority: P1)

**FR-5.1: Campaign Management**
- **Description**: Create, schedule, and execute training campaigns
- **Acceptance Criteria**:
  - [ ] Library of pre-built training modules (Insider Threat Awareness, Data Handling, Policy Acknowledgment, Recognizing Risky Behaviors, Reporting Mechanisms)
  - [ ] Create custom campaigns
  - [ ] Role-based assignment (all staff, managers only, IT only, etc.)
  - [ ] Schedule campaigns (start date, deadline)
  - [ ] Auto-enroll users based on role
  - [ ] Send launch announcement email
- **User Stories**: US-5.1 through US-5.6

**FR-5.2: Reminder System**
- **Description**: Automated reminders and escalations
- **Acceptance Criteria**:
  - [ ] Send reminders at 50%, 80% of time elapsed, 1 day before deadline, day of deadline
  - [ ] Escalate to manager if user overdue by 3+ days
  - [ ] Allow custom reminder schedules
  - [ ] Support SMS reminders (optional)
- **User Stories**: US-5.7 through US-5.9

**FR-5.3: Completion Tracking**
- **Description**: Track individual and aggregate training progress
- **Acceptance Criteria**:
  - [ ] Track individual progress (not started, in progress, completed)
  - [ ] Record completion date and time
  - [ ] Track quiz/assessment results (if applicable)
  - [ ] Calculate department rollup (% complete per dept)
  - [ ] Display on executive dashboard
  - [ ] Integrate with HRIS (if available)
- **User Stories**: US-5.10 through US-5.13

**FR-5.4: Training Reporting**
- **Description**: Generate completion and performance reports
- **Acceptance Criteria**:
  - [ ] Generate reports: Overall % complete, Completion by department, Completion by role, Overdue list, Quiz performance summary
  - [ ] Export to CSV/Excel
  - [ ] Visualize trends over time
- **User Stories**: US-5.14 through US-5.15

---

#### Epic 6: DLP Integration (Priority: P1)

**FR-6.1: Purview Detection & Configuration**
- **Description**: Auto-detect M365 Purview availability and provide setup guidance
- **Acceptance Criteria**:
  - [ ] Detect if user has O365 tenant
  - [ ] Query O365 license type (E5/A5/E3/A3)
  - [ ] Display Purview availability prominently
  - [ ] Provide activation instructions if not enabled
  - [ ] Link to Microsoft Purview portal
  - [ ] Provide DLP policy templates for insider threat
  - [ ] Suggest alert thresholds based on org size
  - [ ] Provide tuning guidance (reduce false positives)
- **User Stories**: US-6.1 through US-6.6

**FR-6.2: DLP Alert Integration**
- **Description**: Ingest DLP alerts and create incidents automatically
- **Acceptance Criteria**:
  - [ ] Ingest DLP alerts via API or webhook
  - [ ] Create incidents automatically for high-severity alerts
  - [ ] Deduplicate similar alerts
  - [ ] Display DLP alerts in dashboard
  - [ ] Correlate DLP alerts with HR flags (e.g., termination + data download)
  - [ ] Alert ingestion latency <5 minutes
  - [ ] Automatic retry on API failures
- **User Stories**: US-6.7 through US-6.11

**FR-6.3: Vendor Support**
- **Description**: Support major DLP vendors beyond Purview
- **Acceptance Criteria**:
  - [ ] Support Microsoft Purview (priority)
  - [ ] Support Symantec DLP
  - [ ] Support Forcepoint DLP
  - [ ] Support Digital Guardian
  - [ ] Support McAfee DLP
  - [ ] Vendor-agnostic alert ingestion API
- **User Stories**: US-6.12 through US-6.15

---

#### Epic 7: Oversight Features - Adapted (Priority: P1)

**FR-7.1: Framework Mapping**
- **Description**: Pre-populated insider threat-specific frameworks
- **Acceptance Criteria**:
  - [ ] Pre-populate with CISA Insider Threat Mitigation Framework, NIST SP 800-53 (Insider Threat controls), ITMG Best Practices, Industry-specific frameworks
  - [ ] Allow user to add/remove framework elements
  - [ ] Support industry swapping (financial, healthcare, tech, manufacturing, government)
  - [ ] Map controls to implementation status (Not Started, In Progress, Implemented, Not Applicable)
  - [ ] Allow adding evidence (document links, notes)
  - [ ] Calculate overall coverage % per framework
- **User Stories**: US-7.1 through US-7.5

**FR-7.2: Volume & Framework Baseline**
- **Description**: Target vs. actual metrics based on program maturity
- **Acceptance Criteria**:
  - [ ] Operate in "Target Mode" for zero-incident orgs (Months 0-4)
  - [ ] Display target metrics (industry benchmarks)
  - [ ] Transition to "Actual Mode" when incidents exist (Month 4+)
  - [ ] Show variance between target and actual
- **User Stories**: US-7.6 through US-7.8

**FR-7.3: Controls Mapping**
- **Description**: Pre-populated insider threat control library
- **Acceptance Criteria**:
  - [ ] Pre-populate with technical, administrative, physical controls
  - [ ] Allow user customization (add/remove/edit)
  - [ ] Support client-swappable content for demos
  - [ ] Track control implementation status
  - [ ] Link controls to rollout planner phases
  - [ ] Calculate control coverage %
- **User Stories**: US-7.9 through US-7.12

**FR-7.4: Threat Intelligence**
- **Description**: Industry benchmarks and threat scenarios
- **Acceptance Criteria**:
  - [ ] Provide industry benchmarks (average incidents per org size, common threat types by industry, average cost per incident)
  - [ ] Provide "What could happen" scenarios (data exfiltration, IP theft, sabotage)
  - [ ] Update quarterly with latest research
- **User Stories**: US-7.13 through US-7.15

**FR-7.5: Org Risk Viewer**
- **Description**: Visual risk assessment for potential threat areas
- **Acceptance Criteria**:
  - [ ] Operate in assessment mode (no actual incidents yet)
  - [ ] Visualize potential risk areas: Departments with sensitive data access, Roles with elevated privileges, Remote/hybrid workers, Contractors/third-parties, Employees on PIP or with performance issues
  - [ ] Suggest risk mitigation priorities
  - [ ] Transition to incident mode at Month 4+
- **User Stories**: US-7.16 through US-7.18

**FR-7.6: Reporting**
- **Description**: Report templates for starting programs
- **Acceptance Criteria**:
  - [ ] Provide 4 reports: Program Progress Report, Maturity Assessment Report, Quick Win Activity Report, Policy Coverage Report
  - [ ] DO NOT include incident reports until incidents exist
  - [ ] Transition to incident reports at Month 4+
  - [ ] Export to PDF/Excel
  - [ ] Professional formatting
- **User Stories**: US-7.19 through US-7.21

---

#### Epic 8: Demo Mode System (Priority: P1)

**FR-8.1: Mode Selection**
- **Description**: Flexible demo modes for sales enablement
- **Acceptance Criteria**:
  - [ ] Provide 5 modes: "Show Me the Journey" (interactive step-through), "Month 0 View" (pure startup), "Month 6 View" (mid-maturity), "Month 12 View" (mature program), "Custom Timeline" (user-defined)
  - [ ] Mode selector prominently displayed
  - [ ] "You are viewing Month X" indicator always visible
- **User Stories**: US-8.1 through US-8.5

**FR-8.2: Data Population**
- **Description**: Generate appropriate synthetic data for selected month
- **Acceptance Criteria**:
  - [ ] Month 0: Empty states, targets only
  - [ ] Month 3: Training in progress, policies drafted, no incidents
  - [ ] Month 6: 5-10 incidents, early trends, DLP deployed
  - [ ] Month 9: 15-25 incidents, clear trends, patterns emerging
  - [ ] Month 12: 30+ incidents, full KPIs, mature analytics
  - [ ] Synthetic data looks realistic (not obviously fake)
  - [ ] Trends statistically plausible
- **User Stories**: US-8.6 through US-8.10

**FR-8.3: Feature Visibility**
- **Description**: Show/hide features based on program maturity
- **Acceptance Criteria**:
  - [ ] Months 0-3: Priority Picker, Rollout Planner, Quick Wins, Training
  - [ ] Month 4+: Add Incidents module, DLP dashboard
  - [ ] Month 8+: Add full KPIs, trends, behavioral analytics
  - [ ] Smooth transitions between modes (<2 seconds)
  - [ ] Reset to Month 0 functionality
- **User Stories**: US-8.11 through US-8.15

---

#### Epic 9: Content Management (Priority: P2)

**FR-9.1: Industry Content Packs**
- **Description**: Pre-built content for 5 industries
- **Acceptance Criteria**:
  - [ ] Provide content for: Financial Services, Healthcare, Technology, Manufacturing, Government
  - [ ] Each pack includes: Industry-specific risk scenarios, Relevant regulatory frameworks, Typical incident examples, Budget estimates (market rates), Policy templates
  - [ ] Allow adding new industry packs
- **User Stories**: US-9.1 through US-9.5

**FR-9.2: Content Swapping**
- **Description**: Quick content swapping for demos
- **Acceptance Criteria**:
  - [ ] Swap industry pack in <1 minute
  - [ ] Update all relevant areas: Dashboard scenarios, Framework mapping, Threat intelligence, PPTX generation, Reports
  - [ ] Preserve user data (don't overwrite)
  - [ ] Change audit log (who changed what when)
- **User Stories**: US-9.6 through US-9.9

**FR-9.3: Framework & Template Management**
- **Description**: Manage frameworks, controls, and templates
- **Acceptance Criteria**:
  - [ ] Add/edit frameworks
  - [ ] Add/edit controls
  - [ ] Manage policy templates
  - [ ] Manage report templates
  - [ ] Manage PPTX templates
  - [ ] Version control (track changes)
  - [ ] Import from CSV/Excel
  - [ ] Preview before using
- **User Stories**: US-9.10 through US-9.15

---

#### Epic 10: Incident Management (Priority: P2)

**FR-10.1: Incident Logging**
- **Description**: Manual and automated incident creation
- **Acceptance Criteria**:
  - [ ] Manual incident creation (form-based)
  - [ ] Auto-creation from DLP alerts (high severity)
  - [ ] Auto-creation from HR flags
  - [ ] Auto-creation from quick win channels
  - [ ] Capture: Title, Description, Severity, Source, Affected user, Date/time, Evidence
  - [ ] Generate unique incident ID
  - [ ] Assign to investigator
- **User Stories**: US-10.1 through US-10.6

**FR-10.2: Incident Investigation**
- **Description**: Track investigation progress and outcomes
- **Acceptance Criteria**:
  - [ ] Investigation workflow (New → In Progress → Resolved → Closed)
  - [ ] Add notes/comments
  - [ ] Attach evidence
  - [ ] Timeline view of incident activities
  - [ ] Assign severity (Low, Medium, High, Critical)
  - [ ] Track time spent (for MTTR calculation)
- **User Stories**: US-10.7 through US-10.11

**FR-10.3: Incident Reporting**
- **Description**: Generate incident reports and analytics
- **Acceptance Criteria**:
  - [ ] Incident list view (filterable, sortable)
  - [ ] Incident detail view
  - [ ] Export incident list to CSV
  - [ ] Generate incident summary report
  - [ ] Track MTTD and MTTR
  - [ ] Show incident trends over time
- **User Stories**: US-10.12 through US-10.15

---

### Non-Functional Requirements

#### Performance (NFR-PERF)

**NFR-PERF-001: Page Load Time**
- All pages MUST load in <2 seconds (95th percentile)
- Dashboard MUST render in <2 seconds
- Priority Picker questions MUST load in <500ms

**NFR-PERF-002: API Response Time**
- API endpoints MUST respond in <500ms (95th percentile)
- Database queries MUST complete in <200ms (average)

**NFR-PERF-003: Processing Time**
- AI policy analysis MUST complete in <60 seconds for 100 pages
- PPTX generation MUST complete in <5 seconds
- Report generation MUST complete in <5 seconds
- DLP alert ingestion latency MUST be <5 minutes

**NFR-PERF-004: Scalability**
- Platform MUST support 10,000 concurrent users
- Training campaigns MUST support 10,000+ users per campaign
- Email queue MUST handle 1,000+ messages/hour

---

#### Security (NFR-SEC)

**NFR-SEC-001: Data Encryption**
- All data MUST be encrypted at rest (AES-256)
- All data MUST be encrypted in transit (TLS 1.3)

**NFR-SEC-002: Authentication & Authorization**
- Platform MUST support email/password and SSO (SAML 2.0, OAuth 2.0)
- Platform MUST implement role-based access control (RBAC)
- Platform MUST enforce multi-factor authentication (MFA) for admin roles

**NFR-SEC-003: Audit Logging**
- Platform MUST log all sensitive actions (incident access, HR flag access, configuration changes)
- Audit logs MUST be tamper-proof
- Audit logs MUST be retained for 7 years

**NFR-SEC-004: Privacy & Compliance**
- Platform MUST comply with GDPR (data subject rights, privacy by design)
- Platform MUST comply with CCPA (data disclosure, deletion)
- Platform MUST NOT store employee PII unnecessarily
- HR flag data MUST be restricted to need-to-know basis

**NFR-SEC-005: Security Testing**
- Platform MUST undergo penetration testing before production launch
- Platform MUST have 0 critical, <3 high vulnerabilities at launch
- Platform MUST perform quarterly vulnerability scans

---

#### Accessibility (NFR-ACC)

**NFR-ACC-001: WCAG Compliance**
- Platform MUST be WCAG 2.1 Level AA compliant
- All interactive elements MUST be keyboard navigable
- Platform MUST be screen reader compatible
- Platform MUST use color-blind friendly palettes

**NFR-ACC-002: Mobile Responsiveness**
- Platform MUST be responsive (desktop, tablet, mobile)
- Dashboard MUST be readable on mobile devices
- Critical workflows MUST work on mobile (incident logging, training)

---

#### Reliability (NFR-REL)

**NFR-REL-001: Uptime**
- Platform MUST achieve 99.9% uptime (excluding planned maintenance)
- Planned maintenance windows MUST be <4 hours/month

**NFR-REL-002: Data Durability**
- User data MUST have 99.999999999% durability (11 nines)
- Database backups MUST be performed daily
- Point-in-time recovery MUST be available for last 30 days

**NFR-REL-003: Disaster Recovery**
- Platform MUST have disaster recovery plan (RTO <4 hours, RPO <1 hour)
- Platform MUST have geo-redundant backups

---

#### Usability (NFR-USE)

**NFR-USE-001: Ease of Use**
- Priority Picker MUST be completable in <10 minutes
- AI policy analysis MUST have <5% user error rate
- Dashboard MUST be understandable without training

**NFR-USE-002: Documentation**
- Platform MUST have comprehensive user documentation
- Platform MUST have video tutorials (5-10 min each)
- Platform MUST have contextual help tooltips

**NFR-USE-003: Onboarding**
- New users MUST complete onboarding in <15 minutes
- Platform MUST have interactive product tour

---

#### Maintainability (NFR-MAIN)

**NFR-MAIN-001: Code Quality**
- Codebase MUST have >80% test coverage
- Code MUST pass automated linting
- Code MUST follow established style guide

**NFR-MAIN-002: Monitoring**
- Platform MUST have application performance monitoring (APM)
- Platform MUST have error tracking (Sentry, Rollbar, etc.)
- Platform MUST have usage analytics
- Platform MUST have uptime monitoring

**NFR-MAIN-003: Deployment**
- Platform MUST have CI/CD pipeline
- Deployments MUST be automated
- Rollbacks MUST be possible within 5 minutes

---

### Out of Scope (v1.0)

The following features are explicitly OUT OF SCOPE for v1.0 and deferred to future releases:

1. **UEBA Integration** (v1.3) - Behavioral analytics for advanced tier orgs
2. **MSSP Integration** (v1.4) - Alert forwarding, joint workflows with MSSPs
3. **Foresight "Easy-Start" Mode** (v2.0) - Simplified predictive analytics
4. **Mobile Apps** - Native iOS/Android apps (web-responsive sufficient for v1.0)
5. **White-Label Branding** - Custom branding for resellers (future commercial feature)
6. **Compliance Report Automation** - Auto-generate SOC 2, ISO 27001 reports (future)
7. **Threat Intelligence Feeds** - Real-time external threat feeds (future)
8. **Advanced Behavioral Analytics** - User behavior profiling (requires UEBA)
9. **Integration Marketplace** - Third-party app integrations (future ecosystem)
10. **API for External Developers** - Public API for partners (future)

---

## User Stories

### Epic 1: User Onboarding & Discovery

**US-1.1: Complete Priority Picker**
- **As a** CISO
- **I want to** answer 10 questions about my organization
- **So that** I get a customized recommendation on where to start
- **Acceptance Criteria**:
  - Questions are clear and jargon-free
  - Can navigate back to change answers
  - Completes in <10 minutes
  - Recommendation makes sense for my context

**US-1.2: Get DLP Recommendation**
- **As an** IT Manager
- **I want to** know if I already have DLP (Purview)
- **So that** I don't waste money procuring another DLP tool
- **Acceptance Criteria**:
  - System detects my M365 license
  - Clearly states if Purview is available (and cost)
  - Explains what Purview can do

**US-1.3: Receive Sophistication Tier**
- **As a** Risk Officer
- **I want to** understand my organization's sophistication level
- **So that** I set realistic expectations for my program
- **Acceptance Criteria**:
  - Tier (Basic/Intermediate/Advanced) displayed
  - Explains what tier means
  - Suggests appropriate features for my tier

**US-1.4: Get Starting Path Recommendation**
- **As a** new CISO
- **I want to** know which path to take (Policy Dev, Risk Assessment, Quick Win)
- **So that** I don't waste time on wrong priorities
- **Acceptance Criteria**:
  - Clear recommendation with rationale
  - Explains what each path entails
  - Shows next steps

**US-1.5: Save Priority Picker Responses**
- **As a** user
- **I want to** save my Priority Picker responses
- **So that** I can reference them later or update them
- **Acceptance Criteria**:
  - Responses saved to my account
  - Can view/edit responses later
  - Can retake Priority Picker if context changes

**US-1.6: Share Priority Picker Results**
- **As a** CISO
- **I want to** share Priority Picker results with my team
- **So that** we're aligned on starting point
- **Acceptance Criteria**:
  - Can export results to PDF
  - Can share via email
  - Can copy shareable link

**US-1.7: Understand UEBA Readiness**
- **As a** CISO at a sophisticated org
- **I want to** know if UEBA is appropriate for me
- **So that** I can plan for advanced capabilities
- **Acceptance Criteria**:
  - Clear Yes/No/Maybe recommendation on UEBA
  - Explains criteria (team size, budget, MSSP)
  - Suggests timing (Month 4 decision point)

**US-1.8: Generate Program Approval PPTX**
- **As a** CISO
- **I want to** auto-generate a board-ready presentation
- **So that** I save 2+ weeks of manual work
- **Acceptance Criteria**:
  - All 8 slides generated with my data
  - Budget estimates match my org size
  - Industry-specific risk scenarios included
  - Editable (I can customize before presenting)

**US-1.9: See Accurate Budget Estimates**
- **As a** Risk Officer
- **I want to** see realistic budget estimates for Year 1
- **So that** I can request appropriate funding
- **Acceptance Criteria**:
  - Personnel, tools, training, consulting costs broken down
  - Estimates within ±20% of market rates
  - Purview shown as $0 if I have E5/A5
  - Contingency included

**US-1.10: Customize PPTX Before Presenting**
- **As a** CISO
- **I want to** edit the generated PPTX
- **So that** I can tailor it to my board's preferences
- **Acceptance Criteria**:
  - PPTX opens in PowerPoint without errors
  - All slides editable
  - No placeholder text (all customized)
  - Professional design

**US-1.11: Download PPTX Quickly**
- **As a** user
- **I want** PPTX generation to complete in <5 seconds
- **So that** I don't wait around
- **Acceptance Criteria**:
  - Generation time <5 seconds
  - Download starts automatically
  - File size <5MB

**US-1.12: Reference PPTX Content**
- **As a** CISO
- **I want to** view the PPTX content online (before downloading)
- **So that** I can decide if it's worth presenting
- **Acceptance Criteria**:
  - Preview all 8 slides in browser
  - Can download after preview
  - Can regenerate if I change Priority Picker answers

**US-1.13: Create Account**
- **As a** new user
- **I want to** create an account quickly
- **So that** I can start using the platform
- **Acceptance Criteria**:
  - Email/password or SSO options
  - Email verification required
  - Account created in <2 minutes

**US-1.14: Set Up Organization Profile**
- **As a** CISO
- **I want to** configure my organization profile
- **So that** the platform is customized to my context
- **Acceptance Criteria**:
  - Org name, size, industry captured
  - Can upload logo (optional)
  - Can configure branding colors (optional)

**US-1.15: Invite Team Members**
- **As a** CISO
- **I want to** invite team members to the platform
- **So that** we collaborate on the program
- **Acceptance Criteria**:
  - Send email invitations
  - Assign roles (Admin, Analyst, Viewer)
  - Invitees can accept and create accounts

*(Additional user stories for Epic 2-10 follow similar format - see full epic specifications in separate document)*

---

## Design & User Experience

### Design Principles

1. **Clarity Over Complexity** - Prefer simple, obvious UI over feature-rich but confusing
2. **Progressive Disclosure** - Show what's needed now, hide what's not (based on phase)
3. **Data-Driven Confidence** - Always show data source and reasoning (build trust)
4. **Guidance First** - Assume users are new, provide contextual help everywhere
5. **Mobile-First** - Design for mobile, enhance for desktop
6. **Accessible by Default** - WCAG 2.1 AA compliance is not optional

### Information Architecture

```
Platform
├── Dashboard (default landing page)
│   ├── Zero-Incident View (Months 0-4)
│   ├── Early Detection View (Months 4-7)
│   └── Mature View (Months 8-12)
├── Onboarding
│   ├── Priority Picker
│   ├── PPTX Generator
│   └── Account Setup
├── Quick Wins
│   ├── AI Policy Gap Analysis
│   ├── Self-Reporting Portal (public-facing)
│   ├── Manager Concern Form
│   └── HR Flag Dashboard
├── Rollout Planner
│   ├── Phase Overview
│   ├── Task Checklists
│   └── Timeline View
├── Training & Awareness
│   ├── Campaign Library
│   ├── Active Campaigns
│   ├── Completion Tracking
│   └── Reports
├── Incidents (appears Month 4+)
│   ├── Incident List
│   ├── Incident Detail
│   ├── Investigation Workflow
│   └── Incident Reports
├── DLP Integration (appears Month 4+)
│   ├── Purview Setup
│   ├── Alert Dashboard
│   ├── Configuration
│   └── Tuning
├── Oversight
│   ├── Framework Mapping
│   ├── Controls Mapping
│   ├── Threat Intelligence
│   ├── Org Risk Viewer
│   └── Reports
├── Settings
│   ├── Organization Profile
│   ├── Team Members
│   ├── Integrations (HRIS, O365, MSSP)
│   ├── Content Management (Admin only)
│   └── Demo Mode Selector (Sales/Demo accounts only)
└── Help & Documentation
    ├── User Guide
    ├── Video Tutorials
    ├── FAQ
    └── Support Contact
```

### Key User Flows

**Flow 1: First-Time User → Program Approval (Week 0-4)**
```
1. User signs up → Email verification
2. Complete Priority Picker (10 questions, <10 min)
3. View recommendation (starting path, tier, DLP option, UEBA readiness)
4. Download PPTX (auto-generated, <5 sec)
5. Customize PPTX in PowerPoint
6. Present to board/executives
7. Receive budget approval
8. Return to platform, begin Phase 1
```

**Flow 2: Week 1 → AI Policy Gap Analysis**
```
1. Navigate to Quick Wins → AI Policy Gap Analysis
2. Upload policies (PDF, Word, drag-and-drop)
3. Wait for analysis (<60 sec, progress indicator)
4. Review gap report (Executive Summary, Heatmap, Findings, Recommendations, Templates)
5. Download report (PDF or Word)
6. Download policy templates for gaps
7. Begin policy remediation
8. Track policy coverage % on dashboard
```

**Flow 3: Month 4 → DLP Deployment**
```
1. Navigate to DLP Integration
2. Platform detects Purview availability (if E5/A5)
3. Follow setup wizard (6 steps)
4. Configure DLP policies (use templates)
5. Set alert thresholds
6. Test alerts (simulate violations)
7. Go live
8. Monitor dashboard (alert volume, false positives)
9. Tune alerts over 2-4 weeks
10. First incidents logged automatically
```

**Flow 4: Manager → Report Concern**
```
1. Navigate to Manager Concern Form (or use direct link)
2. Authenticate as manager
3. Fill form (employee, concern type, description, urgency)
4. Submit
5. Receive confirmation (ticket ID)
6. Security team notified
7. Case created in incident system
8. Manager can track status (if permissions allow)
```

---

## Technical Architecture

### High-Level Architecture

```
┌─────────────────────────────────────────────────────┐
│                   Client Layer                       │
│  (React 18 / Next.js 14 / TypeScript / Tailwind)   │
└─────────────────────────────────────────────────────┘
                         │
                         ▼
┌─────────────────────────────────────────────────────┐
│                API Gateway / Load Balancer           │
│              (NGINX / AWS ALB / Cloudflare)         │
└─────────────────────────────────────────────────────┘
                         │
        ┌────────────────┴───────────────┐
        ▼                                ▼
┌────────────────────┐          ┌────────────────────┐
│  Application Layer │          │  Background Jobs   │
│  (Node.js/Express) │          │  (Bull Queue/Redis)│
│  - API Endpoints   │          │  - Email sends     │
│  - Business Logic  │          │  - Report gen      │
│  - Auth/RBAC       │          │  - Alert ingestion │
└────────────────────┘          └────────────────────┘
         │                               │
         └───────────┬───────────────────┘
                     ▼
┌─────────────────────────────────────────────────────┐
│                   Data Layer                         │
│  ┌──────────────┐  ┌──────────────┐  ┌───────────┐ │
│  │  PostgreSQL  │  │    Redis     │  │  S3/Blob  │ │
│  │  (Primary DB)│  │    (Cache)   │  │  (Files)  │ │
│  └──────────────┘  └──────────────┘  └───────────┘ │
└─────────────────────────────────────────────────────┘
                     │
        ┌────────────┴────────────┐
        ▼                         ▼
┌────────────────────┐   ┌────────────────────┐
│  External Services │   │    Integrations    │
│  - OpenAI GPT-4    │   │  - Microsoft Graph │
│  - SendGrid        │   │  - HRIS APIs       │
│  - Stripe          │   │  - DLP Vendors     │
└────────────────────┘   └────────────────────┘
```

### Technology Stack

**Frontend**:
- React 18 (UI library)
- Next.js 14 (framework, SSR, API routes)
- TypeScript (type safety)
- Tailwind CSS (styling)
- shadcn/ui (component library)
- Chart.js / D3.js (visualizations)
- React Query (data fetching)
- Zustand (state management)

**Backend**:
- Node.js 20 LTS (runtime)
- Express.js (web framework) OR Next.js API routes
- TypeScript (type safety)
- Prisma (ORM)
- PostgreSQL 15 (relational database)
- Redis 7 (caching, queues, sessions)
- Bull (job queue)

**AI/ML**:
- OpenAI GPT-4 API (policy gap analysis)
- LangChain (LLM orchestration)
- Pinecone / Weaviate (vector database for embeddings)

**File Storage**:
- AWS S3 / Azure Blob Storage (documents, reports, uploads)

**Email**:
- SendGrid / AWS SES (transactional emails)

**Payments** (if SaaS model):
- Stripe (subscription management)

**Integrations**:
- Microsoft Graph API (O365, Purview)
- HRIS APIs (Workday, BambooHR, ADP, etc.)
- DLP Vendor APIs (Symantec, Forcepoint, etc.)

**Infrastructure**:
- AWS / Azure / GCP (cloud hosting)
- Docker (containerization)
- Kubernetes / ECS (orchestration - optional for MVP)
- GitHub Actions (CI/CD)
- Terraform (infrastructure as code)

**Monitoring**:
- Datadog / New Relic (APM)
- Sentry (error tracking)
- LogRocket / Mixpanel (analytics)
- Uptime Robot / Pingdom (uptime monitoring)

---

## Go-to-Market Strategy

### Pricing Model

**Recommended: SaaS Subscription (Annual)**

| Tier | Org Size | Price | Features |
|------|----------|-------|----------|
| **Starter** | 100-500 employees | $6k/year ($500/month) | Priority Picker, PPTX, AI Gap Analysis (5x), Quick Wins, Dashboard (Zero-Incident), Rollout Planner |
| **Professional** | 500-2,000 employees | $18k/year ($1,500/month) | All Starter + Unlimited AI analyses, Training Module, DLP Integration (Purview), Oversight Features, 5 team members |
| **Enterprise** | 2,000-5,000 employees | $36k/year ($3,000/month) | All Professional + Content Management, Demo Modes, 20 team members, Priority support, Custom integrations |
| **Enterprise Plus** | 5,000+ employees | Custom | All Enterprise + UEBA Integration, MSSP Integration, White-label, Dedicated CSM, SLA |

**Add-Ons**:
- Professional Services (implementation): $10k-$50k one-time
- Training (onsite/virtual): $5k per session
- Custom integrations: $10k-$25k per integration

### Sales Strategy

**Target Channels**:
1. **Direct Sales** (primary for Enterprise)
   - Outbound: Targeted outreach to CISOs, Risk Officers at 1,000-5,000 employee orgs
   - Inbound: Content marketing, SEO, webinars driving demo requests
2. **Self-Service** (primary for Starter/Professional)
   - Freemium: Free Priority Picker + PPTX, upgrade for full platform
   - Free trial: 14-day trial of Professional tier
3. **Channel Partners** (future)
   - MSSPs (resell to their clients)
   - Security consultancies (implementation partners)
   - Microsoft (co-sell for Purview adoption)

**Sales Process**:
```
1. Lead Generation (content, ads, events)
2. Demo Request (self-service signup or sales meeting)
3. Priority Picker (prospect completes, gets PPTX)
4. Follow-Up (sales reviews recommendation, offers trial)
5. Trial (14 days Professional tier)
6. Close (annual contract, payment via Stripe or invoicing)
7. Onboarding (CSM-led for Enterprise, self-service for Starter/Pro)
```

**Key Metrics**:
- Demo-to-trial conversion: >40%
- Trial-to-paid conversion: >50%
- Time to close: <30 days (Starter/Pro), <60 days (Enterprise)
- Annual contract value (ACV): $15k average

### Marketing Strategy

**Positioning**:
- **For**: Organizations starting insider threat programs from zero
- **Who**: CISOs, Risk Officers, IT Managers
- **The**: Non-Expert Insider Threat Demo Platform
- **Is a**: Demo + Educational + SaaS platform
- **That**: Guides you from program approval to operational maturity in 12 months
- **Unlike**: Traditional insider threat tools (Splunk, Exabeam, etc.)
- **Our Product**: Provides value without requiring historical incident data

**Key Messages**:
1. "Start Your Insider Threat Program in 30 Days, Not 6 Months"
2. "Get Board Approval in 1 Click (Auto-Generated Presentation)"
3. "AI-Powered Policy Analysis in 60 Seconds"
4. "Discover if You Already Have FREE DLP (Purview)"
5. "From Zero Incidents to Full Program Maturity in 12 Months"

**Content Strategy**:
- **Blog**: Weekly posts on insider threat program establishment (SEO-optimized)
- **Webinars**: Monthly "How to Start an Insider Threat Program" (lead gen)
- **E-books**: "The Ultimate Guide to Insider Threat Programs for Non-Experts" (gated)
- **Case Studies**: Customer success stories (post-launch)
- **Video Tutorials**: YouTube series on program establishment

**Demand Generation**:
- Google Ads: "insider threat program", "how to start insider threat", "DLP for small business"
- LinkedIn Ads: Targeting CISOs, Risk Officers, IT Managers at 1k-5k employee orgs
- Conference Sponsorships: RSA, Black Hat, Gartner Security Summit (post-launch)
- Partnerships: Microsoft (Purview co-marketing), SANS Institute (training)

---

## Success Metrics & KPIs

### North Star Metric

**Number of organizations with operational insider threat programs** (defined as: reached Month 12, >80% training completion, DLP deployed, >5 incidents logged and resolved)

### Product Metrics

**Engagement**:
- Priority Picker completion rate: Target >90%
- PPTX download rate: Target >80% (of Priority Picker completions)
- AI Gap Analysis usage: Target >70% (of paid users)
- Dashboard daily active users (DAU): Target >30% (of total users)
- Average session duration: Target >15 minutes

**Feature Adoption**:
- Quick Win channels used: Target >60% (at least 1 channel used)
- Training campaigns launched: Target >50% (of paid users)
- DLP integration completed: Target >80% (by Month 4)
- Rollout Planner tasks completed: Target >70% (of total tasks)

**Outcome Metrics**:
- Program approval rate: Target >70% (within 30 days of demo)
- DLP deployment on schedule: Target >80% (Month 4 target met)
- Training completion rate: Target >80% (of enrolled users)
- Time to first incident detection: Target <7 months
- User satisfaction (NPS): Target >50

### Business Metrics

**Acquisition**:
- Demo requests: 100+ per month (by Month 6 post-launch)
- Demo-to-trial conversion: Target >40%
- Trial-to-paid conversion: Target >50%
- Time to close: Target <30 days (Starter/Pro), <60 days (Enterprise)

**Revenue**:
- Monthly Recurring Revenue (MRR): Target $100k by Month 6 post-launch
- Annual Recurring Revenue (ARR): Target $1.2M-$9M Year 1
- Average Contract Value (ACV): Target $15k
- Customer Lifetime Value (LTV): Target $45k (3-year retention)

**Retention**:
- Monthly churn rate: Target <5%
- Annual retention rate: Target >75%
- Net Revenue Retention (NRR): Target >100% (upsells > churn)

**Efficiency**:
- Customer Acquisition Cost (CAC): Target <$5k
- LTV:CAC ratio: Target >3:1
- Months to recover CAC: Target <12 months
- Gross margin: Target >80%

---

## Risks & Dependencies

### Critical Risks

| Risk | Impact | Probability | Mitigation |
|------|--------|-------------|------------|
| AI policy analysis quality poor | High | Medium | Use GPT-4, validate with SME, iterate based on feedback, offer human review |
| Market rejects zero-incident value prop | High | Low | Pilot with 10 users, validate before Phase 2, adjust messaging |
| O365 API complexity delays DLP integration | High | Medium | Microsoft partnership, allocate extra time (3-week buffer), professional services option |
| Purview adoption lower than expected | Medium | Medium | Support 3+ vendors, don't rely solely on Purview, market agnostic |
| Competitor launches similar product | Medium | Low | First-mover advantage, patent AI gap analysis, focus on customer success |
| Regulatory changes (privacy laws) | Medium | Low | Legal review, privacy by design, adapt quickly to changes |
| Security breach (platform hacked) | High | Very Low | Penetration testing, bug bounty, SOC 2 compliance, insurance |
| Key personnel turnover | High | Low | Knowledge sharing, documentation, competitive comp, equity |

### Key Dependencies

**External**:
- OpenAI GPT-4 API availability and pricing
- Microsoft Graph API access and stability
- HRIS vendor API availability (Workday, BambooHR, etc.)
- DLP vendor API availability (Symantec, Forcepoint, etc.)

**Internal**:
- Product management (define requirements)
- Engineering team (build platform)
- Design team (create UI/UX)
- Security SME (create content, validate AI)
- Sales team (sell platform)
- Customer success team (onboard and retain customers)

**Business**:
- Funding ($1.15M-$1.44M for Year 1)
- Market validation (10-20 user interviews)
- Pilot customers (5-10 for MVP testing)
- Microsoft partnership (for Purview co-marketing)

---

## Release Plan

### Phase 1: MVP (Week 12)

**Release Date**: Week 12 (Q1 2026 est.)

**What's Included**:
- Priority Picker
- Program Approval PPTX Generator
- AI Policy Gap Analysis
- 3 Quick Win channels (self-report, manager, HR flags)
- Zero-Incident Dashboard
- Basic incident logging

**Release Criteria**:
- [ ] All P0 features complete and tested
- [ ] Demo to 5 pilot users successful (>4/5 satisfaction)
- [ ] No critical bugs
- [ ] Performance targets met (page load <2 sec, AI analysis <60 sec)
- [ ] Security review passed (0 critical vulnerabilities)

**Go/No-Go Decision**: Week 11 sprint review

---

### Phase 2: v1.1 - Demo Enhancement (Week 24)

**Release Date**: Week 24 (Q2 2026 est.)

**What's Included**:
- Demo mode system (5 modes)
- Training campaign management
- Incident source breakdown visualization
- Five-phase rollout planner
- PDF export capabilities

**Release Criteria**:
- [ ] All P1 features complete and tested
- [ ] Sales team using platform actively (>10 demos/month)
- [ ] Client feedback positive (NPS >40)
- [ ] Demo modes work flawlessly (0 crashes in 50 demos)

**Go/No-Go Decision**: Week 23 sprint review

---

### Phase 3: v1.2 - Full Capability (Week 40)

**Release Date**: Week 40 (Q4 2026 est.)

**What's Included**:
- DLP integration (Purview + vendor API)
- 6 Oversight features adapted
- Content management system
- 5 industry packs
- Incident management (full workflow)

**Release Criteria**:
- [ ] All P1-P2 features complete and tested
- [ ] Security audit passed (0 critical, <3 high vulnerabilities)
- [ ] Performance targets met (10k concurrent users)
- [ ] Accessibility compliant (WCAG 2.1 AA)
- [ ] Documentation complete
- [ ] Production deployment successful

**Go/No-Go Decision**: Week 39 sprint review

---

## Appendices

### A. Glossary

- **DLP**: Data Loss Prevention - technology to detect and prevent data exfiltration
- **UEBA**: User and Entity Behavior Analytics - ML-based anomaly detection
- **MSSP**: Managed Security Service Provider - outsourced SOC
- **Purview**: Microsoft 365 data governance and compliance platform (includes DLP)
- **MTTD**: Mean Time To Detect - average time to detect an insider threat
- **MTTR**: Mean Time To Respond - average time to resolve an incident
- **KPI**: Key Performance Indicator - measurable value showing program effectiveness
- **PII**: Personally Identifiable Information - data that identifies individuals
- **HRIS**: Human Resources Information System - HR software (Workday, BambooHR, etc.)
- **ROI**: Return on Investment - (Gain - Cost) / Cost
- **ARR**: Annual Recurring Revenue - annualized subscription revenue
- **NPS**: Net Promoter Score - customer satisfaction metric (-100 to +100)

### B. References

- Co-Elicitation Session Notes: `session-notes-2025-10-31-153500-analyst-co-elicitation.md`
- Project Brief: `PROJECT-BRIEF.md`
- Feature Requirements: `FEATURE-REQUIREMENTS.md`
- Implementation Roadmap: `IMPLEMENTATION-ROADMAP.md`
- Executive Summary: `EXECUTIVE-SUMMARY.md`
- Barclays PoC Analysis: `/home/jez/code/Barclays-PoC-on-Vercel/COMPREHENSIVE_CODEBASE_ANALYSIS.md`

### C. Document History

| Version | Date | Author | Changes |
|---------|------|--------|---------|
| 0.1 | 2025-10-31 | Mary | Initial draft from co-elicitation |
| 1.0 | 2025-10-31 | Mary | Complete PRD ready for review |

---

**Document Owner**: Product Management
**Next Review**: After MVP pilot (Week 13)
**Approval Required From**: Engineering Lead, Design Lead, CTO, CEO

**Status**: ✅ Ready for Stakeholder Review


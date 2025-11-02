# User Stories - Non-Expert Insider Threat Demo Platform

**Last Updated**: 2025-11-01
**Status**: Complete - All 10 Epics documented

---

## Document Purpose

This document contains all user stories for the Non-Expert Insider Threat Demo Platform, organized by Epic and Theme. Stories are tagged with:
- **Demo**: Mockup/simplified implementation for demo
- **R1**: Full implementation deferred to Release 1 (post-demo)
- **Dropped**: Story removed from scope

---

## Epic 1: User Onboarding & Discovery (P0, Phase 1)

**Epic Goal**: Help new organizations understand their insider threat program needs and generate initial artifacts (priority recommendations, board approval deck).

### Theme 1: Priority Picker (Interactive Decision Tree)

#### US-1.1: Start Priority Picker Quiz
**As a** CISO or IT Manager
**I want** to start an interactive quiz when I first log in
**So that** the platform can understand my organization's current state and needs

**Acceptance Criteria**:
- [ ] First-time users see "Welcome! Let's find your priorities" screen
- [ ] Quiz introduction explains: "10 questions, 5 minutes, personalized recommendations"
- [ ] "Start Quiz" button launches question flow
- [ ] Option to "Skip for now" and return later
- [ ] Quiz progress saved if user exits early

**Story Points**: 2
**Priority**: P0
**Phase**: Demo (Phase 1)

---

#### US-1.2: Answer 10 Contextual Questions
**As a** CISO
**I want** to answer questions about my org's size, industry, maturity, and concerns
**So that** the platform can tailor recommendations to my situation

**Acceptance Criteria**:
- [ ] 10 questions covering: org size, industry, regulatory requirements, existing tools, incident history, biggest concerns, budget constraints, timeline urgency, technical maturity, executive support
- [ ] Multiple choice format (3-5 options per question)
- [ ] Progress indicator shows "Question X of 10"
- [ ] "Back" button allows changing previous answers
- [ ] Questions adapt based on previous answers (e.g., if "no incidents", skip incident-related questions)

**Story Points**: 5
**Priority**: P0
**Phase**: Demo (Phase 1)

---

#### US-1.3: View Personalized Priority Recommendations
**As a** CISO
**I want** to see which features/capabilities I should prioritize first
**So that** I can focus on high-impact, achievable quick wins

**Acceptance Criteria**:
- [ ] Results page shows "Top 5 Priorities for [Org Name]"
- [ ] Each priority includes: title, rationale ("Why this matters for you"), estimated effort, expected impact
- [ ] Priorities ranked 1-5 based on quiz responses
- [ ] Visual cards/tiles for each priority
- [ ] "Learn More" expands to show implementation steps

**Story Points**: 5
**Priority**: P0
**Phase**: Demo (Phase 1)

---

#### US-1.4: Understand Why Priorities Were Chosen
**As a** Risk Officer
**I want** to see the reasoning behind each priority recommendation
**So that** I can explain the approach to my team and leadership

**Acceptance Criteria**:
- [ ] Each priority shows "Why this matters for you" section
- [ ] Rationale references specific quiz answers (e.g., "Because you indicated no DLP...")
- [ ] Industry benchmarks: "75% of orgs your size start here"
- [ ] Risk explanation: "This addresses your top concern: [X]"
- [ ] Effort vs. impact visualization (2x2 matrix)

**Story Points**: 3
**Priority**: P0
**Phase**: Demo (Phase 1)

---

#### US-1.5: Export Priority Recommendations
**As a** CISO
**I want** to export my priority recommendations to PDF or Word
**So that** I can share with my team and reference during planning

**Acceptance Criteria**:
- [ ] "Export" button offers PDF and Word formats
- [ ] Export includes: quiz summary, all 5 priorities with rationale, next steps
- [ ] Branded with org logo (if uploaded)
- [ ] Professional formatting suitable for executive review
- [ ] Downloaded file named: "[OrgName]_Priorities_[Date].pdf"

**Story Points**: 3
**Priority**: P1
**Phase**: Demo (Phase 1)

---

#### US-1.6: Retake Priority Quiz
**As a** IT Manager
**I want** to retake the priority quiz if my situation changes
**So that** I can get updated recommendations

**Acceptance Criteria**:
- [ ] Settings menu includes "Retake Priority Quiz"
- [ ] Warning: "This will replace your current priorities. Continue?"
- [ ] Previous quiz answers pre-populated (user can modify)
- [ ] Comparison view: "Your priorities changed from [X] to [Y]"
- [ ] History log: "Quiz taken on [dates]"

**Story Points**: 2
**Priority**: P2
**Phase**: R1 (deferred from demo)

---

#### US-1.7: Save Quiz Progress and Resume Later
**As a** CISO
**I want** my quiz progress saved automatically
**So that** I can complete it across multiple sessions

**Acceptance Criteria**:
- [ ] Auto-save after each question answered
- [ ] Return to quiz shows: "Resume from Question X?"
- [ ] Option to "Start Over" or "Continue"
- [ ] Quiz expires after 7 days of inactivity
- [ ] Notification: "You have an incomplete quiz" on dashboard

**Story Points**: 2
**Priority**: P2
**Phase**: R1 (deferred from demo)

---

### Theme 2: PPTX Generator (Program Approval Deck)

#### US-1.8: Generate Program Approval Presentation
**As a** CISO
**I want** to automatically generate a PowerPoint deck for board/executive approval
**So that** I can quickly secure buy-in for the insider threat program

**Acceptance Criteria**:
- [ ] "Generate Approval Deck" button on dashboard
- [ ] System generates 8-section PPTX: Executive Summary, Risk Landscape, Program Vision, Phased Roadmap, Resource Requirements, Quick Wins, Success Metrics, Investment Ask
- [ ] Content auto-populated from quiz answers and priorities
- [ ] Professional template with org branding
- [ ] Downloaded file named: "[OrgName]_InsiderThreat_Proposal_[Date].pptx"

**Story Points**: 8
**Priority**: P0
**Phase**: Demo (Phase 1)

---

#### US-1.9: Customize Approval Presentation Content
**As a** CISO
**I want** to edit the generated presentation before presenting
**So that** I can tailor messaging to my executive audience

**Acceptance Criteria**:
- [ ] Preview PPTX in browser before download
- [ ] Edit key fields: budget amount, timeline, team size, risk scenarios
- [ ] Toggle sections on/off (e.g., hide "Resource Requirements" if not needed)
- [ ] Add custom slides or notes
- [ ] Save customized version

**Story Points**: 5
**Priority**: P1
**Phase**: R1 (deferred from demo)

---

### Theme 3: Account Management

#### US-1.10: Create Organization Account
**As a** CISO
**I want** to create an account for my organization
**So that** I can access the platform and save my progress

**Acceptance Criteria**:
- [ ] Sign-up form: org name, industry, size, admin email, password
- [ ] Email verification required
- [ ] Terms of service and privacy policy acceptance
- [ ] Account created and user logged in automatically
- [ ] Welcome email sent with getting started guide

**Story Points**: 3
**Priority**: P0
**Phase**: Demo (Phase 1)

---

#### US-1.11: Invite Team Members (Deferred to R1)
**Story Points**: 3
**Priority**: P2
**Phase**: R1

---

#### US-1.12: Manage User Roles and Permissions (Deferred to R1)
**Story Points**: 5
**Priority**: P2
**Phase**: R1

---

## Epic 2: Quick Wins - Pre-DLP Value (P0, Phase 1)

**Epic Goal**: Deliver immediate value before DLP deployment through AI-powered policy analysis and human reporting channels.

### Theme 1: AI Policy Gap Analysis

#### US-2.1: Upload Current Policies
**As a** Risk Officer
**I want** to upload my organization's current policies (acceptable use, data handling, etc.)
**So that** the AI can analyze them for insider threat gaps

**Acceptance Criteria**:
- [ ] Upload interface accepts PDF, Word, text files
- [ ] Multiple file upload (drag-and-drop)
- [ ] File size limit: 10MB per file, 50MB total
- [ ] Preview uploaded files before analysis
- [ ] Files stored securely with encryption

**Story Points**: 3
**Priority**: P0
**Phase**: Demo (Phase 1)

---

#### US-2.2: Run AI Gap Analysis
**As a** Risk Officer
**I want** the AI to analyze my policies for insider threat gaps
**So that** I can identify missing controls and weak areas

**Acceptance Criteria**:
- [ ] "Analyze Policies" button triggers AI analysis
- [ ] Progress indicator: "Analyzing... X% complete"
- [ ] Analysis completes in under 2 minutes
- [ ] AI identifies: missing policies, weak language, outdated references, compliance gaps
- [ ] Results stored for historical comparison

**Story Points**: 8
**Priority**: P0
**Phase**: Demo (Phase 1)

---

#### US-2.3: View Gap Analysis Results
**As a** Risk Officer
**I want** to see a detailed report of policy gaps
**So that** I know what to fix

**Acceptance Criteria**:
- [ ] Results dashboard shows: overall score (0-100), number of gaps found, severity breakdown (critical/high/medium/low)
- [ ] List view of all gaps with: gap title, description, affected policy section, severity, recommendation
- [ ] Filter by severity or policy type
- [ ] Search gaps by keyword
- [ ] "Fix This" button links to remediation guidance

**Story Points**: 5
**Priority**: P0
**Phase**: Demo (Phase 1)

---

#### US-2.4: Generate Policy Recommendations
**As a** Compliance Officer
**I want** AI-generated language to fix policy gaps
**So that** I can quickly update policies

**Acceptance Criteria**:
- [ ] Each gap shows "Recommended Language" section
- [ ] Copy-paste ready text for policy updates
- [ ] References industry standards (NIST, ISO, etc.)
- [ ] Customizable by industry (financial, healthcare, tech, etc.)
- [ ] "Download All Recommendations" as Word doc

**Story Points**: 5
**Priority**: P0
**Phase**: Demo (Phase 1)

---

#### US-2.5: Track Policy Updates
**As a** Compliance Officer
**I want** to mark gaps as "Fixed" or "In Progress"
**So that** I can track remediation progress

**Acceptance Criteria**:
- [ ] Each gap has status: Open / In Progress / Fixed
- [ ] Status change requires: date, notes, responsible person
- [ ] Dashboard shows: gaps remaining, % complete
- [ ] Historical view: "Gap fixed on [date]"
- [ ] Re-run analysis to validate fixes

**Story Points**: 3
**Priority**: P1
**Phase**: Demo (Phase 1)

---

#### US-2.6: Export Gap Analysis Report
**As a** Risk Officer
**I want** to export the gap analysis as PDF or Excel
**So that** I can share with leadership and track in other tools

**Acceptance Criteria**:
- [ ] "Export" button offers PDF and Excel formats
- [ ] PDF includes: executive summary, all gaps, recommendations, action plan
- [ ] Excel includes: sortable/filterable gap list
- [ ] Branded with org logo
- [ ] Downloaded file named: "[OrgName]_PolicyGaps_[Date]"

**Story Points**: 3
**Priority**: P1
**Phase**: Demo (Phase 1)

---

### Theme 2: Self-Reporting Portal (Deferred to R1)

All stories deferred to R1.

---

### Theme 3: Manager Concern Form (Deferred to R1)

All stories deferred to R1.

---

### Theme 4: HR Flag Triggers

#### US-2.10: Integrate with HR System
**As a** IT Manager
**I want** to connect to our HRIS (Workday, BambooHR, etc.)
**So that** the platform can detect insider risk indicators from HR events

**Acceptance Criteria**:
- [ ] Integration wizard supports: Workday, BambooHR, ADP, SAP SuccessFactors
- [ ] OAuth/API authentication
- [ ] Permission request: read access to employee status, performance reviews, terminations
- [ ] Test connection button validates credentials
- [ ] Data sync schedule: daily or real-time

**Story Points**: 8
**Priority**: P1
**Phase**: Demo (Phase 1)

---

#### US-2.11: Detect HR Risk Indicators
**As a** Risk Officer
**I want** the system to flag HR events that indicate insider risk
**So that** I can proactively monitor high-risk individuals

**Acceptance Criteria**:
- [ ] Auto-detect events: terminations, PIPs, disciplinary actions, denied promotions, sudden leave
- [ ] Configurable rules: which events trigger flags
- [ ] Severity scoring: critical (termination), high (PIP), medium (denied promotion)
- [ ] Alert generated for security team
- [ ] Privacy controls: limit who can see HR data

**Story Points**: 8
**Priority**: P1
**Phase**: Demo (Phase 1)

---

#### US-2.12: View HR-Triggered Alerts
**As a** Security Analyst
**I want** to see alerts triggered by HR events
**So that** I can investigate potential insider threats

**Acceptance Criteria**:
- [ ] Dashboard shows HR alerts with: employee name (anonymized option), event type, date, severity
- [ ] Filter by event type or severity
- [ ] Click alert to see: full HR context, recommended actions, investigation checklist
- [ ] Mark alert as "Reviewed" or "Escalated"
- [ ] Link alert to incident if needed

**Story Points**: 5
**Priority**: P1
**Phase**: Demo (Phase 1)

---

### Theme 5: Basic Incident Logging

#### US-2.14: Log Manual Incidents
**As a** Security Analyst
**I want** to manually log insider threat incidents
**So that** I can track concerns even before DLP is deployed

**Acceptance Criteria**:
- [ ] "Log Incident" button on dashboard
- [ ] Form fields: date, employee name (optional), incident type, description, severity, source (self-report, manager, HR, observation)
- [ ] Attach evidence: screenshots, emails, files
- [ ] Auto-assign incident ID
- [ ] Incident saved and searchable

**Story Points**: 5
**Priority**: P0
**Phase**: Demo (Phase 1)

---

#### US-2.15: View Incident Log
**As a** CISO
**I want** to see all logged incidents in one place
**So that** I can track program activity and trends

**Acceptance Criteria**:
- [ ] Incident list view: ID, date, type, severity, status
- [ ] Sort by date, severity, or type
- [ ] Filter by status (open/closed), severity, date range
- [ ] Search by employee name or keyword
- [ ] Click incident to view full details

**Story Points**: 3
**Priority**: P0
**Phase**: Demo (Phase 1)

---

## Epic 3: Dashboard & Metrics - Adaptive (P0, Phase 1)

**Epic Goal**: Provide adaptive dashboard that evolves from zero-incident orgs (leading indicators) to mature programs (full KPIs).

### Theme 1: Zero-Incident Dashboard (Months 0-3)

#### US-3.1: View Program Readiness Score
**As a** CISO
**I want** to see a program readiness score (0-100)
**So that** I can track my progress from zero to operational

**Acceptance Criteria**:
- [ ] Dashboard prominently displays readiness score with visual gauge
- [ ] Score factors: policies uploaded, tools connected, training launched, roles assigned, incidents logged
- [ ] Tooltip explains score calculation
- [ ] Historical trend: score over time
- [ ] Recommendations to improve score

**Story Points**: 5
**Priority**: P0
**Phase**: Demo (Phase 1)

---

#### US-3.2: View Policy Coverage Percentage
**As a** Risk Officer
**I want** to see what % of required policies are in place
**So that** I can track policy completeness

**Acceptance Criteria**:
- [ ] Widget shows: "Policy Coverage: X%"
- [ ] Breakdown by policy type: acceptable use, data handling, BYOD, remote work, etc.
- [ ] Green/red indicators: complete vs. missing
- [ ] Click to see: which policies missing, recommendations
- [ ] Progress tracking: "Last updated [date]"

**Story Points**: 3
**Priority**: P0
**Phase**: Demo (Phase 1)

---

#### US-3.3: View Training Launch Status
**As a** IT Manager
**I want** to see if training campaigns are launched and active
**So that** I can track awareness program deployment

**Acceptance Criteria**:
- [ ] Widget shows: "Training Status: Not Started / In Progress / Launched"
- [ ] Stats: % employees enrolled, % completed, avg completion time
- [ ] Alert if training not launched after 30 days
- [ ] Link to training module setup
- [ ] Trend: enrollments over time

**Story Points**: 3
**Priority**: P1
**Phase**: Demo (Phase 1)

---

#### US-3.4: View Quick Win Completion Status
**As a** CISO
**I want** to see which quick wins have been completed
**So that** I can demonstrate early program value

**Acceptance Criteria**:
- [ ] Checklist: AI Policy Gap Analysis (done/not done), Self-Reporting Portal (done/not done), Manager Concern Form (done/not done), HR Integration (done/not done)
- [ ] Visual progress: "3 of 4 Quick Wins Complete"
- [ ] Each quick win shows: status, date completed, impact summary
- [ ] Recommendations for incomplete quick wins
- [ ] Export quick wins summary for leadership

**Story Points**: 3
**Priority**: P0
**Phase**: Demo (Phase 1)

---

#### US-3.5: View Engagement Metrics
**As a** Risk Officer
**I want** to see employee engagement with the program
**So that** I can measure awareness and participation

**Acceptance Criteria**:
- [ ] Metrics: # of self-reports, # of manager concerns, training completion rate, policy acknowledgment rate
- [ ] Trend over time: engagement increasing/decreasing
- [ ] Benchmark: "Your engagement is [above/below] industry average"
- [ ] Recommendations to improve engagement
- [ ] Export engagement report

**Story Points**: 5
**Priority**: P1
**Phase**: Demo (Phase 1)

---

#### US-3.6: View Tool Integration Status
**As a** IT Manager
**I want** to see which tools are integrated and operational
**So that** I can ensure technical readiness

**Acceptance Criteria**:
- [ ] List of integrations: HRIS, DLP, SIEM, Identity Provider, etc.
- [ ] Status per integration: Not Connected / Connected / Data Flowing / Error
- [ ] Last sync time and data volume
- [ ] Health check: green/yellow/red per integration
- [ ] "Fix Connection" troubleshooting link

**Story Points**: 5
**Priority**: P1
**Phase**: Demo (Phase 1)

---

#### US-3.7: Receive Recommendations for Next Steps
**As a** CISO
**I want** to see what I should do next to advance the program
**So that** I can maintain momentum

**Acceptance Criteria**:
- [ ] "Recommended Next Steps" widget on dashboard
- [ ] 3-5 prioritized actions based on current state
- [ ] Each action shows: title, rationale, effort estimate, "Start Now" button
- [ ] Actions adapt based on progress (e.g., if policies done, recommend training)
- [ ] Dismiss or defer actions

**Story Points**: 5
**Priority**: P1
**Phase**: Demo (Phase 1)

---

### Theme 2: Early Detection Dashboard (Months 4-7)

#### US-3.8: View Incident Count and Trend
**As a** Security Analyst
**I want** to see total incidents and trend over time
**So that** I can monitor program activity

**Implementation Note**: Reuse Oversight PoC incident tracking methods exactly as is.

**Acceptance Criteria**:
- [ ] Widget shows: "Total Incidents: X" and trend (up/down/stable)
- [ ] Line chart: incidents per week/month
- [ ] Breakdown by source: DLP, HR, self-report, manager concern
- [ ] Breakdown by severity: critical/high/medium/low
- [ ] Click to drill down to incident list

**Story Points**: 3
**Priority**: P1
**Phase**: Demo (Phase 1)

---

#### US-3.9: View Detection Sources Breakdown
**As a** Risk Officer
**I want** to see where incidents are coming from
**So that** I can understand which detection methods are most effective

**Implementation Note**: Reuse Oversight PoC detection source tracking exactly as is.

**Acceptance Criteria**:
- [ ] Pie chart: incidents by source (DLP, HR, self-report, manager, SIEM)
- [ ] Stats: "X% from DLP, Y% from HR, Z% from self-report"
- [ ] Trend: source mix changing over time
- [ ] Insight: "DLP is your primary detection method"
- [ ] Recommendations to diversify sources if over-reliant on one

**Story Points**: 3
**Priority**: P1
**Phase**: Demo (Phase 1)

---

#### US-3.10: View Mean Time to Detect (MTTD)
**As a** Security Analyst
**I want** to see how long it takes to detect incidents
**So that** I can measure detection efficiency

**Implementation Note**: Reuse Oversight PoC MTTD calculation exactly as is.

**Acceptance Criteria**:
- [ ] Widget shows: "MTTD: X days"
- [ ] Trend: MTTD improving/worsening over time
- [ ] Benchmark: "Your MTTD is [better/worse] than industry average"
- [ ] Breakdown by detection source: DLP MTTD vs. HR MTTD
- [ ] Goal tracking: "Target MTTD: Y days"

**Story Points**: 3
**Priority**: P1
**Phase**: Demo (Phase 1)

---

#### US-3.11: View Mean Time to Respond (MTTR)
**As a** Security Analyst
**I want** to see how long it takes to respond to incidents
**So that** I can measure response efficiency

**Implementation Note**: Reuse Oversight PoC MTTR calculation exactly as is.

**Acceptance Criteria**:
- [ ] Widget shows: "MTTR: X hours"
- [ ] Trend: MTTR improving/worsening
- [ ] Benchmark comparison
- [ ] Breakdown by severity: critical MTTR vs. low MTTR
- [ ] Goal tracking

**Story Points**: 3
**Priority**: P1
**Phase**: Demo (Phase 1)

---

#### US-3.12: View False Positive Rate
**As a** CISO
**I want** to see what % of alerts are false positives
**So that** I can optimize detection rules

**Implementation Note**: Reuse Oversight PoC false positive tracking exactly as is.

**Acceptance Criteria**:
- [ ] Widget shows: "False Positive Rate: X%"
- [ ] Trend over time
- [ ] Breakdown by detection source
- [ ] Insight: "High false positives from DLP - tune rules"
- [ ] Link to tuning recommendations

**Story Points**: 3
**Priority**: P1
**Phase**: Demo (Phase 1)

---

### Theme 3: Mature Dashboard (Months 8-12)

#### US-3.13: View All 10 KPIs from Mature Program

**As a** CISO/CRO
**I want** to see all 10 comprehensive insider threat KPIs on my dashboard
**So that** I can monitor the full maturity of my insider threat program with industry-standard metrics

**Demo Implementation**: Reuse Oversight PoC dashboard exactly as is. Show existing KPI visualizations without modification.

**Acceptance Criteria (Demo)**:
- [ ] Displays Oversight PoC dashboard in "Month 12" demo mode
- [ ] Shows existing KPIs as-is from Oversight PoC
- [ ] No new development - pure visual mockup using existing assets
- [ ] Demo script explains "this is what mature dashboard looks like"

**Story Points**: 1 (demo mockup only)
**Priority**: P1
**Phase**: Demo (Phase 2)
**R1 Implementation**: Full custom KPI development deferred to R1

---

#### US-3.14: View Incident Trends Over Time

**As a** CISO
**I want** to see incident trends over months/quarters/years
**So that** I can identify patterns and seasonality

**Demo Implementation**: Reuse Oversight PoC exactly as is (demo).

**Acceptance Criteria (Demo)**:
- [ ] Displays Oversight PoC trend visualization
- [ ] Mockup only - no new development

**Story Points**: 1 (demo mockup only)
**Priority**: P1
**Phase**: Demo (Phase 2)

---

#### US-3.15: View Behavioral Analytics (if UEBA)

**As a** Security Analyst
**I want** to see user behavior analytics and anomaly scores
**So that** I can identify high-risk users proactively

**Demo Implementation**: Reuse Oversight PoC exactly as is (demo).

**Acceptance Criteria (Demo)**:
- [ ] Displays Oversight PoC UEBA visualization
- [ ] Mockup only - no new development

**Story Points**: 1 (demo mockup only)
**Priority**: P1
**Phase**: Demo (Phase 2)

---

#### US-3.16: View Predictive Insights

**As a** Risk Officer
**I want** to see AI-powered predictions of future risk trends
**So that** I can take proactive mitigation actions

**Demo Implementation**: Reuse Oversight PoC exactly as is (demo).

**Acceptance Criteria (Demo)**:
- [ ] Displays Oversight PoC predictive analytics visualization
- [ ] Mockup only - no new development

**Story Points**: 1 (demo mockup only)
**Priority**: P1
**Phase**: Demo (Phase 2)

---

#### US-3.17: View ROI Demonstration

**As a** CISO
**I want** to see ROI calculation showing program value
**So that** I can justify continued investment to leadership

**Demo Implementation**: Show "zero to mature" ROI journey with cost-benefit visualization.

**Acceptance Criteria (Demo)**:
- [ ] Static ROI calculator showing example: "You spent $X on program, prevented $Y in potential losses"
- [ ] Quick wins ROI: "AI policy gap analysis saved Z hours"
- [ ] Month 0 → Month 12 value progression visualization
- [ ] Mockup suitable for CFO/Board presentation

**Story Points**: 2 (demo mockup)
**Priority**: P0
**Phase**: Demo (Phase 2)
**R1 Implementation**: Dynamic ROI tracking with org-specific inputs deferred to R1

---

## Epic 4: Five-Phase Rollout Planner (P1, Phase 2)

**Epic Goal**: Help non-expert orgs navigate Foundation → Assessment → Implementation → Optimization → Governance phases with basic task checklists and timeline. Not a full project management tool.

### Theme 1: Phase Management

#### US-4.1: View All Five Phases Overview

**As a** IT Manager/Risk Officer
**I want** to see all five rollout phases (Foundation → Governance) with high-level descriptions
**So that** I understand the full journey from zero to mature insider threat program

**Acceptance Criteria**:
- [ ] Dashboard shows 5 phases: Foundation, Assessment, Implementation, Optimization, Governance
- [ ] Each phase shows: name, 2-sentence description, estimated duration, key deliverables
- [ ] Visual progress indicator shows which phase org is currently in
- [ ] "Learn More" expands to show detailed phase objectives
- [ ] Current phase is highlighted/emphasized

**Story Points**: 3
**Priority**: P1
**Phase**: Demo (Phase 2)

---

#### US-4.3: View Phase-Specific Task Checklist

**As a** Risk Officer
**I want** to see a detailed checklist of tasks for my current phase
**So that** I know exactly what work needs to be completed

**Acceptance Criteria (Demo - Mockup Only)**:
- [ ] Visual mockup shows example checklist for one phase (e.g., Foundation)
- [ ] Example tasks organized by category (Policy, Technology, Training, Governance)
- [ ] Mockup shows task structure: title, description, status indicator
- [ ] Demo script explains full checklist functionality coming in R1
- [ ] No functional task management in demo

**Story Points**: 1 (mockup only)
**Priority**: P1
**Phase**: Demo (Phase 2)
**R1 Implementation**: Full interactive checklist with 15-25 tasks per phase

---

#### US-4.2: Select and Enter a Phase (R1)
**Story Points**: 2
**Priority**: P1
**Phase**: R1

---

#### US-4.4: Mark Tasks Complete/In Progress (R1)
**Story Points**: 3
**Priority**: P1
**Phase**: R1

---

#### US-4.5: View Phase Prerequisites and Dependencies (R1)
**Story Points**: 3
**Priority**: P1
**Phase**: R1

---

#### US-4.6: Track Phase Completion Percentage (R1)
**Story Points**: 2
**Priority**: P1
**Phase**: R1

---

#### US-4.7: Export Phase Checklist to PDF/CSV (R1)
**Story Points**: 2
**Priority**: P2
**Phase**: R1

---

#### US-4.8: Receive Phase Completion Recommendations (R1)
**Story Points**: 3
**Priority**: P1
**Phase**: R1

---

#### US-4.9: View Estimated Time per Phase (R1)
**Story Points**: 2
**Priority**: P1
**Phase**: R1

---

### Theme 2: Timeline Visualization

#### US-4.10: View Rollout Timeline (Gantt-style) (R1)
**Story Points**: 5
**Priority**: P1
**Phase**: R1

---

#### US-4.11: Adjust Timeline Based on Org Size/Complexity (DROPPED)
**Rationale**: Not a full project management tool - basic planning features only.

---

#### US-4.12: Export Timeline to Project Management Tool (R1)
**Story Points**: 3
**Priority**: P2
**Phase**: R1

---

## Epic 5: Training & Awareness Module (P1, Phase 2)

**Epic Goal**: Provide IRMT (Insider Risk Management Training) package that orgs can host in their existing LMS. Lightweight integration.

### Theme 1: Training Module Provision

#### US-5.3: Preview IRMT Training Module

**As a** IT Manager
**I want** to preview the IRMT training module before deploying to my LMS
**So that** I can ensure content is appropriate for my organization

**Acceptance Criteria (Demo - Mockup Only)**:
- [ ] Visual mockup shows IRMT module structure and sample screens
- [ ] Example content: insider threat scenarios, policy overview, reporting channels
- [ ] Mockup shows interactive elements: quizzes, knowledge checks
- [ ] Demo script explains: "This module packages for your LMS"
- [ ] No functional training module in demo

**Story Points**: 1 (mockup only)
**Priority**: P1
**Phase**: Demo (Phase 2)

---

#### US-5.1: Download IRMT Training Package (R1)
**Story Points**: 3
**Priority**: P1
**Phase**: R1

---

#### US-5.2: Customize IRMT Content (R1)
**Story Points**: 5
**Priority**: P1
**Phase**: R1

---

#### US-5.4: View Training Completion Percentage (R1)
**Note**: May already be covered in Epic 3 metrics
**Story Points**: 2
**Priority**: P1
**Phase**: R1

---

## Epic 6: DLP Integration (P1, Phase 3)

**Epic Goal**: Integrate with DLP platforms (Microsoft Purview primary, multi-vendor support) to receive alerts and map policies.

### Theme 1: Purview Detection & Configuration

**Demo**: Simplified mockup showing Purview connection/config UI
**R1**: Full implementation

#### US-6.1: Connect to Microsoft Purview (R1)
**Story Points**: 5
**Priority**: P1
**Phase**: R1

---

#### US-6.2: Configure DLP Policies in Purview (R1)
**Story Points**: 5
**Priority**: P1
**Phase**: R1

---

#### US-6.3: Map Purview Policies to Insider Risk Scenarios (R1)
**Story Points**: 5
**Priority**: P1
**Phase**: R1

---

#### US-6.4: View Purview Policy Status/Health (R1)
**Story Points**: 3
**Priority**: P1
**Phase**: R1

---

#### US-6.5: Test DLP Detection Rules (R1)
**Story Points**: 3
**Priority**: P1
**Phase**: R1

---

#### US-6.6: Sync Purview Policy Changes (R1)
**Story Points**: 3
**Priority**: P1
**Phase**: R1

---

### Theme 2: Alert Integration

**Demo**: Simplified mockup showing DLP alerts in dashboard
**R1**: Full implementation

#### US-6.7: Receive DLP Alerts from Purview (R1)
**Story Points**: 5
**Priority**: P1
**Phase**: R1

---

#### US-6.8: View DLP Alerts in Dashboard (R1)
**Story Points**: 3
**Priority**: P1
**Phase**: R1

---

#### US-6.9: Triage DLP Alerts (R1)
**Story Points**: 5
**Priority**: P1
**Phase**: R1

---

#### US-6.10: Link DLP Alerts to Incidents (R1)
**Story Points**: 3
**Priority**: P1
**Phase**: R1

---

#### US-6.11: Configure Alert Severity Thresholds (R1)
**Story Points**: 3
**Priority**: P1
**Phase**: R1

---

### Theme 3: Vendor Support

**Demo**: Mockup showing multi-vendor connection options (Symantec, Forcepoint, Digital Guardian)
**R1**: Full implementation

#### US-6.12: Connect to Symantec DLP (R1)
**Story Points**: 5
**Priority**: P2
**Phase**: R1

---

#### US-6.13: Connect to Forcepoint DLP (R1)
**Story Points**: 5
**Priority**: P2
**Phase**: R1

---

#### US-6.14: Connect to Digital Guardian DLP (R1)
**Story Points**: 5
**Priority**: P2
**Phase**: R1

---

#### US-6.15: View Multi-Vendor DLP Alerts in Unified Dashboard (R1)
**Story Points**: 5
**Priority**: P2
**Phase**: R1

---

## Epic 7: Oversight Features - Adapted (P1, Phase 3)

**Epic Goal**: Demonstrate mature insider threat capabilities by reusing Barclays Oversight PoC exactly as-is. All 6 features shown as "Month 12" mature state mockups.

**Demo Implementation**: Reuse all Oversight PoC assets, visualizations, and workflows without modification. All stories are 1-point demo mockups.

### Theme 1: Framework Mapping (5 stories)

#### US-7.1: Map Controls to Frameworks (NIST, ISO, etc.)
**Demo**: Show Oversight PoC framework mapping UI as-is
**Story Points**: 1
**Priority**: P1
**Phase**: Demo (Phase 2)

#### US-7.2: View Framework Compliance Status
**Demo**: Show Oversight PoC compliance dashboard as-is
**Story Points**: 1
**Priority**: P1
**Phase**: Demo (Phase 2)

#### US-7.3: Generate Framework Gap Report
**Demo**: Show Oversight PoC gap report as-is
**Story Points**: 1
**Priority**: P1
**Phase**: Demo (Phase 2)

#### US-7.4: Track Framework Updates
**Demo**: Show Oversight PoC framework versioning as-is
**Story Points**: 1
**Priority**: P2
**Phase**: Demo (Phase 2)

#### US-7.5: Export Framework Mapping
**Demo**: Show Oversight PoC export functionality as-is
**Story Points**: 1
**Priority**: P2
**Phase**: Demo (Phase 2)

---

### Theme 2: Volume & Framework Baseline (3 stories)

#### US-7.6: View Data Volume Baselines
**Demo**: Show Oversight PoC volume baseline dashboards as-is
**Story Points**: 1
**Priority**: P1
**Phase**: Demo (Phase 2)

#### US-7.7: Detect Volume Anomalies
**Demo**: Show Oversight PoC anomaly detection as-is
**Story Points**: 1
**Priority**: P1
**Phase**: Demo (Phase 2)

#### US-7.8: Set Custom Baseline Thresholds
**Demo**: Show Oversight PoC threshold configuration as-is
**Story Points**: 1
**Priority**: P2
**Phase**: Demo (Phase 2)

---

### Theme 3: Controls Mapping (4 stories)

#### US-7.9: Map Technical Controls to Risks
**Demo**: Show Oversight PoC controls mapping interface as-is
**Story Points**: 1
**Priority**: P1
**Phase**: Demo (Phase 2)

#### US-7.10: View Control Coverage Gaps
**Demo**: Show Oversight PoC coverage dashboard as-is
**Story Points**: 1
**Priority**: P1
**Phase**: Demo (Phase 2)

#### US-7.11: Prioritize Control Deployments
**Demo**: Show Oversight PoC prioritization matrix as-is
**Story Points**: 1
**Priority**: P1
**Phase**: Demo (Phase 2)

#### US-7.12: Track Control Effectiveness
**Demo**: Show Oversight PoC effectiveness metrics as-is
**Story Points**: 1
**Priority**: P2
**Phase**: Demo (Phase 2)

---

### Theme 4: Threat Intelligence (3 stories)

#### US-7.13: Integrate Threat Intelligence Feeds
**Demo**: Show Oversight PoC threat feed integration as-is
**Story Points**: 1
**Priority**: P1
**Phase**: Demo (Phase 2)

#### US-7.14: View Industry-Specific Threat Trends
**Demo**: Show Oversight PoC threat trend visualizations as-is
**Story Points**: 1
**Priority**: P1
**Phase**: Demo (Phase 2)

#### US-7.15: Map Threats to Your Environment
**Demo**: Show Oversight PoC threat mapping as-is
**Story Points**: 1
**Priority**: P2
**Phase**: Demo (Phase 2)

---

### Theme 5: Org Risk Viewer (3 stories)

#### US-7.16: View Organization-Wide Risk Heat Map
**Demo**: Show Oversight PoC risk heat map as-is
**Story Points**: 1
**Priority**: P1
**Phase**: Demo (Phase 2)

#### US-7.17: Drill Down by Department/Business Unit
**Demo**: Show Oversight PoC drill-down interface as-is
**Story Points**: 1
**Priority**: P1
**Phase**: Demo (Phase 2)

#### US-7.18: View Risk Score Trends Over Time
**Demo**: Show Oversight PoC risk trend charts as-is
**Story Points**: 1
**Priority**: P2
**Phase**: Demo (Phase 2)

---

### Theme 6: Reporting (3 stories)

#### US-7.19: Generate Executive Risk Report
**Demo**: Show Oversight PoC executive report as-is
**Story Points**: 1
**Priority**: P1
**Phase**: Demo (Phase 2)

#### US-7.20: Schedule Automated Reports
**Demo**: Show Oversight PoC report scheduling as-is
**Story Points**: 1
**Priority**: P2
**Phase**: Demo (Phase 2)

#### US-7.21: Customize Report Templates
**Demo**: Show Oversight PoC template editor as-is
**Story Points**: 1
**Priority**: P2
**Phase**: Demo (Phase 2)

---

## Epic 8: Demo Mode System (P1, Phase 2)

**Epic Goal**: Allow users to toggle between Month 0 (just starting), Month 6 (early detection), and Month 12 (mature program) demo states with appropriate data/features visible per mode.

### Theme 1: Mode Selection

#### US-8.1: Select Demo Mode (Month 0/6/12)

**As a** CISO doing a product demo
**I want** to select which program maturity stage to demonstrate
**So that** I can show prospects what the platform looks like at different stages

**Acceptance Criteria**:
- [ ] Settings menu includes "Demo Mode" selector
- [ ] Three options: "Month 0 - Getting Started", "Month 6 - Early Detection", "Month 12 - Mature Program"
- [ ] Selection persists across sessions
- [ ] Mode change triggers dashboard/data refresh
- [ ] Confirmation prompt: "Switch to [Mode]? This will change visible features and data."

**Story Points**: 3
**Priority**: P0
**Phase**: Demo (Phase 2)

---

### Theme 2: Data Population

#### US-8.6: Auto-Populate Month 0 Data

**As a** system
**I want** to show appropriate data for Month 0 mode
**So that** demos reflect realistic "just starting" state

**Acceptance Criteria**:
- [ ] Month 0 shows: 0 incidents, incomplete policies, 0% training completion, not-connected integrations
- [ ] Readiness score: 15-25%
- [ ] Priority Picker results visible
- [ ] Generated PPTX visible
- [ ] All "Quick Wins" marked "Not Started"

**Story Points**: 3
**Priority**: P0
**Phase**: Demo (Phase 2)

---

#### US-8.7: Auto-Populate Month 6 Data

**As a** system
**I want** to show appropriate data for Month 6 mode
**So that** demos reflect realistic "early detection" state

**Acceptance Criteria**:
- [ ] Month 6 shows: 8-12 incidents (mixed sources), partial policy coverage (60-70%), 50-60% training completion, HR+basic DLP connected
- [ ] Readiness score: 55-65%
- [ ] Quick Wins: 3 of 4 complete
- [ ] MTTD/MTTR metrics visible
- [ ] Some false positives logged

**Story Points**: 5
**Priority**: P0
**Phase**: Demo (Phase 2)

---

#### US-8.8: Auto-Populate Month 12 Data

**As a** system
**I want** to show appropriate data for Month 12 mode
**So that** demos reflect realistic "mature program" state

**Acceptance Criteria**:
- [ ] Month 12 shows: 25-35 incidents (diverse sources), full policy coverage (95%+), 85%+ training completion, all integrations connected
- [ ] Readiness score: 90-95%
- [ ] All 10 KPIs visible with healthy trends
- [ ] Oversight PoC features active
- [ ] ROI demonstration showing value

**Story Points**: 5
**Priority**: P0
**Phase**: Demo (Phase 2)

---

#### US-8.9: Randomize Demo Data Slightly (R1)
**Story Points**: 3
**Priority**: P2
**Phase**: R1

---

#### US-8.10: Industry-Specific Demo Data

**As a** sales user
**I want** to populate demo data appropriate for prospect's industry
**So that** scenarios feel relevant

**Acceptance Criteria**:
- [ ] Select industry: Financial, Healthcare, Technology, Manufacturing, Retail
- [ ] Incident scenarios tailored to industry (e.g., HIPAA for healthcare)
- [ ] Policy templates match industry standards
- [ ] Threat intelligence shows industry-specific trends
- [ ] Framework compliance defaults to industry norms (SOX, HIPAA, PCI, etc.)

**Story Points**: 8
**Priority**: P1
**Phase**: Demo (Phase 2)

---

### Theme 3: Feature Visibility & Transitions

#### US-8.11: Show/Hide Features by Mode

**As a** system
**I want** to show only features appropriate for each maturity stage
**So that** demos don't confuse prospects with irrelevant capabilities

**Acceptance Criteria**:
- [ ] Month 0: Only Priority Picker, PPTX Generator, Policy Gap Analysis, Account Setup visible
- [ ] Month 6: Add HR Integration, Incident Logging, Basic Dashboard, Training visible
- [ ] Month 12: Add all Oversight features, full KPIs, DLP, advanced analytics visible
- [ ] Hidden features grayed out with "Unlock at Month X" tooltip
- [ ] Progressive disclosure: features appear as mode advances

**Story Points**: 8
**Priority**: P0
**Phase**: Demo (Phase 2)

---

#### US-8.12: Show Mode-Appropriate Messaging

**As a** user
**I want** to see contextual messaging for my current mode
**So that** I understand what actions are appropriate

**Acceptance Criteria**:
- [ ] Month 0: "Welcome! Let's build your program foundation" messaging
- [ ] Month 6: "Great progress! You're detecting threats" messaging
- [ ] Month 12: "Your mature program is running smoothly" messaging
- [ ] Dashboard welcome cards adapt to mode
- [ ] Recommendations change per mode

**Story Points**: 3
**Priority**: P1
**Phase**: Demo (Phase 2)

---

#### US-8.13: Animate Mode Transitions (R1)
**Story Points**: 3
**Priority**: P2
**Phase**: R1

---

**Dropped Stories**:
- US-8.2: View Current Demo Mode Indicator
- US-8.3: Reset Demo Data
- US-8.4: Save Custom Demo Scenarios
- US-8.5: Quick Mode Switcher (Keyboard Shortcut)
- US-8.14: Compare Modes Side-by-Side
- US-8.15: Export Mode-Specific Screenshots

---

## Epic 9: Content Management (P2, Phase 3)

**Epic Goal**: Provide industry-swappable content packs for financial, healthcare, tech, manufacturing, retail sectors.

### Theme 1: Industry Content Packs

#### US-9.1: Browse Available Industry Packs

**As a** IT Manager
**I want** to browse available industry content packs
**So that** I can select content appropriate for my organization

**Acceptance Criteria**:
- [ ] Content library shows: Financial Services, Healthcare, Technology, Manufacturing, Retail packs
- [ ] Each pack preview shows: included policies, scenarios, frameworks, templates
- [ ] Industry-specific compliance mappings highlighted (SOX, HIPAA, PCI, etc.)
- [ ] Search and filter packs by industry or framework
- [ ] "Install Pack" button per industry

**Story Points**: 3
**Priority**: P2
**Phase**: R1

---

#### US-9.2: Install Industry Pack (Financial/Healthcare/Tech/Mfg/Retail)

**As a** Risk Officer
**I want** to install an industry-specific content pack
**So that** policies, scenarios, and templates match my sector

**Acceptance Criteria**:
- [ ] Select industry pack and click "Install"
- [ ] Installation progress indicator
- [ ] Pack contents imported: policies, incident scenarios, training content, framework mappings
- [ ] Confirmation: "Financial Services pack installed successfully"
- [ ] Pack becomes active industry context

**Story Points**: 5
**Priority**: P2
**Phase**: R1

---

#### US-9.6: Switch Active Industry Pack

**As a** demo user
**I want** to switch between installed industry packs
**So that** I can demo the platform for different prospect industries

**Acceptance Criteria**:
- [ ] Settings: "Active Industry Pack" dropdown
- [ ] Select different installed pack
- [ ] Warning: "Switching packs will change policies, scenarios, and frameworks. Continue?"
- [ ] Content swaps immediately (policies, scenarios, compliance mappings)
- [ ] Demo data adapts to new industry context

**Story Points**: 5
**Priority**: P1
**Phase**: Demo (Phase 2)

---

**Dropped Stories**:
- US-9.3: Preview Pack Contents Before Installing
- US-9.4: View Installed Packs
- US-9.5: Uninstall/Remove Industry Pack
- US-9.7: Merge Multiple Packs
- US-9.8: Customize Pack Content
- US-9.9: Export Custom Pack
- US-9.10: View Included Frameworks
- US-9.11: Customize Framework Mappings
- US-9.12: Add Custom Policy Templates
- US-9.13: Edit Incident Scenario Templates
- US-9.14: Manage Training Content by Industry
- US-9.15: Version Control for Content Changes

---

## Epic 10: Incident Management (P2, Phase 3)

**Epic Goal**: Full incident investigation workflow with case management.

**Scope**: All incident management stories deferred to R1 (post-demo).

**Note**: Basic incident logging already covered in Epic 2 (US-2.14: Log Manual Incidents, US-2.15: View Incident Log) for demo purposes.

**Deferred Features (R1)**:
- Theme 1: Advanced Incident Logging (6 stories)
- Theme 2: Investigation Workflow (5 stories)
- Theme 3: Incident Reporting (4 stories)

**Total Deferred**: ~15 stories to R1

---

## Story Count Summary

### All Epics (Final Count):

**Epic 1: User Onboarding & Discovery**
- 10 stories total (7 demo, 3 R1)

**Epic 2: Quick Wins - Pre-DLP Value**
- 11 stories total (9 demo, 2 themes deferred to R1)

**Epic 3: Dashboard & Metrics - Adaptive**
- 17 stories total (12 demo functional, 5 demo mockups)

**Epic 4: Five-Phase Rollout Planner**
- 12 stories total (2 demo, 9 R1, 1 dropped)

**Epic 5: Training & Awareness Module**
- 4 stories total (1 demo mockup, 3 R1)

**Epic 6: DLP Integration**
- 15 stories total (all R1, 3 themes noted as demo mockups)

**Epic 7: Oversight Features - Adapted**
- 21 stories total (all demo mockups reusing Oversight PoC)

**Epic 8: Demo Mode System**
- 9 stories total (7 demo, 2 R1, 6 dropped)

**Epic 9: Content Management**
- 3 stories total (1 demo, 2 R1, 12 dropped)

**Epic 10: Incident Management**
- All stories deferred to R1 (~15 stories estimated)

---

### Final Totals:

**Total Stories Documented**: 102 stories
**Demo Scope**: ~60 stories (functional + mockups)
**R1 Scope**: ~42 stories
**Dropped**: ~20 stories

---

## Demo Story Breakdown by Type:

**Functional Demo Features** (Full implementation for demo):
- Epic 1: Priority Picker, PPTX Generator, Account Setup (7 stories)
- Epic 2: AI Policy Gap Analysis, HR Integration, Basic Incident Logging (9 stories)
- Epic 3: Zero-Incident Dashboard, Early Detection Dashboard (12 stories)
- Epic 4: Phase Overview, Phase Checklist Mockup (2 stories)
- Epic 8: Mode Selection, Data Population, Feature Visibility (7 stories)
- Epic 9: Switch Industry Pack (1 story)

**Demo Mockups** (Visual only, reuse Oversight PoC):
- Epic 3: Mature Dashboard (5 mockups)
- Epic 5: IRMT Training Preview (1 mockup)
- Epic 6: DLP Integration UI (3 theme mockups)
- Epic 7: All Oversight Features (21 mockups)

---

**Document Version**: 2.0
**Last Updated**: 2025-11-01
**Status**: Complete - All 10 Epics Documented

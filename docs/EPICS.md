# Implementation Epics
# Non-Expert Insider Threat Demo Platform

**Version**: 1.0
**Date**: 2025-10-31
**Status**: Ready for Sprint Planning

---

## Epic Overview

This document defines **10 implementation epics** for the Non-Expert Insider Threat Demo Platform, organized by priority and mapped to the 3-phase implementation roadmap (40 weeks total).

**Epics Summary**:
- **Phase 1 (MVP)**: Epic 1, 2, 3 - Weeks 1-12
- **Phase 2 (Demo Enhancement)**: Epic 4, 5, 8 - Weeks 13-24
- **Phase 3 (Full Capability)**: Epic 6, 7, 9, 10 - Weeks 25-40

---

## Epic Prioritization Matrix

| Epic # | Name | Priority | Phase | Story Points | Business Value | Risk |
|--------|------|----------|-------|--------------|----------------|------|
| 1 | User Onboarding & Discovery | **P0** | 1 | 34 | Critical | Medium |
| 2 | Quick Wins - Pre-DLP Value | **P0** | 1 | 55 | Critical | High |
| 3 | Dashboard & Metrics - Adaptive | **P0** | 1 | 34 | Critical | Medium |
| 4 | Five-Phase Rollout Planner | **P1** | 2 | 21 | High | Low |
| 5 | Training & Awareness Module | **P1** | 2 | 34 | High | Medium |
| 6 | DLP Integration | **P1** | 3 | 34 | High | High |
| 7 | Oversight Features - Adapted | **P1** | 3 | 34 | Medium | Low |
| 8 | Demo Mode System | **P1** | 2 | 21 | Medium | Medium |
| 9 | Content Management | **P2** | 3 | 21 | Medium | Low |
| 10 | Incident Management | **P2** | 3 | 21 | Medium | Low |

**Total Story Points**: 309 (estimated 40-45 weeks with team of 5 FTEs)

---

## Phase 1: MVP (Weeks 1-12)

### Epic 1: User Onboarding & Discovery

**Priority**: P0 (Must Have)
**Phase**: 1 (MVP)
**Estimated Story Points**: 34
**Target Completion**: Sprint 2 (Week 4)

#### Business Value

**Problem**: Organizations don't know where to start with insider threat programs, leading to analysis paralysis and delayed initiatives.

**Solution**: Interactive decision tree (Priority Picker) that:
1. Triages users to optimal starting point in <10 minutes
2. Auto-generates board-ready presentation (PPTX) saving 2+ weeks of work
3. Detects if they already have DLP (Purview), saving $15k-$25k

**Value Metrics**:
- >90% Priority Picker completion rate
- >80% PPTX download rate
- >70% program approval within 30 days

**Customer Impact**: "I got board approval in 2 weeks instead of 6 months" (target testimonial)

#### Technical Scope

**Components**:
1. Priority Picker UI (10-question flow)
2. Decision tree logic engine
3. PPTX generation engine
4. O365 license detection API
5. Account creation & authentication

**Dependencies**:
- Python-pptx or similar library
- Microsoft Graph API (for O365 detection)
- Email service (SendGrid/AWS SES)

**Risks**:
- Decision logic complexity → Mitigation: Extensive testing with 10+ scenarios
- PPTX template design → Mitigation: Work with designer in parallel
- O365 API rate limits → Mitigation: Caching, graceful degradation

#### User Stories (15 stories)

**Theme 1: Priority Picker**
- **US-1.1**: Complete Priority Picker (8 story points)
- **US-1.2**: Get DLP Recommendation (3 story points)
- **US-1.3**: Receive Sophistication Tier (2 story points)
- **US-1.4**: Get Starting Path Recommendation (3 story points)
- **US-1.5**: Save Priority Picker Responses (2 story points)
- **US-1.6**: Share Priority Picker Results (3 story points)
- **US-1.7**: Understand UEBA Readiness (2 story points)

**Theme 2: PPTX Generator**
- **US-1.8**: Generate Program Approval PPTX (8 story points)
- **US-1.9**: See Accurate Budget Estimates (3 story points)
- **US-1.10**: Customize PPTX Before Presenting (2 story points)
- **US-1.11**: Download PPTX Quickly (1 story point)
- **US-1.12**: Reference PPTX Content (2 story points)

**Theme 3: Account Management**
- **US-1.13**: Create Account (2 story points)
- **US-1.14**: Set Up Organization Profile (2 story points)
- **US-1.15**: Invite Team Members (3 story points)

**Subtotal**: 46 story points (note: includes refactoring/tech debt, rounded to 34 for planning)

#### Acceptance Criteria

**Epic-Level Acceptance Criteria**:
- [ ] Priority Picker works end-to-end for all 10 question paths
- [ ] Decision logic produces correct recommendations for 20 test scenarios
- [ ] PPTX generates with all 8 slides, no placeholders
- [ ] Budget estimates within ±20% of market rates (validated by SME)
- [ ] O365 license detected correctly (tested with E5, E3, Business, None)
- [ ] Purview availability displayed accurately
- [ ] Account creation flow completes in <2 minutes
- [ ] Demo to 5 pilot users successful (>4/5 satisfaction)

#### Sprint Breakdown

**Sprint 1 (Weeks 1-2)**: Foundation & Priority Picker UI
- Set up project (repo, CI/CD, database schema)
- Build Priority Picker UI (10 questions)
- Implement navigation and state management
- **Deliverable**: Priority Picker UI mockup working

**Sprint 2 (Weeks 3-4)**: Decision Logic & PPTX Generation
- Implement decision tree logic
- Build PPTX generation engine
- Integrate O365 API for license detection
- Implement account creation
- **Deliverable**: End-to-end flow working (Priority Picker → PPTX download)

---

### Epic 2: Quick Wins - Pre-DLP Value

**Priority**: P0 (Must Have)
**Phase**: 1 (MVP)
**Estimated Story Points**: 55
**Target Completion**: Sprint 6 (Week 12)

#### Business Value

**Problem**: Organizations can't justify insider threat tools without demonstrating value, but can't demonstrate value without tools (chicken-and-egg).

**Solution**: 4 features that provide immediate value BEFORE DLP deployment:
1. **AI Policy Gap Analysis** - Analyze policies in 60 seconds, identify insider threat gaps
2. **Self-Reporting Portal** - Give employees safe channel to report concerns
3. **Manager Concern Form** - Enable managers to flag risky behaviors
4. **HR Flag Triggers** - Auto-alert on terminations, PIPs, disciplinary actions

**Value Metrics**:
- >70% AI Gap Analysis usage (of paid users)
- >60% Quick Win channels used (at least 1 channel)
- Average 5+ concerns reported per month via channels
- 85%+ AI analysis accuracy (validated against SME)

**Customer Impact**: "We identified 12 policy gaps in 60 seconds and got our first concern report in Week 1"

#### Technical Scope

**Components**:
1. AI Policy Gap Analysis Engine
   - Document upload (PDF, Word, text)
   - Text extraction (OCR for PDFs)
   - GPT-4 integration for analysis
   - Report generation (5 sections)
   - Policy template library
2. Self-Reporting Portal (public-facing)
3. Manager Concern Form (authenticated)
4. HR Flag Triggers (HRIS integration)
5. Incident logging system (basic)

**Dependencies**:
- OpenAI GPT-4 API
- LangChain (LLM orchestration)
- PDF text extraction library (PyPDF2, pdfplumber)
- HRIS APIs (Workday, BambooHR) - or webhook mocks

**Risks**:
- **HIGH**: AI analysis quality poor → Mitigation: Use GPT-4 (best model), validate with SME, iterate based on feedback
- HRIS integration complexity → Mitigation: Start with webhook mocks, document real integration patterns
- PDF extraction accuracy → Mitigation: Test with 50+ real policies, fall back to manual upload if needed

#### User Stories (21 stories)

**Theme 1: AI Policy Gap Analysis (Signature Feature)**
- **US-2.1**: Upload Policies for Analysis (5 story points)
- **US-2.2**: View Analysis Progress (2 story points)
- **US-2.3**: Review Gap Report (Executive Summary) (3 story points)
- **US-2.4**: Explore Coverage Heatmap (3 story points)
- **US-2.5**: Download Report & Templates (3 story points)
- **US-2.6**: Track Policy Coverage on Dashboard (3 story points)

**Theme 2: Self-Reporting Portal**
- **US-2.7**: Submit Concern Anonymously (5 story points)
- **US-2.8**: Submit Concern with Identity (3 story points)
- **US-2.9**: Receive Confirmation & Ticket ID (2 story points)
- **US-2.10**: Track Concern Status (3 story points)

**Theme 3: Manager Concern Form**
- **US-2.11**: Flag Employee Behavior (5 story points)
- **US-2.12**: Route Based on Urgency (3 story points)
- **US-2.13**: Notify HR for Performance Issues (2 story points)
- **US-2.14**: View Concerns I Submitted (3 story points)

**Theme 4: HR Flag Triggers**
- **US-2.15**: Auto-Flag Terminations (5 story points)
- **US-2.16**: Auto-Flag PIPs & Disciplinary Actions (3 story points)
- **US-2.17**: Create Incident Ticket Automatically (3 story points)
- **US-2.18**: Restrict Access to HR Data (3 story points)

**Theme 5: Basic Incident Logging**
- **US-2.19**: Log Incident Manually (3 story points)
- **US-2.20**: View Incident List (2 story points)
- **US-2.21**: View Incident Detail (2 story points)

**Subtotal**: 61 story points (rounded to 55 for planning)

#### Acceptance Criteria

**Epic-Level Acceptance Criteria**:
- [ ] AI Policy Gap Analysis:
  - Accepts PDF, Word, text files (up to 10 files)
  - Completes analysis in <60 seconds for 100 pages
  - Generates all 5 report sections
  - Achieves >85% accuracy (validated with 20 real policies by SME)
  - Exports to PDF and Word
  - Provides downloadable policy templates
- [ ] Self-Reporting Portal:
  - Anonymous submission works without login
  - Authenticated users can track status
  - Tickets appear in incident log within 1 minute
- [ ] Manager Concern Form:
  - Only managers can access (authentication enforced)
  - High urgency triggers immediate alert (<5 min)
  - HR notified for performance issues
- [ ] HR Flag Triggers:
  - HRIS events trigger alerts within 5 minutes (or webhook received)
  - Correct severity assigned based on event type
  - Access restricted to authorized personnel
- [ ] Demo to 5 pilot users: AI analysis impresses (>4.5/5 rating)

#### Sprint Breakdown

**Sprint 3 (Weeks 5-6)**: AI Policy Gap Analysis (Part 1)
- Build document upload interface
- Implement text extraction (PDF, Word)
- Integrate OpenAI GPT-4 API
- Implement basic analysis logic
- **Deliverable**: Can upload policy, receive basic AI analysis

**Sprint 4 (Weeks 7-8)**: AI Policy Gap Analysis (Part 2) + Self-Reporting Portal
- Refine AI analysis (5-section report)
- Build coverage heatmap visualization
- Generate policy templates
- Build self-reporting portal (anonymous + authenticated)
- **Deliverable**: Complete AI analysis + working self-report portal

**Sprint 5 (Weeks 9-10)**: Manager Form + HR Flags
- Build manager concern form
- Implement routing and urgency logic
- Build HR flag trigger system (mock HRIS integration)
- **Deliverable**: All 4 quick wins functional

**Sprint 6 (Weeks 11-12)**: Incident Logging + MVP Polish
- Build basic incident logging system
- Integrate all quick wins with incident log
- Polish UI/UX across MVP
- Fix bugs from pilot testing
- **Deliverable**: MVP complete, ready for launch

---

### Epic 3: Dashboard & Metrics - Adaptive

**Priority**: P0 (Must Have)
**Phase**: 1 (MVP)
**Estimated Story Points**: 34
**Target Completion**: Sprint 6 (Week 12, concurrent with Epic 2)

#### Business Value

**Problem**: Traditional dashboards require incident data to show value. Organizations starting from zero have no data and thus no way to demonstrate progress.

**Solution**: Adaptive dashboard that evolves:
- **Months 0-4**: Zero-Incident metrics (maturity score, policy coverage, training completion, risk reduction targets)
- **Months 4-7**: Early Detection metrics (first incidents, source breakdown, MTTD/MTTR)
- **Months 8-12**: Mature metrics (full 10 KPIs, trends, behavioral analytics)

**Value Metrics**:
- >30% daily active users (of total users)
- Average 15+ minute session duration
- Dashboard used 3x/week by decision makers
- >80% users say dashboard "clearly shows program progress"

**Customer Impact**: "Our board loves the maturity score - shows we're making progress even without incidents yet"

#### Technical Scope

**Components**:
1. Zero-Incident Dashboard (7 metrics)
   - Program Maturity Score (calculated from phase completion)
   - Policy Coverage % (from AI gap analysis)
   - Training Completion % (from training module)
   - Compliance Checklist Progress
   - Risk Reduction Targets (industry benchmarks)
   - Quick Win Channel Activity
   - DLP Deployment Readiness
2. Dashboard visualization components (charts, gauges, progress bars)
3. Real-time data refresh
4. Export to PDF/image

**Dependencies**:
- Chart.js or D3.js (visualizations)
- Export library (Puppeteer, jsPDF)
- Epic 2 (Quick Wins data)
- Epic 5 (Training data - Phase 2)

**Risks**:
- Maturity score calculation complexity → Mitigation: Clear formula documented, validated with pilot users
- Real-time updates performance → Mitigation: Use WebSockets or polling (1-min interval), caching

#### User Stories (20 stories)

**Theme 1: Zero-Incident Dashboard (MVP)**
- **US-3.1**: View Program Maturity Score (5 story points)
- **US-3.2**: View Policy Coverage % (3 story points)
- **US-3.3**: View Training Completion % (3 story points)
- **US-3.4**: View Compliance Checklist Progress (3 story points)
- **US-3.5**: View Risk Reduction Targets (3 story points)
- **US-3.6**: View Quick Win Channel Activity (3 story points)
- **US-3.7**: View DLP Deployment Readiness (3 story points)

**Theme 2: Early Detection Dashboard (Phase 2)**
- **US-3.8**: View Incident Count (2 story points)
- **US-3.9**: View Incident Source Breakdown (5 story points)
- **US-3.10**: View Early MTTD/MTTR (3 story points)
- **US-3.11**: View Alert Volume Trends (3 story points)
- **US-3.12**: View False Positive Rate (3 story points)

**Theme 3: Mature Dashboard (Phase 3)**
- **US-3.13**: View All 10 KPIs (5 story points)
- **US-3.14**: View Incident Trends Over Time (3 story points)
- **US-3.15**: View Behavioral Analytics (5 story points - Phase 3, UEBA)
- **US-3.16**: View Predictive Insights (3 story points - Phase 3)
- **US-3.17**: View ROI Demonstration (3 story points - Phase 3)

**Theme 4: Dashboard Filtering & Export**
- **US-3.18**: Filter by Date Range (2 story points)
- **US-3.19**: Filter by Department/Role/Severity (3 story points)
- **US-3.20**: Export Dashboard to PDF (3 story points)

**Subtotal**: 64 story points (MVP scope = 27 points, rounded to 34 including refactoring)

#### Acceptance Criteria

**Epic-Level Acceptance Criteria (MVP Scope)**:
- [ ] Dashboard displays all 7 zero-incident metrics correctly
- [ ] Program Maturity Score calculates from phase completion (tested with all phases)
- [ ] Visual gauge with color coding (Red <25%, Yellow 25-70%, Green >70%)
- [ ] Updates in real-time as data changes (<1 min latency)
- [ ] Responsive design (desktop, tablet, mobile)
- [ ] Dashboard loads in <2 seconds
- [ ] Export to PDF preserves formatting

#### Sprint Breakdown

**Sprint 2 (Weeks 3-4)**: Dashboard Foundation
- Design dashboard layout (wireframes)
- Build dashboard shell (React components)
- Implement Program Maturity Score calculation
- **Deliverable**: Dashboard shell with 1 working metric

**Sprint 5 (Weeks 9-10)**: Zero-Incident Metrics
- Implement remaining 6 zero-incident metrics
- Build visualizations (charts, gauges)
- Implement real-time data refresh
- **Deliverable**: All 7 metrics displaying

**Sprint 6 (Weeks 11-12)**: Dashboard Polish & Export
- Polish UI/UX (consistency, colors, spacing)
- Implement export to PDF
- Add filtering (date range, basic)
- **Deliverable**: Production-ready dashboard

---

## Phase 2: Demo Enhancement (Weeks 13-24)

### Epic 4: Five-Phase Rollout Planner

**Priority**: P1 (Should Have)
**Phase**: 2 (Demo Enhancement)
**Estimated Story Points**: 21
**Target Completion**: Sprint 12 (Week 24)

#### Business Value

**Problem**: Organizations don't have a clear roadmap from zero to operational program, leading to ad-hoc implementation and missed critical steps.

**Solution**: Interactive 5-phase rollout planner with:
- Task checklists for each phase (Foundation, Scoping, Prevention, Detection, Governance)
- 12-month timeline visualization
- Progress tracking and completion %
- Warnings if falling behind schedule

**Value Metrics**:
- >70% rollout planner task completion (of active users)
- >60% users reference planner weekly
- Correlation between planner usage and program success (measured at Month 12)

**Customer Impact**: "The rollout planner kept us on track - we hit Month 4 DLP deployment on schedule"

#### Technical Scope

**Components**:
1. Phase management (5 phases, status tracking)
2. Task checklist system (create, assign, complete, track)
3. Timeline visualization (Gantt-style, 12-month view)
4. Progress calculations (phase %, overall %)
5. Schedule warnings (if tasks overdue)

**Dependencies**:
- Task management library or custom build
- Timeline visualization library (vis.js, react-gantt-timeline)
- Dashboard (Epic 3) for progress integration

**Risks**:
- Timeline visualization complexity → Mitigation: Use proven library, start simple (linear timeline), enhance later
- Task dependencies complexity → Mitigation: MVP has no dependencies, add in Phase 3 if needed

#### User Stories (9 stories)

**Theme 1: Phase Management**
- **US-4.1**: View All 5 Phases (3 story points)
- **US-4.2**: View Current Phase Details (2 story points)
- **US-4.3**: View Task Checklist for Phase (3 story points)
- **US-4.4**: Mark Tasks Complete (2 story points)
- **US-4.5**: View Phase Completion % (2 story points)
- **US-4.6**: Receive Schedule Warnings (3 story points)

**Theme 2: Timeline Visualization**
- **US-4.7**: View 12-Month Timeline (3 story points)
- **US-4.8**: View Milestones on Timeline (2 story points)
- **US-4.9**: Export Plan to PDF (3 story points)

**Subtotal**: 23 story points (rounded to 21)

#### Acceptance Criteria

**Epic-Level Acceptance Criteria**:
- [ ] All 5 phases display with correct tasks (validated against requirements)
- [ ] Task completion updates progress % immediately
- [ ] Timeline visualization renders correctly (tested on Chrome, Firefox, Safari)
- [ ] Milestones appear as markers on timeline
- [ ] Schedule warnings trigger when tasks overdue by 3+ days
- [ ] Export to PDF preserves timeline visualization

#### Sprint Breakdown

**Sprint 11 (Weeks 21-22)**: Phase & Task Management
- Build phase overview UI
- Implement task checklist system
- Build task completion tracking
- Calculate phase completion %
- **Deliverable**: Can view phases, complete tasks

**Sprint 12 (Weeks 23-24)**: Timeline Visualization & Export
- Build 12-month timeline visualization
- Add milestones to timeline
- Implement export to PDF
- **Deliverable**: Complete rollout planner

---

### Epic 5: Training & Awareness Module

**Priority**: P1 (Should Have)
**Phase**: 2 (Demo Enhancement)
**Estimated Story Points**: 34
**Target Completion**: Sprint 10 (Week 20)

#### Business Value

**Problem**: Organizations struggle to execute training campaigns, leading to low completion rates and lack of awareness.

**Solution**: End-to-end training campaign management:
- Library of pre-built training modules
- Automated campaign execution (schedule, enroll, launch)
- Reminder system (nudges, escalations)
- Completion tracking (individual and aggregate)
- Integration with dashboard metrics

**Value Metrics**:
- >50% training campaigns launched (of paid users)
- >80% training completion (of enrolled users)
- Correlation between training completion and program maturity

**Customer Impact**: "We achieved 92% training completion in 4 weeks - automated reminders saved us hours"

#### Technical Scope

**Components**:
1. Training module library (5 pre-built modules)
2. Campaign management (create, schedule, assign)
3. User enrollment (auto-enroll by role)
4. Reminder system (email scheduler, escalations)
5. Completion tracking (individual progress, department rollup)
6. Reporting (completion reports, quiz results if applicable)
7. Dashboard integration (training completion %)

**Dependencies**:
- Email service (SendGrid/AWS SES)
- LMS integration (optional - SCORM support for future)
- HRIS integration (for user enrollment - optional)
- Dashboard (Epic 3) for metric integration

**Risks**:
- Email deliverability → Mitigation: Use reputable service (SendGrid), monitor bounce rates
- LMS integration complexity → Mitigation: Start with embedded training (in-app), defer LMS to Phase 3

#### User Stories (15 stories)

**Theme 1: Campaign Management**
- **US-5.1**: Browse Training Module Library (2 story points)
- **US-5.2**: Create Custom Campaign (3 story points)
- **US-5.3**: Assign Campaign by Role (3 story points)
- **US-5.4**: Schedule Campaign Launch (2 story points)
- **US-5.5**: Auto-Enroll Users (3 story points)
- **US-5.6**: Launch Campaign (2 story points)

**Theme 2: Reminder System**
- **US-5.7**: Send Automated Reminders (5 story points)
- **US-5.8**: Escalate to Manager (3 story points)
- **US-5.9**: Customize Reminder Schedule (3 story points)

**Theme 3: Completion Tracking**
- **US-5.10**: Track Individual Progress (3 story points)
- **US-5.11**: Record Completion Date (2 story points)
- **US-5.12**: Calculate Department Rollup (3 story points)
- **US-5.13**: Display on Dashboard (2 story points)

**Theme 4: Reporting**
- **US-5.14**: Generate Completion Reports (3 story points)
- **US-5.15**: Export Reports to CSV (2 story points)

**Subtotal**: 41 story points (rounded to 34)

#### Acceptance Criteria

**Epic-Level Acceptance Criteria**:
- [ ] 5 pre-built training modules available (Insider Threat Awareness, Data Handling, Policy Acknowledgment, Recognizing Risky Behaviors, Reporting Mechanisms)
- [ ] Can create and launch campaign in <5 minutes
- [ ] Users receive enrollment email within 1 hour
- [ ] Reminders send on schedule (tested: 50%, 80%, 1-day before, day-of)
- [ ] Completion tracked accurately (tested: 100 users complete, verify dashboard shows 100%)
- [ ] Dashboard training completion % updates in real-time
- [ ] Reports export correctly to CSV

#### Sprint Breakdown

**Sprint 9 (Weeks 17-18)**: Campaign Management & Enrollment
- Build training module library (5 modules)
- Build campaign creation UI
- Implement role-based assignment
- Implement auto-enrollment
- **Deliverable**: Can create and launch campaign

**Sprint 10 (Weeks 19-20)**: Reminder System & Tracking
- Build email reminder scheduler
- Implement escalation logic
- Build completion tracking
- Integrate with dashboard
- Build reporting
- **Deliverable**: Complete training module

---

### Epic 8: Demo Mode System

**Priority**: P1 (Should Have)
**Phase**: 2 (Demo Enhancement)
**Estimated Story Points**: 21
**Target Completion**: Sprint 8 (Week 16)

#### Business Value

**Problem**: Sales teams need flexibility to demo different program maturity stages (Month 0, 6, 12) but can't without synthetic data and dynamic feature visibility.

**Solution**: Demo mode system with:
- 5 modes (Show Me Journey, Month 0/6/12, Custom Timeline)
- Synthetic data generation for each month
- Feature visibility controller (show/hide based on maturity)
- Smooth transitions (<2 seconds)
- Reset functionality

**Value Metrics**:
- Sales team uses demo modes in >80% of demos
- >5 demo mode switches per sales demo (average)
- Demo-to-engagement conversion >40%

**Customer Impact**: (Internal) "Sales can now demo any maturity stage - closed 3 deals this week"

#### Technical Scope

**Components**:
1. Demo mode selector (UI dropdown or modal)
2. Synthetic data generator (for Month 0, 3, 6, 9, 12)
3. Feature visibility controller (show/hide modules based on month)
4. Transition animations
5. Reset functionality
6. "You are viewing Month X" indicator

**Dependencies**:
- All Phase 1 & 2 features (must exist to show/hide)
- Dashboard (Epic 3)
- Incident logging (Epic 2)

**Risks**:
- Synthetic data realism → Mitigation: Work with security SME, validate with sales team
- Feature visibility bugs → Mitigation: Extensive testing, feature flag system

#### User Stories (15 stories)

**Theme 1: Mode Selection**
- **US-8.1**: Select "Show Me the Journey" Mode (2 story points)
- **US-8.2**: Select "Month 0 View" (2 story points)
- **US-8.3**: Select "Month 6 View" (2 story points)
- **US-8.4**: Select "Month 12 View" (2 story points)
- **US-8.5**: Select "Custom Timeline" Mode (3 story points)

**Theme 2: Data Population**
- **US-8.6**: Generate Month 0 Data (2 story points)
- **US-8.7**: Generate Month 3 Data (2 story points)
- **US-8.8**: Generate Month 6 Data (3 story points)
- **US-8.9**: Generate Month 9 Data (3 story points)
- **US-8.10**: Generate Month 12 Data (3 story points)

**Theme 3: Feature Visibility & Transitions**
- **US-8.11**: Show/Hide Features Based on Month (5 story points)
- **US-8.12**: Smooth Mode Transitions (3 story points)
- **US-8.13**: Display "Viewing Month X" Indicator (2 story points)
- **US-8.14**: Reset to Month 0 (2 story points)
- **US-8.15**: Preserve User Config on Reset (3 story points)

**Subtotal**: 39 story points (rounded to 21 - includes reuse of existing features)

#### Acceptance Criteria

**Epic-Level Acceptance Criteria**:
- [ ] All 5 demo modes selectable
- [ ] Synthetic data populates realistically for each month (validated by sales team)
- [ ] Trends are statistically plausible (no obvious fake data)
- [ ] Features show/hide correctly based on month (tested: all combinations)
- [ ] Mode switch time <2 seconds
- [ ] Transitions smooth (no jarring UI changes)
- [ ] "You are viewing Month X" indicator always visible
- [ ] Reset to Month 0 works, preserves org profile

#### Sprint Breakdown

**Sprint 7 (Weeks 13-14)**: Mode Selection & Data Generation
- Build demo mode selector UI
- Implement synthetic data generator (Month 0, 3, 6, 9, 12)
- **Deliverable**: Can select mode, data populates

**Sprint 8 (Weeks 15-16)**: Feature Visibility & Transitions
- Implement feature visibility controller
- Build smooth transitions
- Add "Viewing Month X" indicator
- Implement reset functionality
- **Deliverable**: Complete demo mode system

---

## Phase 3: Full Capability (Weeks 25-40)

### Epic 6: DLP Integration

**Priority**: P1 (Should Have)
**Phase**: 3 (Full Capability)
**Estimated Story Points**: 34
**Target Completion**: Sprint 15 (Week 30)

#### Business Value

**Problem**: Month 4 is the critical DLP deployment milestone, but organizations struggle with vendor selection, configuration, and alert management.

**Solution**: DLP integration platform with:
- Auto-detect Microsoft 365 Purview availability (saves $15k-$25k if E5/A5)
- Setup wizard and configuration guidance
- Alert ingestion (Purview + major vendors)
- Incident auto-creation from high-severity alerts
- Alert correlation (DLP + HR flags)

**Value Metrics**:
- >80% DLP deployment on schedule (Month 4 target)
- >60% use Purview (detected as available)
- Alert ingestion latency <5 minutes
- False positive rate reduces by 20%+ after tuning guidance

**Customer Impact**: "We saved $22k by using Purview - platform detected we already had it"

#### Technical Scope

**Components**:
1. Microsoft Graph API integration (O365 license detection, Purview status)
2. Purview alert ingestion (Microsoft Graph Security API)
3. DLP configuration wizard (policy templates, alert thresholds)
4. Alert deduplication engine
5. Incident auto-creation (from high-severity alerts)
6. Alert correlation engine (DLP + HR flags)
7. Vendor API integrations (Symantec, Forcepoint, Digital Guardian, McAfee)

**Dependencies**:
- Microsoft Graph API access
- O365 tenant for testing
- Vendor API documentation and test accounts
- Incident logging (Epic 2)
- HR flag system (Epic 2)

**Risks**:
- **HIGH**: O365 API complexity and rate limits → Mitigation: Microsoft partnership, allocate 3-week buffer, implement robust error handling and retry logic
- Vendor API diversity → Mitigation: Build vendor-agnostic ingestion API, start with Purview (most common), add vendors incrementally

#### User Stories (15 stories)

**Theme 1: Purview Detection & Configuration**
- **US-6.1**: Detect O365 Tenant (2 story points)
- **US-6.2**: Query License Type (3 story points)
- **US-6.3**: Display Purview Availability (2 story points)
- **US-6.4**: Provide Setup Wizard (5 story points)
- **US-6.5**: Provide DLP Policy Templates (3 story points)
- **US-6.6**: Provide Tuning Guidance (3 story points)

**Theme 2: Alert Integration**
- **US-6.7**: Ingest Purview Alerts (5 story points)
- **US-6.8**: Auto-Create Incidents (3 story points)
- **US-6.9**: Deduplicate Alerts (3 story points)
- **US-6.10**: Display Alerts on Dashboard (3 story points)
- **US-6.11**: Correlate with HR Flags (5 story points)

**Theme 3: Vendor Support**
- **US-6.12**: Support Symantec DLP (3 story points)
- **US-6.13**: Support Forcepoint DLP (3 story points)
- **US-6.14**: Support Digital Guardian (3 story points)
- **US-6.15**: Support McAfee DLP (3 story points)

**Subtotal**: 49 story points (rounded to 34 - Phase 3 focus on Purview, vendor APIs added incrementally)

#### Acceptance Criteria

**Epic-Level Acceptance Criteria**:
- [ ] O365 license detected correctly (tested: E5, E3, Business, None)
- [ ] Purview availability displayed prominently
- [ ] Setup wizard completes in <10 minutes (tested with pilot user)
- [ ] Policy templates provided (6 templates)
- [ ] Alerts ingested within 5 minutes (tested: simulate 100 alerts)
- [ ] High-severity alerts auto-create incidents (tested: 20 alerts, verify 20 incidents)
- [ ] Deduplication works (tested: 10 duplicate alerts → 1 incident)
- [ ] Alert correlation (tested: termination + data download → high priority incident)

#### Sprint Breakdown

**Sprint 13 (Weeks 25-26)**: Purview Detection & Setup
- Build O365 tenant detection
- Build license type query
- Build setup wizard UI
- Create DLP policy templates
- **Deliverable**: Can detect Purview, show setup wizard

**Sprint 14 (Weeks 27-28)**: Alert Ingestion & Incident Creation
- Integrate Microsoft Graph Security API
- Build alert ingestion pipeline
- Build deduplication engine
- Implement incident auto-creation
- **Deliverable**: Alerts ingested, incidents created

**Sprint 15 (Weeks 29-30)**: Correlation & Vendor Support
- Build alert correlation engine (DLP + HR flags)
- Add dashboard integration (alert volume, false positive rate)
- Build vendor-agnostic API (foundation for Symantec, Forcepoint, etc.)
- **Deliverable**: Complete DLP integration (Purview)

---

### Epic 7: Oversight Features - Adapted

**Priority**: P1 (Should Have)
**Phase**: 3 (Full Capability)
**Estimated Story Points**: 34
**Target Completion**: Sprint 18 (Week 36)

#### Business Value

**Problem**: Organizations need governance and control frameworks but don't know which to adopt or how to track implementation.

**Solution**: 6 Oversight features adapted from Barclays PoC:
1. Framework Mapping (prepopulated insider threat frameworks)
2. Volume & Framework Baseline (target vs. actual modes)
3. Controls Mapping (prepopulated control library)
4. Threat Intelligence (industry benchmarks, scenarios)
5. Org Risk Viewer (potential risk areas)
6. Reporting (progress reports, not incident reports)

**Value Metrics**:
- >60% framework mapping usage
- >50% controls mapped to implementation status
- Reports generated 2x/month (average)

**Customer Impact**: "The CISA framework was pre-populated - saved us 2 weeks mapping controls"

#### Technical Scope

**Components**:
1. Framework library (CISA, NIST SP 800-53 subset, ITMG, industry-specific)
2. Framework mapping UI (control status tracking)
3. Controls library (technical, administrative, physical)
4. Threat intelligence content (benchmarks, scenarios)
5. Org risk assessment (visualize risk areas)
6. Report templates (4 reports for starting programs)

**Dependencies**:
- Content creation (security SME)
- Content management (Epic 9)
- Dashboard (Epic 3) for risk viewer integration

**Risks**:
- Content quality and accuracy → Mitigation: Security SME validation, cite sources
- Framework selection (too generic or too specific) → Mitigation: Focus on insider threat-specific, allow customization

#### User Stories (21 stories)

**Theme 1: Framework Mapping**
- **US-7.1**: View Prepopulated Frameworks (3 story points)
- **US-7.2**: Map Controls to Implementation Status (5 story points)
- **US-7.3**: Add Evidence to Controls (3 story points)
- **US-7.4**: Calculate Framework Coverage % (3 story points)
- **US-7.5**: Customize Framework (Add/Remove Controls) (3 story points)

**Theme 2: Volume & Framework Baseline**
- **US-7.6**: View Target Metrics (Industry Benchmarks) (3 story points)
- **US-7.7**: Transition to Actual Metrics (Month 4+) (3 story points)
- **US-7.8**: View Variance (Target vs. Actual) (2 story points)

**Theme 3: Controls Mapping**
- **US-7.9**: View Prepopulated Control Library (2 story points)
- **US-7.10**: Customize Controls (Add/Remove/Edit) (3 story points)
- **US-7.11**: Track Control Implementation Status (3 story points)
- **US-7.12**: Calculate Control Coverage % (2 story points)

**Theme 4: Threat Intelligence**
- **US-7.13**: View Industry Benchmarks (2 story points)
- **US-7.14**: View Threat Scenarios (3 story points)
- **US-7.15**: Filter by Industry (2 story points)

**Theme 5: Org Risk Viewer**
- **US-7.16**: View Potential Risk Areas (5 story points)
- **US-7.17**: Visualize Risk Heatmap (3 story points)
- **US-7.18**: Get Risk Mitigation Suggestions (3 story points)

**Theme 6: Reporting**
- **US-7.19**: Generate Program Progress Report (3 story points)
- **US-7.20**: Generate Maturity Assessment Report (3 story points)
- **US-7.21**: Export Reports to PDF/Excel (3 story points)

**Subtotal**: 61 story points (rounded to 34 - leverages content creation in parallel)

#### Acceptance Criteria

**Epic-Level Acceptance Criteria**:
- [ ] 6 frameworks prepopulated (CISA, NIST, ITMG, Financial, Healthcare, Technology)
- [ ] User can map all controls to status (tested: 50 controls)
- [ ] Framework coverage % calculates correctly
- [ ] Controls library comprehensive (50+ controls across technical, admin, physical)
- [ ] Threat intelligence accurate (validated by SME)
- [ ] Quarterly updates planned (content refresh)
- [ ] Org risk viewer visualizes 5 risk areas (departments, roles, remote workers, contractors, PIPs)
- [ ] 4 report templates generate correctly (Program Progress, Maturity Assessment, Quick Win Activity, Policy Coverage)
- [ ] Reports export to PDF/Excel

#### Sprint Breakdown

**Sprint 16 (Weeks 31-32)**: Framework & Controls Mapping
- Create framework library content (SME collaboration)
- Build framework mapping UI
- Create controls library content
- Build controls mapping UI
- **Deliverable**: Framework and controls mapping functional

**Sprint 17 (Weeks 33-34)**: Threat Intelligence & Risk Viewer
- Create threat intelligence content (benchmarks, scenarios)
- Build threat intelligence UI
- Build org risk viewer (risk area identification)
- Build risk heatmap visualization
- **Deliverable**: Threat intelligence and risk viewer functional

**Sprint 18 (Weeks 35-36)**: Reporting & Polish
- Create report templates (4 reports)
- Build report generation engine
- Implement export to PDF/Excel
- Polish UI/UX across Oversight features
- **Deliverable**: Complete Oversight features

---

### Epic 9: Content Management

**Priority**: P2 (Nice to Have)
**Phase**: 3 (Full Capability)
**Estimated Story Points**: 21
**Target Completion**: Sprint 18 (Week 36, concurrent with Epic 7)

#### Business Value

**Problem**: Demo platform needs industry-specific content (frameworks, scenarios, budgets) but swapping content manually is time-consuming and error-prone.

**Solution**: Content management system with:
- 5 industry content packs (Financial, Healthcare, Technology, Manufacturing, Government)
- Quick content swapping (<1 minute)
- Version control and audit log
- Framework and template management

**Value Metrics**:
- Sales team uses content swapping in >60% of demos
- <1 minute to swap industry content
- >90% accuracy (no missing content after swap)

**Customer Impact**: (Internal) "Demoed to healthcare client - swapped content in 30 seconds, won the deal"

#### Technical Scope

**Components**:
1. Industry content packs (5 packs, each includes: risk scenarios, frameworks, incident examples, budget estimates, policy templates)
2. Content swapping engine
3. Version control (track changes)
4. Admin interface (manage frameworks, controls, templates)
5. Import/export (CSV/Excel)

**Dependencies**:
- Content creation (security SME, industry research)
- Epic 7 (Oversight features use this content)
- Epic 1 (PPTX generator uses budget estimates)

**Risks**:
- Content creation time-intensive → Mitigation: Start with 2 packs (Financial, Healthcare), add 3 more incrementally
- Content accuracy → Mitigation: SME validation, cite sources

#### User Stories (15 stories)

**Theme 1: Industry Content Packs**
- **US-9.1**: View Available Content Packs (2 story points)
- **US-9.2**: Preview Content Pack (3 story points)
- **US-9.3**: Activate Content Pack (2 story points)
- **US-9.4**: Deactivate Content Pack (2 story points)
- **US-9.5**: Create New Content Pack (5 story points - Admin only)

**Theme 2: Content Swapping**
- **US-9.6**: Swap Content in <1 Minute (3 story points)
- **US-9.7**: Verify Content Updated (2 story points)
- **US-9.8**: Preserve User Data on Swap (3 story points)
- **US-9.9**: View Change Audit Log (3 story points)

**Theme 3: Framework & Template Management**
- **US-9.10**: Add/Edit Frameworks (3 story points - Admin only)
- **US-9.11**: Add/Edit Controls (3 story points - Admin only)
- **US-9.12**: Manage Policy Templates (3 story points - Admin only)
- **US-9.13**: Manage Report Templates (3 story points - Admin only)
- **US-9.14**: Import from CSV/Excel (5 story points - Admin only)
- **US-9.15**: Preview Before Using (2 story points)

**Subtotal**: 48 story points (rounded to 21 - content creation parallel work)

#### Acceptance Criteria

**Epic-Level Acceptance Criteria**:
- [ ] 5 industry packs pre-loaded (Financial, Healthcare, Technology, Manufacturing, Government)
- [ ] Each pack includes all required content (risk scenarios, frameworks, incident examples, budget estimates, policy templates)
- [ ] Content swap completes in <1 minute
- [ ] All areas update correctly after swap (Dashboard, PPTX, Oversight, Threat Intel)
- [ ] User data preserved (tasks, incidents, custom configs)
- [ ] Change audit log captures all swaps (who, what, when)
- [ ] Admin can add/edit frameworks, controls, templates
- [ ] Import from CSV/Excel works (tested with 50-row file)

#### Sprint Breakdown

**Sprint 16 (Weeks 31-32)**: Content Packs & Swapping
- Create 5 industry content packs (SME collaboration)
- Build content pack management UI
- Build content swapping engine
- Implement change audit log
- **Deliverable**: Can swap content packs

**Sprint 18 (Weeks 35-36)**: Admin Management (concurrent with Epic 7 polish)
- Build admin interface (manage frameworks, controls, templates)
- Implement import from CSV/Excel
- Add preview functionality
- **Deliverable**: Complete content management

---

### Epic 10: Incident Management

**Priority**: P2 (Nice to Have)
**Phase**: 3 (Full Capability)
**Estimated Story Points**: 21
**Target Completion**: Sprint 20 (Week 40)

#### Business Value

**Problem**: Once DLP deploys and incidents start logging, organizations need proper investigation workflows to track and resolve incidents efficiently.

**Solution**: Complete incident management system with:
- Manual and automated incident creation
- Investigation workflow (New → In Progress → Resolved → Closed)
- Evidence attachment and timeline view
- MTTD/MTTR calculation
- Incident reporting and analytics

**Value Metrics**:
- >90% incidents logged (from all sources)
- MTTD and MTTR improve 20%+ over 6 months
- >80% incidents closed within SLA (defined per org)

**Customer Impact**: "MTTR dropped from 15 days to 8 days using the investigation workflow"

#### Technical Scope

**Components**:
1. Incident creation (manual form, auto-creation from DLP/HR/Quick Wins)
2. Investigation workflow (status transitions, assignments)
3. Note/comment system
4. Evidence attachment (file upload)
5. Timeline view (incident activities)
6. Severity assignment (Low, Medium, High, Critical)
7. MTTD/MTTR calculation
8. Incident list (filterable, sortable)
9. Incident detail view
10. Incident reporting (summary reports, trends)

**Dependencies**:
- Epic 2 (Basic incident logging - extended here)
- Epic 6 (DLP alerts auto-create incidents)
- Epic 3 (Dashboard shows incident metrics)

**Risks**:
- Workflow complexity → Mitigation: Start simple (4 states), enhance based on feedback
- Evidence storage costs → Mitigation: Retention policy (30-90 days), S3 lifecycle

#### User Stories (15 stories)

**Theme 1: Incident Logging**
- **US-10.1**: Create Incident Manually (3 story points)
- **US-10.2**: Auto-Create from DLP Alert (2 story points - built in Epic 6)
- **US-10.3**: Auto-Create from HR Flag (2 story points - built in Epic 2)
- **US-10.4**: Auto-Create from Quick Win Channel (2 story points - built in Epic 2)
- **US-10.5**: Assign Unique Incident ID (1 story point)
- **US-10.6**: Assign to Investigator (2 story points)

**Theme 2: Investigation Workflow**
- **US-10.7**: Transition Status (New → In Progress → Resolved → Closed) (3 story points)
- **US-10.8**: Add Notes/Comments (2 story points)
- **US-10.9**: Attach Evidence (3 story points)
- **US-10.10**: View Timeline of Activities (3 story points)
- **US-10.11**: Track Time Spent (for MTTR) (3 story points)

**Theme 3: Incident Reporting**
- **US-10.12**: View Incident List (Filterable, Sortable) (3 story points)
- **US-10.13**: View Incident Detail (2 story points)
- **US-10.14**: Export Incident List to CSV (2 story points)
- **US-10.15**: Generate Incident Summary Report (3 story points)

**Subtotal**: 36 story points (rounded to 21 - leverages Epic 2 foundation)

#### Acceptance Criteria

**Epic-Level Acceptance Criteria**:
- [ ] Incidents created from all sources (manual, DLP, HR, Quick Wins)
- [ ] Investigation workflow works (tested: 20 incidents through all states)
- [ ] Notes and evidence attach correctly
- [ ] Timeline view shows all activities (creation, status changes, notes, evidence)
- [ ] MTTD and MTTR calculate correctly (tested with known data)
- [ ] Incident list filters and sorts (tested: by date, severity, status, source)
- [ ] Export to CSV includes all fields
- [ ] Incident summary report generates (tested: Month 6 data)

#### Sprint Breakdown

**Sprint 19 (Weeks 37-38)**: Investigation Workflow
- Build investigation workflow (status transitions)
- Build note/comment system
- Build evidence attachment
- Build timeline view
- Implement time tracking (for MTTR)
- **Deliverable**: Complete investigation workflow

**Sprint 20 (Weeks 39-40)**: Reporting & Final Polish
- Build incident list (filterable, sortable)
- Build incident detail view
- Implement export to CSV
- Build incident summary report
- Final UI/UX polish across entire platform
- Performance optimization
- **Deliverable**: Production-ready platform

---

## Implementation Strategy

### Sprint Planning Guidelines

**Sprint Cadence**: 2 weeks per sprint (20 sprints total)

**Team Velocity**:
- Expected: 20-25 story points per sprint (team of 5 FTEs)
- Total story points: 309
- Total sprints: 15-16 (allows 4-5 sprints buffer for unknowns)

**Sprint Structure**:
- Sprint Planning: Monday (Week 1)
- Daily Standups: 15 minutes daily
- Sprint Review: Friday (Week 2)
- Sprint Retrospective: Friday (Week 2)

### Epic Dependencies

```
Phase 1 (MVP):
  Epic 1 (Onboarding) ─┬─> Epic 2 (Quick Wins) ─┬─> Epic 3 (Dashboard)
                       │                         │
                       └─────────────────────────┘

Phase 2 (Demo Enhancement):
  Epic 1+2+3 ──> Epic 4 (Rollout Planner)
              ├─> Epic 5 (Training)
              └─> Epic 8 (Demo Modes)

Phase 3 (Full Capability):
  Epic 2 ──> Epic 6 (DLP) ──> Epic 10 (Incidents)
  Epic 1 ──┬─> Epic 7 (Oversight)
  Epic 4 ──┘    ├─> Epic 9 (Content Mgmt)
                └─> Epic 10 (Incidents)
```

### Risk Management by Epic

| Epic # | Risk Level | Mitigation Strategy |
|--------|------------|---------------------|
| 1 | Medium | Extensive testing (10+ scenarios), designer collaboration |
| 2 | **HIGH** | GPT-4 API (best model), SME validation, iterate based on feedback |
| 3 | Medium | Clear formula, caching, WebSockets/polling |
| 4 | Low | Proven libraries, start simple |
| 5 | Medium | Reputable email service, monitor deliverability |
| 6 | **HIGH** | Microsoft partnership, 3-week buffer, robust error handling |
| 7 | Low | SME validation, cite sources |
| 8 | Medium | SME for synthetic data, sales validation |
| 9 | Low | Parallel content creation, SME validation |
| 10 | Low | Start simple workflow, enhance based on feedback |

---

## Success Metrics by Epic

### Epic 1: User Onboarding & Discovery
- Priority Picker completion rate: >90%
- PPTX download rate: >80%
- Program approval rate: >70% (within 30 days)

### Epic 2: Quick Wins - Pre-DLP Value
- AI Gap Analysis usage: >70%
- AI analysis accuracy: >85% (SME validated)
- Quick Win channels used: >60%

### Epic 3: Dashboard & Metrics
- Daily active users: >30%
- Session duration: >15 minutes
- Dashboard used 3x/week by decision makers

### Epic 4: Five-Phase Rollout Planner
- Rollout planner task completion: >70%
- Weekly planner usage: >60%

### Epic 5: Training & Awareness Module
- Training campaigns launched: >50%
- Training completion: >80%

### Epic 6: DLP Integration
- DLP on schedule (Month 4): >80%
- Purview adoption: >60%
- Alert ingestion latency: <5 minutes

### Epic 7: Oversight Features
- Framework mapping usage: >60%
- Controls mapped: >50%

### Epic 8: Demo Mode System
- Demo mode usage (sales): >80% of demos
- Mode switches per demo: >5

### Epic 9: Content Management
- Content swapping (sales): >60% of demos
- Swap time: <1 minute

### Epic 10: Incident Management
- Incidents logged: >90%
- MTTD/MTTR improvement: >20% over 6 months

---

## Appendices

### A. Story Point Estimation Guide

- **1 point**: Trivial (1-2 hours, clear requirements, no unknowns)
- **2 points**: Simple (3-4 hours, clear requirements, minor complexity)
- **3 points**: Moderate (1 day, understood requirements, some complexity)
- **5 points**: Complex (2-3 days, some unknowns, significant complexity)
- **8 points**: Very Complex (4-5 days, many unknowns, high complexity)
- **13 points**: Epic-sized (1-2 weeks, break down further)

### B. Epic Template

```markdown
## Epic X: [Name]

**Priority**: P0/P1/P2
**Phase**: 1/2/3
**Story Points**: XX
**Target Completion**: Sprint X (Week X)

### Business Value
- Problem
- Solution
- Value Metrics
- Customer Impact

### Technical Scope
- Components
- Dependencies
- Risks

### User Stories (X stories)
- Theme 1: [...]
- Theme 2: [...]

### Acceptance Criteria
- [ ] Criterion 1
- [ ] Criterion 2

### Sprint Breakdown
- Sprint X: [...]
```

### C. References

- PRD: `docs/prd.md`
- Feature Requirements: `FEATURE-REQUIREMENTS.md`
- Implementation Roadmap: `IMPLEMENTATION-ROADMAP.md`

---

**Document Version**: 1.0
**Last Updated**: 2025-10-31
**Status**: ✅ Ready for Sprint Planning


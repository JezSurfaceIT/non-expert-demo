# Feature Requirements: Non-Expert Insider Threat Demo Platform

**Document Version**: 1.0
**Date**: 2025-10-31
**Status**: Requirements Complete

---

## Table of Contents

1. [Priority Picker](#1-priority-picker)
2. [Program Approval PPTX Generator](#2-program-approval-pptx-generator)
3. [Five-Phase Rollout Planner](#3-five-phase-rollout-planner)
4. [Quick Win Features](#4-quick-win-features)
5. [Dashboard & Metrics](#5-dashboard--metrics)
6. [Training & Awareness Module](#6-training--awareness-module)
7. [Adapted Oversight Features](#7-adapted-oversight-features)
8. [DLP Integration](#8-dlp-integration)
9. [Demo Mode System](#9-demo-mode-system)
10. [Content Management](#10-content-management)

---

## 1. Priority Picker

### Feature Overview
Interactive decision tree that triages users to optimal starting point and collects critical organizational data for customization.

### User Stories
- **As a CISO**, I want to quickly determine where to start so I don't waste time on wrong priorities
- **As a Risk Officer**, I want budget estimates so I can prepare approval materials
- **As an IT Manager**, I want to know if I already have DLP capability so I don't overspend

### Functional Requirements

#### FR-PP-001: Question Flow
- **MUST** present 10 discovery questions in logical order
- **MUST** support Yes/No, Multiple Choice, and Range inputs
- **MUST** allow back navigation to revise answers
- **SHOULD** show progress indicator (question X of 10)

#### FR-PP-002: Discovery Questions

| # | Question | Type | Options/Range |
|---|----------|------|---------------|
| 1 | Executive buy-in status | Multiple | Yes / Partial / No |
| 2 | Budget allocated | Boolean | Yes / No |
| 3 | Existing policies | Multiple | Yes / Partial / No |
| 4 | Recent incident or near-miss | Boolean | Yes / No |
| 5 | Regulatory/audit pressure | Boolean | Yes / No |
| 6 | Microsoft 365 license type | Multiple | E5/A5 / E3/A3 / Business / None |
| 7 | MSSP usage | Boolean | Yes / No |
| 8 | Tool budget range | Range | <$50k / $50k-$150k / >$150k |
| 9 | Technical team size | Range | 0-2 / 3-5 / 6+ |
| 10 | Industry | Multiple | Financial / Healthcare / Technology / Manufacturing / Government / Other |

#### FR-PP-003: Decision Logic

**Starting Path Recommendations**:
```
IF buy-in = No AND budget = No:
  → RECOMMEND: "Start with Policy Development" + Generate executive PPTX

IF buy-in = Partial OR budget = Partial:
  → RECOMMEND: "Start with Risk Assessment" + Show ROI calculator

IF buy-in = Yes AND budget = Yes:
  → RECOMMEND: "Start with Quick Win Detection" + Deploy human channels
```

**Sophistication Tier Assignment**:
```
BASIC (Tier 1):
  - Team size 0-2 AND Budget <$50k AND NO MSSP

INTERMEDIATE (Tier 2):
  - Team size 3-5 OR Budget $50k-$150k OR Basic MSSP

ADVANCED (Tier 3):
  - Team size 6+ AND Budget >$150k AND Advanced MSSP
```

**DLP Recommendation Logic**:
```
IF M365_license = E5 OR A5:
  → "You already have Purview DLP included (FREE)"

IF M365_license = E3 OR A3:
  → "Purview available as add-on (~$5-10/user/month)"

IF M365_license = Business OR None:
  → "Consider third-party DLP vendor (budget estimate: $X)"
```

**UEBA Readiness**:
```
IF tier = ADVANCED AND team_size >= 6 AND budget > $150k:
  → "UEBA recommended - discuss in Month 4"
ELSE IF tier = INTERMEDIATE AND MSSP = Yes:
  → "UEBA optional - MSSP can provide"
ELSE:
  → "UEBA not recommended at this stage"
```

#### FR-PP-004: Outputs
- **MUST** display recommended starting path with rationale
- **MUST** assign sophistication tier (displayed to user)
- **MUST** provide DLP recommendation with cost implications
- **MUST** assess UEBA readiness
- **MUST** trigger PPTX generation with collected data
- **SHOULD** save responses for later reference

### Non-Functional Requirements

#### NFR-PP-001: Performance
- Question page load: <500ms
- Decision calculation: <1 second
- PPTX generation trigger: Immediate (async)

#### NFR-PP-002: Usability
- Mobile-responsive design
- Keyboard navigation support
- Clear, jargon-free language
- Help tooltips on technical questions

#### NFR-PP-003: Data Privacy
- **MUST NOT** transmit data without consent
- **MUST** allow data export/deletion
- **SHOULD** work offline (local storage)

### Acceptance Criteria
- [ ] All 10 questions render correctly
- [ ] Logic produces expected recommendations for 10 test scenarios
- [ ] PPTX generation triggered with correct data
- [ ] User can navigate back and change answers
- [ ] Results display clearly with action items

---

## 2. Program Approval PPTX Generator

### Feature Overview
Automated generation of customized PowerPoint presentation for program approval, populated with user's Priority Picker data and industry-relevant content.

### User Stories
- **As a CISO**, I want a board-ready presentation so I don't spend 2 weeks creating one
- **As a Risk Officer**, I want industry-specific stats so my business case is credible
- **As an IT Manager**, I want budget estimates so I can justify costs

### Functional Requirements

#### FR-PPTX-001: Template Structure
**MUST** include 8 sections with following content:

**Slide 1: Executive Summary**
- Title: "Insider Threat Program Proposal"
- Subtitle: [Industry] Organization
- What is insider threat? (3 bullets)
- Why now? (trigger from Priority Picker)
- What's at risk? (data, IP, reputation)

**Slide 2: Business Case**
- Industry statistics (cost of insider incidents)
- Regulatory/compliance drivers (if applicable from Q5)
- Risk to organization (customized by industry)
- "Cost of inaction" scenarios

**Slide 3: Proposed Program Structure**
- 5-phase visual diagram (Foundation → Governance)
- 12-month timeline graphic
- Milestone-based approach explanation

**Slide 4: Budget Requirements** ⭐
- Year 1 costs table:
  - Personnel (FTE or % allocation) - estimated by org size
  - Tools (DLP choice from Q6, UEBA if Tier 3)
  - Training/awareness materials
  - Consulting/external support
- **Pre-populated estimates** based on answers
- **Purview option highlighted** if E5/A5 detected

**Slide 5: Quick Wins & Value Demonstration**
- Month 1-3 deliverables (no budget needed):
  - AI Policy Gap Analysis
  - Human reporting channels (3)
  - Policy coverage baseline
- Month 4+ with tooling:
  - DLP deployment
  - Incident detection capability
- Month 12 expected outcomes:
  - Mature program metrics

**Slide 6: Resource Requirements**
- Team structure diagram
- Time commitments (% allocations)
- Cross-functional dependencies:
  - HR (flag triggers, policy enforcement)
  - IT (tool deployment, monitoring)
  - Legal (policy review, compliance)

**Slide 7: Success Metrics**
- Program maturity score (visual gauge)
- Coverage metrics (policy %, training %)
- Incident detection capability (timeline)
- Risk reduction targets (industry benchmarks)

**Slide 8: Next Steps & Decision Points**
- Approval needed by [date + 30 days]
- Procurement timeline for Month 4 DLP
- Stakeholder engagement plan
- **Call to action**: "Approve Phase 0 budget and authority to proceed"

#### FR-PPTX-002: Customization Logic

**Budget Estimation Formula** (Slide 4):
```
Personnel Cost:
  IF team_size = 0-2: 25% FTE allocation = $[market_rate * 0.25]
  IF team_size = 3-5: 50% FTE allocation = $[market_rate * 0.50]
  IF team_size = 6+: 1.0 FTE allocation = $[market_rate * 1.0]

Tool Cost:
  IF M365 = E5/A5: $0 (Purview included)
  IF M365 = E3/A3: $[users * 7.5/month * 12]
  IF M365 = Other: $[15-25k base + $5/user]
  IF UEBA_recommended: Add $[50-150k depending on tier]

Training Cost:
  Base: $5k (materials, platform)
  Per-user: $25 * employee_count

Total Year 1: [Sum above with 20% contingency]
```

**Industry-Specific Content**:
- **Financial Services**: Emphasize regulatory pressure (FINRA, SEC), IP theft, trading secrets
- **Healthcare**: HIPAA compliance, patient data, research IP
- **Technology**: Source code theft, trade secrets, competitive intelligence
- **Manufacturing**: Design IP, customer lists, process knowledge
- **Government**: Classified data, national security, public trust

#### FR-PPTX-003: Export Functionality
- **MUST** generate in Microsoft PowerPoint format (.pptx)
- **MUST** be editable by user after export
- **SHOULD** include speaker notes with guidance
- **SHOULD** embed brand-neutral design (user can rebrand)
- **MUST** complete generation in <5 seconds

### Non-Functional Requirements

#### NFR-PPTX-001: Quality
- Professional design template
- Consistent branding throughout
- No placeholder text (all customized)
- Charts/diagrams render correctly

#### NFR-PPTX-002: Accuracy
- Budget estimates within ±20% of market rates
- Industry statistics from credible sources (cited)
- Timeline realistic for org context

### Acceptance Criteria
- [ ] PPTX generates with all 8 slides
- [ ] Budget estimates match test scenarios
- [ ] Industry content correctly selected
- [ ] Purview cost shown as $0 when E5/A5
- [ ] File opens in PowerPoint without errors
- [ ] All customization fields populated (no placeholders)

---

## 3. Five-Phase Rollout Planner

### Feature Overview
Interactive roadmap guiding organizations through 5 phases of program maturity over 12 months, with phase-specific tasks, milestones, and success criteria.

### User Stories
- **As a CISO**, I want a clear roadmap so I know what to do each month
- **As a Risk Officer**, I want milestone tracking so I can report progress
- **As an IT Manager**, I want task checklists so I don't miss critical steps

### Functional Requirements

#### FR-RP-001: Phase Definitions

**Phase 0: Foundation (Month 0)**
- **Goal**: Secure approval and authority to proceed
- **Maturity**: 0% → 15%
- **Tasks**:
  1. Complete Priority Picker
  2. Generate program approval PPTX
  3. Present to executive stakeholders
  4. Obtain budget approval
  5. Make DLP vendor decision (Purview vs. third-party)
  6. Deploy AI Policy Gap Analysis tool
- **Milestone**: "Program Launch" - policies drafted, stakeholders identified, budget allocated
- **Duration**: 2-4 weeks

**Phase 1: Scoping (Months 0-2)**
- **Goal**: Establish foundation with quick wins
- **Maturity**: 15% → 25%
- **Tasks**:
  1. DLP vendor selection (if third-party needed)
  2. Deploy policy violation self-reporting portal
  3. Deploy manager concern submission form
  4. Deploy automated HR flag triggers
  5. Run AI policy analysis
  6. Begin policy development based on gaps
  7. Plan training campaigns
- **Milestone**: "Quick Wins Live" - human reporting channels operational, policy gaps identified
- **Duration**: 6-8 weeks

**Phase 2: Prevention/Awareness (Months 2-4)**
- **Goal**: Build awareness and prepare for detection
- **Maturity**: 25% → 40%
- **Tasks**:
  1. Launch training campaigns
  2. Distribute and track policy acknowledgments
  3. DLP procurement (contracting, purchase)
  4. DLP configuration planning
  5. Log first concerns via quick win channels
  6. Establish incident response procedures
- **Milestone**: "Training Complete" - 80%+ staff trained, DLP ready to deploy
- **Duration**: 8-10 weeks

**Phase 3: Detection (Months 4-7)**
- **Goal**: Deploy monitoring and begin incident logging
- **Maturity**: 40% → 70%
- **Tasks**:
  1. **Month 4: DLP Deployment** ⭐
  2. Tune DLP alerts (reduce false positives)
  3. Log incidents from DLP and human channels
  4. Establish MTTD/MTTR baselines
  5. UEBA decision point (if Tier 2/3)
  6. Begin pattern analysis
  7. Refine detection rules
- **Milestone**: "Detection Live" - monitoring tools operational, first incidents resolved
- **Duration**: 12-14 weeks

**Phase 4: Governance (Months 8-12)**
- **Goal**: Mature program with full capabilities
- **Maturity**: 70% → 85%
- **Tasks**:
  1. Analyze trends from 6+ months data
  2. Implement all 10 KPIs
  3. Deploy UEBA (if selected)
  4. Create board-level reports
  5. Demonstrate ROI
  6. Optimize processes based on data
  7. Plan Year 2 enhancements
- **Milestone**: "Mature Program" - ready for audit, measurable value, sustainable operations
- **Duration**: 16-20 weeks

#### FR-RP-002: Task Management
- **MUST** display current phase prominently
- **MUST** show task checklist for current phase
- **MUST** allow marking tasks complete
- **MUST** calculate phase completion percentage
- **MUST** warn if falling behind schedule
- **SHOULD** suggest next actions based on context

#### FR-RP-003: Timeline Visualization
- **MUST** display 12-month Gantt-style timeline
- **MUST** show phase boundaries clearly
- **MUST** highlight current position
- **SHOULD** show key milestones as markers
- **SHOULD** allow zooming in/out

#### FR-RP-004: Customization
- **MUST** adjust timeline based on org size (faster/slower)
- **SHOULD** allow user to set target completion date
- **SHOULD** suggest acceleration options (e.g., skip UEBA)

### Non-Functional Requirements

#### NFR-RP-001: Usability
- Printable summary view
- Export to PDF or spreadsheet
- Mobile-friendly task tracking

#### NFR-RP-002: Persistence
- Save progress across sessions
- Track historical completion dates
- Allow rollback if needed

### Acceptance Criteria
- [ ] All 5 phases display with correct tasks
- [ ] Task completion updates progress percentage
- [ ] Timeline visualization renders correctly
- [ ] Milestones trigger congratulations/next phase
- [ ] Can export plan to PDF

---

## 4. Quick Win Features

### Feature Overview
Four immediately deployable capabilities that provide value before DLP deployment, focusing on human reporting and AI analysis.

---

### 4.1 Policy Violation Self-Reporting Portal

#### User Stories
- **As an employee**, I want to safely report concerns so I'm not a whistleblower
- **As a security officer**, I want employees to tell me about issues so I can intervene early

#### Functional Requirements

**FR-QW-001: Submission Form**
- **MUST** provide web form accessible to all employees
- **MUST** support anonymous submissions
- **MUST** support authenticated submissions (with identity)
- **MUST** capture:
  - Type of concern (dropdown: data handling, policy violation, suspicious behavior, other)
  - Description (free text, min 50 chars)
  - Date/time observed (optional)
  - Affected person/dept (optional)
  - Supporting evidence (file upload, optional)
- **SHOULD** provide example scenarios to guide users

**FR-QW-002: Submission Handling**
- **MUST** generate unique ticket ID
- **MUST** send confirmation to submitter (if not anonymous)
- **MUST** notify security team
- **MUST** integrate with incident logging system
- **SHOULD** provide status tracking for submitter

#### Acceptance Criteria
- [ ] Anonymous submissions work without login
- [ ] Authenticated users can track submission status
- [ ] Tickets appear in incident log
- [ ] Email notifications sent correctly

---

### 4.2 Manager Concern Submission Form

#### User Stories
- **As a manager**, I want to flag risky employee behaviors so security can assess
- **As a security officer**, I want managers to report early warning signs so I can prevent incidents

#### Functional Requirements

**FR-QW-003: Manager Form**
- **MUST** require manager authentication
- **MUST** capture:
  - Employee name/ID (required)
  - Concern type (dropdown: performance issues, policy violations, behavioral changes, access concerns, resignation risk)
  - Description (free text, min 100 chars)
  - Duration observed (how long has this been happening?)
  - Actions taken so far (optional)
  - Urgency level (low/medium/high)
- **MUST** include disclaimer about employee privacy
- **SHOULD** suggest HR consultation for performance issues

**FR-QW-004: Routing & Escalation**
- **MUST** route high urgency to security immediately
- **MUST** route medium urgency within 24 hours
- **MUST** create case in incident system
- **SHOULD** notify HR for performance-related concerns
- **SHOULD** suggest manager training if needed

#### Acceptance Criteria
- [ ] Only managers can access form
- [ ] High urgency triggers immediate alert
- [ ] HR notified for performance issues
- [ ] Case created with correct priority

---

### 4.3 Automated HR Flag Triggers

#### User Stories
- **As an HR manager**, I want security notified of terminations automatically so we reduce risk
- **As a security officer**, I want to know about PIPs/terminations so I can monitor closely

#### Functional Requirements

**FR-QW-005: HRIS Integration**
- **MUST** integrate with HRIS API or receive webhooks
- **MUST** trigger alerts on:
  - Terminations (voluntary or involuntary)
  - Performance Improvement Plans (PIPs)
  - Disciplinary actions
  - Resignation notices
  - Role changes (especially privilege reductions)
- **SHOULD** capture relevant context (reason codes, dates, supervisor)

**FR-QW-006: Alert Generation**
- **MUST** create incident ticket automatically
- **MUST** assign appropriate severity:
  - Involuntary termination: High
  - Voluntary resignation: Medium
  - PIP: Medium
  - Role change: Low
- **MUST** suggest actions (e.g., "Review access logs for past 30 days")
- **SHOULD** integrate with DLP (when available) to increase monitoring

**FR-QW-007: Privacy & Compliance**
- **MUST** restrict access to HR-flagged cases (need-to-know)
- **MUST** log all access to HR data
- **MUST** comply with employment law (no retaliatory actions)

#### Acceptance Criteria
- [ ] HRIS events trigger alerts within 5 minutes
- [ ] Correct severity assigned based on event type
- [ ] Access restricted to authorized personnel
- [ ] All access logged for audit

---

### 4.4 AI Policy Gap Analysis Tool ⭐

#### User Stories
- **As a CISO**, I want to know if my policies cover insider threats so I can fix gaps quickly
- **As a Risk Officer**, I want AI to analyze policies so I don't spend weeks reading them
- **As an IT Manager**, I want policy templates so I can implement fixes fast

#### Functional Requirements

**FR-QW-008: Document Upload**
- **MUST** accept PDF, Word (.docx), text files
- **MUST** support batch upload (up to 10 files)
- **MUST** extract text from PDFs (OCR if needed)
- **SHOULD** accept policy URLs (scrape web pages)

**FR-QW-009: AI Analysis**
**MUST** analyze policies for insider threat coverage:
- **Data Handling**:
  - Data classification schemes
  - Acceptable use of data
  - Data exfiltration prevention
  - Personal device policies (BYOD)
- **Access Controls**:
  - Least privilege enforcement
  - Access review procedures
  - Termination procedures (access revocation)
  - Third-party/contractor access
- **Monitoring & Detection**:
  - Monitoring disclosure (employee awareness)
  - Acceptable monitoring scope
  - Detection capabilities claimed
  - Incident response procedures
- **Behavioral & Cultural**:
  - Reporting mechanisms (whistleblower protection)
  - Consequences for violations
  - Training requirements
  - Remote work policies

**FR-QW-010: Gap Report Generation**
**MUST** produce report with:
1. **Executive Summary** (1 paragraph)
2. **Coverage Heatmap** (visual):
   - Green: Well covered
   - Yellow: Partially covered
   - Red: Not covered
3. **Detailed Findings** by category:
   - What's covered well (with quotes from policies)
   - What's missing (specific gaps)
   - What's ambiguous (unclear language)
   - Insider threat scenarios not addressed
4. **Prioritized Recommendations**:
   - Critical gaps (must fix)
   - Important gaps (should fix)
   - Nice-to-have improvements
5. **Policy Templates** for identified gaps (downloadable)

**FR-QW-011: Performance**
- **MUST** complete analysis in <60 seconds for up to 100 pages
- **SHOULD** show progress indicator during processing
- **SHOULD** allow cancellation

**FR-QW-012: Output Formats**
- **MUST** display report in web interface
- **MUST** export to PDF
- **SHOULD** export to Word (editable)
- **SHOULD** provide policy templates as separate downloads

#### Non-Functional Requirements

**NFR-QW-001: AI Quality**
- Analysis accuracy: >85% (validated against expert reviews)
- False positive rate: <10%
- Relevant recommendations: >90%

**NFR-QW-002: Security**
- Uploaded files encrypted at rest and in transit
- Files deleted after processing (unless user saves)
- No training on customer data without consent

#### Acceptance Criteria
- [ ] Accepts PDF, Word, text files
- [ ] Analysis completes in <60 seconds
- [ ] Report includes all 5 sections
- [ ] Coverage heatmap visually clear
- [ ] Recommendations are actionable
- [ ] Policy templates provided for gaps
- [ ] Export to PDF works correctly
- [ ] Demo shows impressive results in 30-60 seconds

---

## 5. Dashboard & Metrics

### Feature Overview
Adaptive dashboard that evolves from zero-incident metrics (maturity, coverage, targets) to full incident-based KPIs as program matures.

### User Stories
- **As a CISO**, I want to see program maturity so I can report progress to board
- **As a Risk Officer**, I want to see risk reduction so I can justify budget
- **As an IT Manager**, I want to see quick win activity so I know channels are working

### Functional Requirements

#### FR-DASH-001: Zero-Incident Phase Dashboard (Months 0-4)

**MUST** display:

1. **Program Maturity Score** (0-100%)
   - Calculated from phase completion
   - Visual gauge with color coding (Red <25%, Yellow 25-70%, Green >70%)
   - Breakdown by phase

2. **Policy Coverage Percentage**
   - % of critical insider threat areas covered by policies
   - Derived from AI gap analysis
   - Target: 100%, Current: X%

3. **Training Completion Rates**
   - Overall completion %
   - By department/role
   - Target: 80%+, Current: X%

4. **Compliance Checklist Progress**
   - X of Y compliance items complete
   - Regulatory requirements checked off
   - Industry framework alignment

5. **Risk Reduction Targets**
   - NOT actuals (no incidents yet)
   - Industry benchmarks
   - "Potential threats prevented" estimate

6. **Quick Win Channel Activity**
   - # of self-reports
   - # of manager concerns
   - # of HR flags
   - Trend over time

7. **DLP Deployment Readiness**
   - Procurement status
   - Configuration progress
   - Go-live countdown

#### FR-DASH-002: Early Detection Phase Dashboard (Months 4-7)

**MUST** add:

1. **Incident Count** (3-5 total in this phase)
   - Current month vs. previous
   - Cumulative total

2. **Incident Source Breakdown** ⭐
   - Pie chart or bar chart showing:
     - % from DLP alerts
     - % from employee reports
     - % from manager escalations
     - % from HR referrals
     - % from IT security alerts
   - Demonstrates DLP ROI

3. **Early MTTD/MTTR**
   - Mean Time To Detect (days)
   - Mean Time To Respond (days)
   - Trend improving over time

4. **Alert Volume Trends**
   - DLP alerts per day/week
   - False positive rate
   - Tuning progress

#### FR-DASH-003: Mature Phase Dashboard (Months 8-12)

**MUST** add all 10 KPIs from Barclays PoC:

1. MTTD (Mean Time To Detect)
2. MTTR (Mean Time To Respond)
3. Training Completion %
4. False Positive Rate
5. Risk Reduction %
6. Detection Rate
7. NDR (Named Data References)
8. Program Cost
9. Role Risk Score
10. Overall Security Posture

**MUST** add:
- Incident trends over time (line charts)
- Behavioral analytics (if UEBA deployed)
- Predictive insights
- ROI demonstration

#### FR-DASH-004: Filtering & Drill-Down
- **MUST** support date range selection
- **MUST** support filtering by department, role, severity
- **SHOULD** support exporting dashboard to PDF/image
- **SHOULD** support creating custom views

### Non-Functional Requirements

#### NFR-DASH-001: Performance
- Dashboard load time: <2 seconds
- Metric calculations: <500ms
- Chart rendering: <1 second

#### NFR-DASH-002: Accessibility
- WCAG 2.1 Level AA compliant
- Keyboard navigation
- Screen reader compatible
- Color-blind friendly palettes

### Acceptance Criteria
- [ ] Zero-incident dashboard shows 7 metrics
- [ ] Metrics update in real-time as data changes
- [ ] Phase transition adds appropriate metrics
- [ ] Incident source breakdown visualizes correctly
- [ ] Export to PDF preserves formatting
- [ ] Dashboard responsive on mobile

---

## 6. Training & Awareness Module

### Feature Overview
End-to-end training campaign management from selection to completion tracking, integrated with dashboard metrics.

### User Stories
- **As a CISO**, I want automated training campaigns so I don't manage them manually
- **As an HR manager**, I want completion tracking so I know who hasn't trained
- **As an employee**, I want reminders so I don't miss deadlines

### Functional Requirements

#### FR-TRAIN-001: Campaign Selection Interface
- **MUST** provide library of pre-built training modules:
  - Insider Threat Awareness (foundational, 20 min)
  - Data Handling Best Practices (15 min)
  - Policy Acknowledgment (10 min)
  - Recognizing Risky Behaviors (15 min)
  - Reporting Mechanisms (10 min)
- **MUST** allow creating custom campaigns
- **MUST** support role-based assignment (all staff, managers only, IT only, etc.)
- **SHOULD** suggest campaigns based on phase (e.g., foundational in Phase 2)

#### FR-TRAIN-002: Automated Execution
- **MUST** support scheduling (start date, deadline)
- **MUST** auto-enroll users based on role
- **MUST** send launch announcement email
- **MUST** integrate with LMS or provide embedded training
- **SHOULD** support recurring campaigns (annual refresher)

#### FR-TRAIN-003: Reminder System
- **MUST** send reminders at:
  - 50% of time elapsed
  - 80% of time elapsed
  - 1 day before deadline
  - Day of deadline
- **MUST** escalate to manager if user overdue by 3+ days
- **MUST** allow custom reminder schedules
- **SHOULD** support SMS reminders (optional)

#### FR-TRAIN-004: Completion Tracking
- **MUST** track individual progress (not started, in progress, completed)
- **MUST** record completion date and time
- **MUST** track quiz/assessment results (if applicable)
- **MUST** calculate department rollup (% complete per dept)
- **MUST** display on executive dashboard
- **MUST** integrate with HRIS (if available)

#### FR-TRAIN-005: Reporting
- **MUST** generate completion reports:
  - Overall % complete
  - Completion by department
  - Completion by role
  - Overdue list
  - Quiz performance summary
- **MUST** export to CSV/Excel
- **SHOULD** visualize trends over time

### Non-Functional Requirements

#### NFR-TRAIN-001: Scalability
- Support 10,000+ users per campaign
- Email queue handles 1,000+ messages/hour

#### NFR-TRAIN-002: Integration
- SCORM-compliant for LMS integration
- HRIS API integration for enrollment

### Acceptance Criteria
- [ ] Can create and launch campaign in <5 minutes
- [ ] Users receive enrollment email within 1 hour
- [ ] Reminders sent on schedule
- [ ] Completion tracked accurately
- [ ] Dashboard shows real-time completion %
- [ ] Reports export correctly

---

## 7. Adapted Oversight Features

### Feature Overview
Six features from Barclays PoC Oversight module, adapted for organizations with no incident history.

---

### 7.1 Framework Mapping

#### Functional Requirements

**FR-OVER-001: Framework Selection**
- **MUST** pre-populate with insider threat-specific frameworks (NOT generic NIST/ISO)
- **MUST** support:
  - CISA Insider Threat Mitigation Framework
  - NIST SP 800-53 (Insider Threat controls subset)
  - Insider Threat Working Group (ITMG) Best Practices
  - Industry-specific frameworks (FINRA for financial, HIPAA for healthcare)
- **MUST** allow user to add/remove framework elements
- **MUST** support industry swapping (financial, healthcare, tech, manufacturing, government)

**FR-OVER-002: Control Mapping**
- **MUST** map each control to implementation status:
  - Not Started (gray)
  - In Progress (yellow)
  - Implemented (green)
  - Not Applicable (strikethrough)
- **MUST** allow adding evidence (document links, notes)
- **MUST** calculate overall coverage % per framework

#### Acceptance Criteria
- [ ] Pre-populated frameworks load correctly
- [ ] Industry swap changes relevant controls
- [ ] User can add custom controls
- [ ] Coverage % calculates correctly

---

### 7.2 Volume & Framework Baseline

#### Functional Requirements

**FR-OVER-003: Baseline Mode**
- **MUST** operate in "Target Mode" (not "Actual Mode") for zero-incident orgs
- **MUST** display target metrics:
  - Target detection rate: X% (industry benchmark)
  - Target MTTD: Y days (industry benchmark)
  - Target training completion: 80%
- **MUST** transition to "Actual Mode" when incidents exist (Month 4+)

#### Acceptance Criteria
- [ ] Displays targets before Month 4
- [ ] Displays actuals after Month 4
- [ ] Industry benchmarks accurate

---

### 7.3 Controls Mapping

#### Functional Requirements

**FR-OVER-004: Control Library**
- **MUST** pre-populate with insider threat controls:
  - Technical controls (DLP, UEBA, access monitoring)
  - Administrative controls (policies, training, background checks)
  - Physical controls (badge access, visitor logs)
- **MUST** allow user customization (add/remove/edit)
- **MUST** support client-swappable content for demos

**FR-OVER-005: Implementation Tracking**
- **MUST** track control implementation status
- **MUST** link controls to rollout planner phases
- **MUST** calculate control coverage %

#### Acceptance Criteria
- [ ] Pre-populated controls comprehensive
- [ ] Swapping content easy (<1 minute)
- [ ] Control coverage calculates correctly

---

### 7.4 Threat Intelligence

#### Functional Requirements

**FR-OVER-006: Threat Landscape**
- **MUST** provide industry benchmarks:
  - Average # of insider incidents per org size
  - Most common threat types by industry
  - Average cost per incident
- **MUST** provide "What could happen" scenarios:
  - Data exfiltration scenarios
  - IP theft scenarios
  - Sabotage scenarios
- **SHOULD** update quarterly with latest research

#### Acceptance Criteria
- [ ] Industry benchmarks display correctly
- [ ] Scenarios relevant to user's industry
- [ ] Content updated quarterly

---

### 7.5 Org Risk Viewer

#### Functional Requirements

**FR-OVER-007: Risk Assessment Mode**
- **MUST** operate in assessment mode (no actual incidents)
- **MUST** visualize potential risk areas:
  - Departments with access to sensitive data
  - Roles with elevated privileges
  - Remote/hybrid workers
  - Contractors/third-parties
  - Employees on PIP or with performance issues
- **MUST** suggest risk mitigation priorities

#### Acceptance Criteria
- [ ] Risk areas visualized clearly
- [ ] Suggestions actionable
- [ ] Transitions to incident mode at Month 4+

---

### 7.6 Reporting

#### Functional Requirements

**FR-OVER-008: Report Templates**
- **MUST** provide reports for starting programs:
  - Program Progress Report (for management)
  - Maturity Assessment Report (for board)
  - Quick Win Activity Report (for operations)
  - Policy Coverage Report (for compliance)
- **MUST NOT** include incident reports (until incidents exist)
- **MUST** transition to incident reports at Month 4+

#### Acceptance Criteria
- [ ] All 4 reports generate correctly
- [ ] Reports format professionally
- [ ] Export to PDF/Excel works

---

## 8. DLP Integration

### Feature Overview
Integration with Microsoft 365 Purview and third-party DLP vendors for Month 4 deployment.

### User Stories
- **As an IT Manager**, I want Purview detected automatically so I know it's available
- **As a CISO**, I want DLP alerts in the platform so I have single pane of glass
- **As a Security Analyst**, I want DLP configuration guidance so I set it up correctly

### Functional Requirements

#### FR-DLP-001: Purview Detection
- **MUST** detect if user has O365 tenant
- **MUST** query O365 license type (E5/A5/E3/A3)
- **MUST** display Purview availability prominently
- **MUST** provide activation instructions if not enabled
- **SHOULD** link to Microsoft Purview portal

#### FR-DLP-002: Configuration Guidance
- **MUST** provide DLP policy templates for insider threat:
  - Sensitive data exfiltration (PII, financial, IP)
  - Excessive downloads/uploads
  - Sharing to personal accounts
  - External device usage
  - Printing sensitive documents
- **MUST** suggest alert thresholds based on org size
- **MUST** provide tuning guidance (reduce false positives)

#### FR-DLP-003: Alert Integration
- **MUST** ingest DLP alerts via API or webhook
- **MUST** create incidents automatically for high-severity alerts
- **MUST** deduplicate similar alerts
- **MUST** display DLP alerts in dashboard
- **SHOULD** correlate DLP alerts with HR flags (e.g., termination + data download)

#### FR-DLP-004: Vendor Support
- **MUST** support Microsoft Purview (priority)
- **SHOULD** support major vendors:
  - Symantec DLP
  - Forcepoint DLP
  - Digital Guardian
  - McAfee DLP

### Non-Functional Requirements

#### NFR-DLP-001: Performance
- Alert ingestion latency: <5 minutes
- API polling interval: 1 minute

#### NFR-DLP-002: Reliability
- Alert ingestion uptime: 99.9%
- Automatic retry on API failures

### Acceptance Criteria
- [ ] O365 license detected correctly
- [ ] Purview availability displayed
- [ ] Policy templates provided
- [ ] Alerts ingested within 5 minutes
- [ ] Incidents auto-created for high-severity

---

## 9. Demo Mode System

### Feature Overview
Flexible demo system allowing presenters to jump to any maturity stage and show appropriate features/data for that stage.

### User Stories
- **As a Sales Engineer**, I want to jump to Month 6 view so I can show mid-maturity state
- **As a Product Manager**, I want to reset to Month 0 so I can demo onboarding again
- **As a Presenter**, I want to show custom timeline so I can match client's pace

### Functional Requirements

#### FR-DEMO-001: Mode Selection
- **MUST** provide mode selector with 5 options:
  1. "Show Me the Journey" - Interactive step-through (guided)
  2. "Month 0 View" - Pure startup, empty states
  3. "Month 6 View" - Mid-maturity, some data
  4. "Month 12 View" - Mature program, full capabilities
  5. "Custom Timeline" - User inputs target month (0-12)

#### FR-DEMO-002: Data Population
- **MUST** generate appropriate synthetic data for selected month:
  - Month 0: Empty states, targets only
  - Month 3: Training in progress, policies drafted, no incidents
  - Month 6: 5-10 incidents, early trends, DLP deployed
  - Month 9: 15-25 incidents, clear trends, patterns emerging
  - Month 12: 30+ incidents, full KPIs, mature analytics

#### FR-DEMO-003: Feature Visibility
- **MUST** show/hide features based on month:
  - Months 0-3: Priority Picker, Rollout Planner, Quick Wins, Training
  - Month 4+: Add Incidents module, DLP dashboard
  - Month 8+: Add full KPIs, trends, behavioral analytics

#### FR-DEMO-004: Smooth Transitions
- **MUST** animate transitions between modes (not jarring)
- **MUST** preserve user context when switching modes
- **SHOULD** show "You are viewing Month X" indicator clearly

#### FR-DEMO-005: Reset Functionality
- **MUST** allow reset to Month 0
- **MUST** clear synthetic data
- **MUST** preserve configuration (industry, org size, etc.)

### Non-Functional Requirements

#### NFR-DEMO-001: Performance
- Mode switch time: <2 seconds
- Data generation: <3 seconds

#### NFR-DEMO-002: Realism
- Synthetic data must look realistic (not obviously fake)
- Trends must be statistically plausible

### Acceptance Criteria
- [ ] All 5 modes selectable
- [ ] Data populates correctly for each month
- [ ] Features appear/hide based on maturity
- [ ] Transitions smooth and clear
- [ ] Reset to Month 0 works
- [ ] "You are viewing Month X" indicator always visible

---

## 10. Content Management

### Feature Overview
Backend system for managing industry-specific content, frameworks, and templates that can be quickly swapped for demos or client customization.

### User Stories
- **As a Sales Engineer**, I want to swap to healthcare content so the demo is relevant
- **As a Product Manager**, I want to update frameworks so they stay current
- **As an Admin**, I want to add new industries so we can target new markets

### Functional Requirements

#### FR-CM-001: Industry Content Packs
- **MUST** provide pre-built content for 5 industries:
  1. Financial Services
  2. Healthcare
  3. Technology
  4. Manufacturing
  5. Government

**Each pack includes**:
- Industry-specific risk scenarios
- Relevant regulatory frameworks
- Typical incident examples
- Budget estimates (market rates)
- Policy templates

#### FR-CM-002: Content Swapping
- **MUST** allow swapping industry pack in <1 minute
- **MUST** update all relevant areas:
  - Dashboard scenarios
  - Framework mapping
  - Threat intelligence
  - PPTX generation
  - Reports
- **MUST** preserve user data (don't overwrite)

#### FR-CM-003: Framework Management
- **MUST** allow adding/editing frameworks
- **MUST** allow adding/editing controls
- **MUST** version control (track changes)
- **SHOULD** import from CSV/Excel

#### FR-CM-004: Template Management
- **MUST** manage policy templates (AI gap analysis output)
- **MUST** manage report templates
- **MUST** manage PPTX templates
- **SHOULD** allow preview before using

### Non-Functional Requirements

#### NFR-CM-001: Security
- Content versioning with rollback
- Change audit log (who changed what when)
- Role-based access (not all users can edit)

#### NFR-CM-002: Scalability
- Support 20+ industry packs
- Support 50+ frameworks
- Support 100+ policy templates

### Acceptance Criteria
- [ ] 5 industry packs pre-loaded
- [ ] Content swap completes in <1 minute
- [ ] All areas update correctly after swap
- [ ] Framework editing works
- [ ] Template management functional
- [ ] Change audit log captures edits

---

## Cross-Cutting Requirements

### Export Capabilities
All major features **MUST** support export:
- PPTX: Program approval presentation
- PDF: Reports, dashboards, gap analysis
- CSV/Excel: Training completion, incident logs, metrics
- Image: Dashboard snapshots

### Integration Points
- **HRIS**: HR flag triggers, employee data
- **O365**: Purview detection, license info, DLP alerts
- **LMS**: Training enrollment, completion tracking
- **MSSP**: Future - alert forwarding, joint workflows

### Security & Privacy
- All data encrypted at rest (AES-256)
- All data encrypted in transit (TLS 1.3)
- Role-based access control (RBAC)
- Audit logging for sensitive actions
- Data retention policies
- GDPR/CCPA compliance

### Performance Standards
- Page load time: <2 seconds
- API response time: <500ms
- Dashboard render: <2 seconds
- Report generation: <5 seconds
- PPTX generation: <5 seconds
- AI policy analysis: <60 seconds

### Accessibility
- WCAG 2.1 Level AA compliant
- Keyboard navigation throughout
- Screen reader compatible
- Color-blind friendly palettes
- Mobile responsive design

---

## Appendices

### A. Feature Priority Matrix

| Priority | Feature | Reason |
|----------|---------|--------|
| P0 (MVP) | Priority Picker | Core triage functionality |
| P0 (MVP) | PPTX Generator | Critical for program approval |
| P0 (MVP) | AI Policy Gap Analysis | Signature feature, immediate value |
| P0 (MVP) | Quick Wins (3 human channels) | Pre-DLP value |
| P0 (MVP) | Dashboard (zero-incident) | Show progress without incidents |
| P1 (v1.1) | Rollout Planner | Guidance for implementation |
| P1 (v1.1) | Training Module | Phase 2 requirement |
| P1 (v1.1) | Demo Mode System | Sales enablement |
| P2 (v1.2) | DLP Integration | Month 4 requirement |
| P2 (v1.2) | Oversight Features (adapted) | Mature program features |
| P2 (v1.2) | Content Management | Scalability and customization |
| P3 (v2.0) | UEBA Integration | Advanced tier only |
| P3 (v2.0) | MSSP Integration | Deferred to future |

### B. Feature Dependencies

```
Priority Picker → PPTX Generator (requires picker data)
Priority Picker → Rollout Planner (requires tier assignment)
AI Policy Gap Analysis → Dashboard (provides policy coverage %)
Quick Wins → Dashboard (provides channel activity)
Training Module → Dashboard (provides completion %)
Demo Mode System → All features (controls visibility)
Content Management → PPTX Generator, Oversight Features (provides industry data)
```

### C. Success Metrics

**Feature Adoption**:
- Priority Picker completion rate: >90%
- PPTX download rate: >80% (of picker completions)
- AI Gap Analysis usage: >70%
- Quick Win channel submissions: >5/month average

**Platform Effectiveness**:
- Time to program approval: <30 days (from demo)
- DLP deployment on time: >80% (Month 4 target met)
- Training completion: >80%
- Dashboard usage: >3x/week by decision makers

---

**Document Version**: 1.0
**Total Features**: 10 major features, 50+ discrete requirements
**Last Updated**: 2025-10-31
**Next Review**: After implementation planning


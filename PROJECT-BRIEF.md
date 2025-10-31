# Project Brief: Non-Expert Insider Threat Demo Platform

**Project Name**: Non-Expert Insider Threat Demo Platform
**Target Audience**: Organizations starting insider threat programs from zero
**Platform Type**: Demo + Educational + Sales Tool Hybrid
**Date**: 2025-10-31
**Status**: Requirements Complete - Ready for Implementation Planning

---

## Executive Summary

This platform addresses a critical market gap: organizations that recognize the need for insider threat programs but have no existing incidents, no dedicated security teams, and no historical data to demonstrate value. Unlike existing solutions designed for mature programs with hundreds of incidents, this platform guides organizations from zero to operational capability.

**Core Problem Solved**: Organizations can't justify insider threat programs without data, but can't generate meaningful data without programs. This chicken-and-egg problem requires a fundamentally different approach focused on program establishment rather than threat management.

**Key Differentiator**: Educational journey platform that demonstrates value through program maturity, policy coverage, and risk reduction targets rather than incident metrics.

---

## Business Context

### Who Initiates This Journey?
- **Primary Stakeholders**: CISO, Chief Risk Officer, Board Members
- **Organizational Profile**:
  - Small to medium teams with limited resources
  - No dedicated insider threat staff
  - Limited security budgets (<$150k/year for tools)
  - No incident history to reference

### What Triggers the Decision?
1. Near-miss incident that wasn't caught
2. Audit finding or compliance gap
3. Board/executive mandate
4. Competitive pressure (peers have programs)
5. **New awareness** of insider threat risk (education-driven)

### Day 1 Questions (All Must Be Addressed)
- "Where do I even start?"
- "What should I be monitoring?"
- "How do I get buy-in/budget?"
- "What policies do I need?"
- "Am I even allowed to monitor employees?"

---

## Platform Vision

### Core Purpose
Help organizations **START** insider threat programs by:
1. **Scoping** - Understand where to begin based on context
2. **Prevention/Awareness** - Build foundation before detection
3. **Detection** - Deploy monitoring capabilities progressively
4. **Governance** - Establish sustainable, mature programs

### Value Proposition Evolution

**Months 0-4 (Zero Incidents)**:
- Program maturity scoring
- Policy coverage metrics
- Training completion tracking
- Risk reduction targets (not actuals)
- Quick win channel activity
- Tool deployment readiness

**Months 4-7 (Early Detection)**:
- First incidents from DLP (3-5 total)
- Source breakdown visualization
- Early MTTD/MTTR metrics
- Pattern recognition begins

**Months 8-12 (Mature Operation)**:
- Full KPI dashboard (10 metrics)
- Trend analysis capability
- Predictive insights
- Board-ready reporting
- ROI demonstration

---

## Target User Personas

### Persona 1: "The New CISO"
**Profile**: Recently appointed, inheriting security program with gaps
**Pain Points**: No insider threat capability, board asking questions
**Needs**: Quick justification, realistic timeline, budget estimates
**Success Metric**: Board approval within 30 days

### Persona 2: "The Risk Officer"
**Profile**: Compliance-focused, identifies insider risk gap
**Pain Points**: No technical background, needs business case
**Needs**: Industry benchmarks, regulatory mapping, ROI projections
**Success Metric**: Executive buy-in and budget allocation

### Persona 3: "The IT Manager"
**Profile**: Wearing security hat, no dedicated team
**Pain Points**: Limited time and resources, DIY approach
**Needs**: Practical quick wins, built-in tools (Purview), simple deployment
**Success Metric**: Something operational in 90 days

---

## Core Features Overview

### 1. Priority Picker (Day 1 Decision Tree)
**Purpose**: Triage users to optimal starting point based on their context

**10 Discovery Questions**:
1. Executive buy-in status
2. Budget allocation
3. Existing policies
4. Recent incidents
5. Regulatory pressure
6. Microsoft 365 license type
7. MSSP usage
8. Tool budget range
9. Technical team size
10. Industry

**Outputs**:
- Recommended starting path
- Sophistication tier (Basic/Intermediate/Advanced)
- DLP recommendation (Purview vs. vendor)
- UEBA readiness assessment
- **Custom PPTX for program approval**

### 2. Program Approval Presentation (PPTX Export)
**Purpose**: Board-ready business case generated from Priority Picker data

**8 Sections**:
1. Executive Summary - What/Why/Risk
2. Business Case - Industry stats, compliance drivers, org risk
3. Proposed Program Structure - 5 phases, 12-month roadmap
4. Budget Requirements - Personnel, tools, training, consulting (customized)
5. Quick Wins & Value Demo - Month 1-3 deliverables
6. Resource Requirements - Team, time, dependencies
7. Success Metrics - Maturity, coverage, detection capability
8. Next Steps - Approval timeline, procurement schedule

**Customization**: Pre-populated with user's specific context, Purview availability, budget ranges, industry scenarios

### 3. Five-Phase Rollout Planner

**Phase 0: Foundation (Month 0)**
- Priority Picker completion
- Program approval PPTX generation
- Budget approval & authority
- DLP vendor decision
- Quick Win: AI Policy Gap Analysis

**Phase 1: Scoping (Months 0-2)**
- DLP vendor selection (if needed)
- Deploy human reporting channels
- AI policy analysis & gap remediation
- Training campaign planning

**Phase 2: Prevention/Awareness (Months 2-4)**
- Training campaigns active
- Policy distribution
- Awareness metrics tracking
- DLP procurement & configuration

**Phase 3: Detection (Months 4-7)**
- **Month 4: DLP Deployment** (key milestone)
- Incident logging begins
- First MTTD/MTTR metrics
- UEBA decision point

**Phase 4: Governance (Months 8-12)**
- Mature detection capability
- Full KPI tracking
- Board reporting
- Process optimization
- Optional UEBA deployment

### 4. Quick Wins (Months 1-3, Pre-DLP)

**Human Reporting Channels**:
1. **Policy Violation Self-Reporting Portal**
   - Safe, anonymous option for employees
   - Integration with incident logging

2. **Manager Concern Submission Form**
   - Structured intake for behavioral concerns
   - Priority routing and tracking

3. **Automated HR Flag Triggers**
   - Terminations → automatic alerts
   - PIPs (Performance Improvement Plans) → flags
   - Disciplinary actions → tracked
   - HRIS integration

**AI-Powered Tool** ⭐ SIGNATURE FEATURE:
4. **AI Policy Gap Analysis**
   - Upload existing policies (PDF, Word)
   - AI analyzes from insider threat perspective
   - Generates prioritized gap report
   - Provides policy templates
   - 30-60 second processing
   - Immediate demo value

### 5. Timeline & Demo Modes

**Approach**: Option D + A (Flexible with 12-month default)

**Demo Modes**:
1. "Show Me the Journey" - Interactive step-through
2. "Month 0 View" - Pure startup, empty states
3. "Month 6 View" - Mid-maturity, some data
4. "Month 12 View" - Mature program, full capabilities
5. "Custom Timeline" - User-defined pace

**12-Month Default Timeline**:

| Phase | Months | Maturity | Key Milestones |
|-------|--------|----------|----------------|
| Foundation | 0-1 | 0% → 15% | Approval, Quick Wins, AI Analysis |
| Scoping | 1-2 | 15% → 25% | Vendor selection, Human reporting |
| Prevention | 2-4 | 25% → 40% | Training, DLP procurement |
| Detection | 4-7 | 40% → 70% | **DLP live**, First incidents, MTTD/MTTR |
| Governance | 8-12 | 70% → 85% | Trends, Full KPIs, Board reporting |

---

## Technical Architecture Highlights

### Dashboard Evolution

**Zero-Incident Phase (Months 0-4)**:
- Program maturity score
- Policy coverage percentage
- Training completion rates
- Compliance checklist progress
- Risk reduction targets
- Quick win channel activity
- DLP deployment readiness

**Early Detection Phase (Months 4-7)**:
- First incidents (3-5 total)
- Incident source breakdown:
  - % from DLP alerts
  - % from employee reports
  - % from manager escalations
  - % from HR referrals
  - % from IT security alerts
- Early MTTD/MTTR
- Alert volume trends

**Mature Phase (Months 8-12)**:
- All 10 KPIs from Barclays PoC
- Incident trends over time
- Behavioral analytics (if UEBA)
- Predictive insights
- ROI demonstration

### DLP Deployment Strategy

**Month 4 Deployment (Key Milestone)**

**Option 1: Microsoft 365 Purview** (E5/A5 license - FREE)
**Option 2: Purview Add-on** (E3/A3 - ~$5-10/user/month)
**Option 3: Third-Party Vendor** (no O365 or preference)

**Procurement Timeline**:
- Month 0: Budget approval, vendor decision
- Month 0-1: RFP process (if third-party)
- Month 1-3: Contracting, purchase, delivery
- Month 3-4: Configuration, policy setup, testing
- Month 4: Go live

**Critical Insight**: Month 4 deployment requires Month 0 budgeting and vendor selection. The Priority Picker identifies Purview availability to potentially eliminate procurement delays and costs.

### UEBA Strategy (Optional/Advanced)

**Sophistication Tiers**:
- **Tier 1 (Basic)**: Skip UEBA, DLP only
- **Tier 2 (Intermediate)**: Consider if MSSP available
- **Tier 3 (Advanced)**: Full UEBA recommendation

**Decision Criteria**:
- MSSP sophistication level
- Technical team size (6+ people)
- Budget >$150k/year
- Organizational maturity

**Deployment**: Month 8+ (if selected at Month 4 decision point)

### Training & Awareness Module

**Campaign Management**:
1. Campaign selection interface (pre-built modules)
2. Automated execution (schedule, auto-enroll)
3. Reminder system (nudges, manager escalation)
4. Completion tracking (individual + department rollup)
5. Reporting integration (dashboard metric)

---

## Adapted Features from Barclays PoC

### From Oversight Module (Modified):
1. **Framework Mapping** - PREPOPULATED with insider threat-specific frameworks (not generic NIST/ISO), industry-swappable
2. **Volume & Framework Baseline** - Adapted for zero-incident orgs, shows targets not actuals
3. **Controls Mapping** - PREPOPULATED, customizable, client-swappable
4. **Threat Intelligence** - Industry benchmarks, threat landscape education
5. **Org Risk Viewer** - Risk assessment mode (no incidents yet)
6. **Reporting** - New reports for starting programs (progress, not incidents)

### From Foresight Module (Simplified):
- "Easy-Start" mode (details TBD in future)
- Defer behavioral analytics until detection phase

### From Incidents Module (Evolutionary):
- Hidden in Months 0-4
- Appears at Month 4 (DLP deployment)
- Grows as incidents accumulate
- Full KPI capability at Month 8+

---

## Key Technical Requirements

### Content Management
1. **Industry Content Swapping**
   - Easy mechanism to swap frameworks, controls, risk scenarios
   - Pre-canned examples: Financial, Healthcare, Technology, Manufacturing, Government
   - Quick customization for client demos

### Demo Flexibility
2. **Timeline Progression**
   - Jump to any maturity stage
   - "Fast-forward" through months
   - Reset to Month 0 for new demo

3. **Modular Visibility**
   - Features appear/hide based on maturity
   - Smooth phase transitions
   - No jarring empty experiences

### Export Capabilities
4. **PPTX Generation** - Customized program approval presentations
5. **Report Exports** - Progress reports, gap analysis, training completion

### Integration Points
6. **HRIS Integration** - HR flag triggers
7. **O365 Integration** - Purview detection, license discovery
8. **MSSP Integration** - Future (deferred)

---

## Success Metrics

### Platform Success (Demo Effectiveness)
- Time from demo to client engagement decision
- PPTX export usage rate
- Demo mode utilization patterns
- AI Policy Gap Analysis completion rate

### Client Success (Program Maturity)
- Program approval rate (within 30 days)
- DLP deployment on schedule (Month 4)
- Training completion rates (>80%)
- First incident detection (Month 5-7)
- Board presentation readiness (Month 12)

---

## Competitive Differentiation

### What Competitors Offer
- Mature program management (100s-1000s of incidents)
- Historical trend analysis
- Advanced behavioral analytics
- Assumes existing team and budget

### What We Offer
- **Program establishment** (zero to operational)
- **Educational journey** (learn while building)
- **Business case generation** (PPTX export)
- **Immediate value** (AI policy analysis, quick wins)
- **Realistic timeline** (12 months to maturity)
- **Budget-conscious** (Purview option, tiered approach)

---

## Risks & Mitigation

### Risk 1: Over-Simplification
**Concern**: Platform too basic for sophisticated buyers
**Mitigation**: Sophistication tiering (Basic/Intermediate/Advanced) with UEBA path

### Risk 2: AI Policy Analysis Quality
**Concern**: AI generates poor recommendations
**Mitigation**: Human review templates, industry validation, iterative refinement

### Risk 3: Demo vs. Product Confusion
**Concern**: Clients expect production-ready tool immediately
**Mitigation**: Clear positioning as educational demo + implementation guidance

### Risk 4: DLP Integration Complexity
**Concern**: Purview/vendor integrations difficult
**Mitigation**: Start with Purview (simpler), document integration patterns

---

## Implementation Priorities

### Phase 1 (MVP) - 8-12 weeks
1. Priority Picker decision tree (10 questions)
2. Basic PPTX export (template-based)
3. AI Policy Gap Analysis tool
4. 3 Human reporting channels (self-report, manager, HR flags)
5. Dashboard with maturity score + quick win metrics

**Success Criteria**: Can demo complete Month 0-2 journey

### Phase 2 (Demo Enhancement) - 8-12 weeks
1. Demo mode switcher (Month 0/6/12 views)
2. Industry content swapping mechanism
3. Incident source breakdown visualization
4. Training campaign management
5. Adapted Oversight features

**Success Criteria**: Can demo full 12-month journey with flexibility

### Phase 3 (Full Capability) - 12-16 weeks
1. DLP integration (Purview + vendor options)
2. Full timeline progression with data evolution
3. All Barclays PoC features adapted
4. Foresight Easy-Start mode
5. MSSP integration

**Success Criteria**: Production-ready platform for client deployment

---

## Open Questions for Future Sessions

1. **Foresight "Easy-Start" Mode** - How to simplify behavioral analytics?
2. **MSSP Integration Details** - What specific workflows needed?
3. **Advanced UEBA Features** - What capabilities for Tier 3 orgs?
4. **Industry Framework Details** - Which insider threat frameworks to prepopulate?
5. **Training Content** - Specific modules, learning paths, assessments?
6. **Policy Templates** - What templates for AI gap analysis output?
7. **Budget Estimates** - Specific cost ranges for PPTX generation?

---

## Appendices

### A. Source Documentation
- Session notes: `session-notes-2025-10-31-153500-analyst-co-elicitation.md` (1,191 lines)
- Barclays PoC analysis: `/home/jez/code/Barclays-PoC-on-Vercel/` (4 analysis documents)

### B. Decision Log
- Timeline approach: Option D + A selected (flexible with 12-month default)
- DLP timing: Month 4 confirmed as key milestone
- Quick wins: 4 features confirmed (3 human channels + AI tool)
- MSSP integration: Deferred to future discussion
- Sophistication tiers: 3 levels (Basic/Intermediate/Advanced)

### C. Requirements Summary
- **Total Features Identified**: 50+ discrete capabilities
- **Core Deliverables**: 12 major features/modules
- **Integration Points**: 3 (HRIS, O365, MSSP-future)
- **Export Formats**: 2 (PPTX, Reports)
- **Demo Modes**: 5 (Journey, M0, M6, M12, Custom)

---

**Document Version**: 1.0
**Last Updated**: 2025-10-31
**Next Review**: After implementation planning session


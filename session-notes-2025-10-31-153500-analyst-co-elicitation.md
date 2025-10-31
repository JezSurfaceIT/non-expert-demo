# Co-Elicitation Session: Non-Professional Insider Threat Org Restructure
## Session Metadata
- **Date**: 2025-10-31
- **Time Started**: 15:35:00
- **Analyst**: Mary (Business Analyst Agent)
- **Participant**: Jez
- **Purpose**: Design insider threat platform for organizations starting their programs
- **Source Material**: Barclays-PoC-on-Vercel demo
- **Target Directory**: /home/jez/code/non-Insider-Treat-orgs

---

## Session Format Decisions
1. **Format**: Freeform conversation
2. **Documentation**: Real-time notes + summary compilation
3. **Focus Areas**:
   - Building insider threat programs from scratch
   - Justifying/establishing such programs
   - Prevention/awareness emphasis → detection/governance progression
4. **Target Audience**:
   - Small teams with limited resources
   - Organizations without dedicated security teams
5. **Deliverables**:
   - Session transcript with insights
   - Project brief document
   - Feature requirements list

---

## Key Context: Original vs. Target

### Barclays PoC (Original)
- **Designed for**: Mature organizations with established insider threat programs
- **Assumes**: 100s-1000s of existing incidents, 12+ months KPI trends, behavioral baselines
- **Features**: 10 KPI tracking, ML/behavioral analytics, real-time threat intelligence
- **Problem**: Not suitable for organizations with zero incidents/no existing team

### Target Audience (New Platform)
- **Reality**: No incidents because no insider threat team exists yet
- **Need**: Tools to START a program, not manage an existing one
- **Journey**: Scoping → Prevention/Awareness → Detection → Governance
- **Constraint**: Non-professional (small teams, limited resources, no dedicated security staff)

---

## Verbatim Notes & Insights

### User Statement 1
> "they won't have any insider incidents because they dont have an insider team to measure and monitor them. therefore there will not be any KPIs, emerging trends, etc. we need to work out where the value-prop is."

**Insight**: Core problem is chicken-and-egg - can't have metrics without incidents, can't detect incidents without a team/program. Value proposition must shift from "manage threats" to "establish capability to manage threats."

---

## Co-Elicitation Questions & Discussion

### Q1: Who initiates this journey?
**Answer**: CISO, Chief Risk Officer, The Board

**Insight**: Multi-level stakeholder engagement from start. Not just operational security concern - it's enterprise risk management and governance issue. App needs to speak to multiple audiences with different concerns.

### Q2: What triggers the decision to start?
**Answer**:
- Near-miss incident that wasn't caught
- Audit finding or compliance gap
- Board/executive mandate
- Competitive pressure (peers have programs)
- **NEW**: Becoming aware of the risk when previously they were not

**Insight**: Risk awareness is a trigger itself. Some orgs don't know they need this until someone educates them. Platform might need to help BUILD awareness, not just assume it exists.

### Q3: When they first open this app on Day 1, what is their most urgent question?
**Answer**: ALL OF THESE:
- "Where do I even start?"
- "What should I be monitoring?"
- "How do I get buy-in/budget?"
- "What policies do I need?"
- "Am I even allowed to monitor employees?"

**REQUIREMENT IDENTIFIED**: Need a **priority picker** - help users determine which of these urgent questions to tackle first based on their specific context.

### Q4: What does "success" look like in Month 1 vs Month 6 vs Month 12?
**Answer**: TBD as we go along

**REQUIREMENT IDENTIFIED**: Need to define a **template rollout planner** - guide organizations through staged implementation with clear milestones.

---

## Emerging Requirements Summary

### Core Features Identified So Far:
1. **Priority Picker** - Interactive tool to help orgs identify their most urgent needs
2. **Template Rollout Planner** - Staged implementation guide with milestones

### Next Discussion Topics:

---

### Q5: The Priority Picker Concept - Decision Tree
**Question**: What questions should it ask to determine starting point?

**Answer**: "I really like that. Some sort of decision tree that we can take the user through."

**Proposed Questions**:
- "Do you have executive buy-in?" (Yes/No/Partial)
- "Do you have budget allocated?"
- "Do you have any policies in place?"
- "Have you had a recent incident/near-miss?"
- "Are you facing regulatory/audit pressure?"

**Output**: Recommended starting point like:
- "Start with Policy Development"
- "Start with Risk Assessment"
- "Start with Quick Win Detection"

**REQUIREMENT CONFIRMED**: Interactive decision tree to triage Day 1 users to their optimal starting point.

---

### Q6: The Rollout Planner - Phase Structure
**Proposed Phases**:
- **Phase 0**: Foundation (get buy-in, allocate budget, understand legal constraints)
- **Phase 1**: Scoping
- **Phase 2**: Prevention/Awareness
- **Phase 3**: Detection
- **Phase 4**: Governance

**Answer**: Yes

**REQUIREMENT CONFIRMED**: 5-phase rollout planner (Phase 0-4) with this exact structure.

---

### Q7: Value Without Incidents - Dashboard Content
**Challenge**: What to show when there are ZERO incidents?

**Proposed Ideas**:
- Risk reduction targets (not actuals)
- Program maturity score
- Policy coverage percentage
- Training completion rates
- "Potential threats prevented" (estimated based on industry benchmarks)
- Compliance checklist progress

**Answer**: "Yes, I like your list."

**ADDITIONAL VALUE SOURCES FROM BARCLAYS POC**:
From **Oversight** functions (can be repurposed):
- Framework mapping
- Volume & framework baseline
- Controls mapping
- Threat intel
- Org risk viewer
- Reporting (with suitable reports tailored for new programs)

From **Foresight** functions:
- "Easy-start" version to be defined in later conversations

**Insight**: We're not starting from zero! Significant Oversight/Foresight functionality from Barclays PoC can be adapted. The key is making them relevant for orgs WITHOUT incident history.

**REQUIREMENTS CONFIRMED**:
1. Dashboard shows maturity/progress metrics instead of incident metrics
2. Reuse Oversight: framework, baseline, controls, threat intel, risk viewer, reporting
3. Create simplified "Foresight Easy-Start" mode (details TBD)

---

## Updated Requirements Summary

### Phase 0: Onboarding & Assessment
1. **Priority Picker Decision Tree**
   - Interactive questionnaire
   - Outputs recommended starting point
   - Questions cover: buy-in, budget, policies, incidents, regulatory pressure

### Phase Structure: 5-Phase Rollout Planner
- **Phase 0**: Foundation (buy-in, budget, legal constraints)
- **Phase 1**: Scoping
- **Phase 2**: Prevention/Awareness
- **Phase 3**: Detection
- **Phase 4**: Governance

### Dashboard & Value Metrics (Zero-Incident Context)
1. Program maturity score
2. Risk reduction targets
3. Policy coverage percentage
4. Training completion rates
5. Compliance checklist progress
6. Potential threats prevented (industry benchmark estimates)

### Adapted Barclays PoC Features
**From Oversight** (keep with modifications):
- Framework mapping
- Volume & framework baseline
- Controls mapping
- Threat intelligence
- Org risk viewer
- Reporting (new reports for starting programs)

**From Foresight** (to be simplified):
- "Easy-Start" mode (details TBD in future conversation)

### Next Discussion Topics:

---

### Q8: Priority Picker Decision Tree - Outcomes
**Question**: What happens after each outcome?
- Outcome A: "Start with Policy Development"
- Outcome B: "Start with Risk Assessment"
- Outcome C: "Start with Quick Win Detection"

**Answer**: "Ask the user - we will demo all of these."

**REQUIREMENT IDENTIFIED**: Demo needs to showcase all three starting paths. Each outcome leads to interactive demonstration of that pathway.

**Insight**: This isn't just a tool - it's a DEMO platform that educates through showing. User experience is pedagogical.

---

### Q9: The "Incidents" Module - Evolving Demo
**Question**: Keep, remove, hide, or repurpose Incidents module?

**Answer**: "Good point! We should have the demo evolve as the org matures. So when they do have incidents, then we can show KPIs, etc. We need to work on a timeline story that we can gear the demo up to - make some suggestions. The demo will show increasing sophistication as we go through."

**CRITICAL INSIGHT**: This is an **EVOLVING DEMO** that progresses through maturity stages over time.

**REQUIREMENT IDENTIFIED**: Need a **timeline story** that demonstrates:
- Month 0: No incidents, basic setup
- Month X: First incidents logged, early KPIs appear
- Month Y: Trends emerging, detection improving
- Month Z: Full mature program with historical data

**Action Item**: Generate timeline story suggestions with increasing sophistication levels.

---

### Q10: Framework & Controls Mapping
**Question**: Pre-populated or empty? Which frameworks?

**Answer**: "Prepopulated, but keep the content as-is from the Barclays PoC. We will need to extend the demo here to make the user able to add & remove the default content with some pre-canned examples for different industries (the implementation will need to let me quickly swap in client relevant content for this. Note: we are specific to insider threat, not a generic cyber application, so just straight NIST or ISO mappings are not sufficient. We should revisit this when we understand the value for the client."

**REQUIREMENTS IDENTIFIED**:
1. Pre-populate with Barclays PoC content (as baseline)
2. User can add/remove default content
3. Pre-canned examples for different industries (swappable)
4. **Implementation constraint**: Must allow quick swapping of client-relevant content
5. **Specificity requirement**: Insider threat-specific frameworks, not generic cyber
6. Revisit framework selection when client value is clearer

**Insight**: This is a DEMO tool for sales/education, not just a product. Content needs to be industry-customizable.

---

### Q11: Training & Awareness (Phase 2)
**Question**: What's included in training capability?

**Answer**: "We should include a training capability that the client can select and we run the campaign, send reminders, monitor completion, etc."

**REQUIREMENTS IDENTIFIED**:
1. Campaign selection (client chooses training modules)
2. Campaign execution (platform runs it)
3. Reminder system (automated nudges)
4. Completion monitoring (track who's done, who hasn't)

**Insight**: Full-cycle training management, not just tracking. This is an active engagement tool.

---

## Critical Design Shift: Demo as Educational Journey

**MAJOR INSIGHT FROM Q8-Q9**:
This is not just a "starter version" of the Barclays PoC. This is a **DEMONSTRATION PLATFORM** that:
1. Shows potential clients what's possible
2. Evolves through maturity stages to tell a story
3. Educates users on the journey from zero to mature program
4. Must be industry-customizable for different client contexts

---

## Updated Requirements Summary (v2)

### Core Platform Type
**DEMO PLATFORM** - Educational + Sales Tool + Starter Product Hybrid

### Phase 0: Onboarding & Assessment
1. **Priority Picker Decision Tree**
   - Interactive questionnaire
   - Three demo pathways: Policy Development, Risk Assessment, Quick Win Detection
   - Each pathway shows interactive demonstration

### Phase Structure: 5-Phase Rollout Planner (WITH TIMELINE STORY)
- **Phase 0**: Foundation (buy-in, budget, legal constraints)
- **Phase 1**: Scoping
- **Phase 2**: Prevention/Awareness
- **Phase 3**: Detection (incidents start appearing in demo)
- **Phase 4**: Governance (full KPIs, trends, mature capabilities)

**PENDING**: Define specific timeline story (Month 0, 3, 6, 12, etc.)

### Dashboard & Value Metrics (Zero-Incident Context)
1. Program maturity score
2. Risk reduction targets
3. Policy coverage percentage
4. Training completion rates
5. Compliance checklist progress
6. Potential threats prevented (industry benchmark estimates)

**Evolution**: As demo progresses through timeline, KPIs and incidents gradually appear

### Adapted Barclays PoC Features
**From Oversight** (keep with modifications):
- Framework mapping (PREPOPULATED, insider threat-specific, swappable by industry)
- Volume & framework baseline
- Controls mapping (PREPOPULATED, customizable, client-swappable)
- Threat intelligence
- Org risk viewer
- Reporting (new reports for starting programs)

**From Foresight** (to be simplified):
- "Easy-Start" mode (details TBD in future conversation)

**From Incidents** (evolutionary):
- Hidden/minimal in early stages
- Appears and grows as demo timeline progresses
- Enables KPI tracking once incidents exist in story

### Training & Awareness Module (Phase 2)
1. Campaign selection interface
2. Automated campaign execution
3. Reminder/nudge system
4. Completion tracking & reporting
5. Integration with dashboard metrics (training completion rates)

### Technical Requirements
1. **Industry Content Swapping**: Easy mechanism to swap pre-canned content for different industries
2. **Timeline Progression**: Demo can be "fast-forwarded" through maturity stages
3. **Modular Visibility**: Features appear/hide based on program maturity stage

---

## Timeline Story Options - FOR DISCUSSION

### Option A: 12-Month Journey (Realistic Timeline)

**Month 0-1: Foundation Phase**
- Dashboard shows: Program maturity = 0%, empty states everywhere
- Features visible: Priority Picker, Rollout Planner, Framework viewer (read-only)
- User activity: Complete priority picker, review recommended starting path
- Milestone: "Program Launch" - policies drafted, stakeholders identified

**Month 2-4: Prevention/Awareness Phase**
- Dashboard shows: Training completion %, policy coverage %, maturity = 25%
- Features visible: Training campaigns, policy distribution, awareness metrics
- User activity: Launch first training campaign, distribute policies
- Milestone: "First Campaign Complete" - 80%+ staff trained on basics

**Month 5-7: Early Detection Phase**
- Dashboard shows: First 3-5 incidents appear, early MTTD/MTTR, maturity = 50%
- Features visible: Incident logging, basic analytics, risk viewer with live data
- User activity: Log first concerns, establish response procedures
- Milestone: "Detection Live" - monitoring tools configured, first incident resolved

**Month 8-10: Maturing Detection Phase**
- Dashboard shows: 15-25 incidents total, trends starting to emerge, maturity = 70%
- Features visible: All Oversight functions, basic Foresight, emerging trends
- User activity: Analyze patterns, refine detection rules, improve MTTR
- Milestone: "Program Operational" - consistent detection and response capability

**Month 11-12: Governance & Optimization Phase**
- Dashboard shows: 30+ incidents, clear trends, full KPIs, maturity = 85%
- Features visible: Full Barclays PoC functionality, predictive analytics
- User activity: Report to board, demonstrate ROI, optimize processes
- Milestone: "Mature Program" - ready for audit, showing measurable value

---

### Option B: 18-Month Journey (Conservative, Thorough)

**Months 0-3: Foundation (Extended)**
- Includes buy-in building, budget allocation, legal/HR consultation
- Multiple stakeholder presentations, policy development cycles
- Slower but more thorough groundwork

**Months 4-8: Prevention/Awareness (Extended)**
- Multiple training waves, different departments/roles
- Policy refinement based on feedback
- Awareness campaigns with measurement

**Months 9-12: Detection Buildout**
- Tool evaluation and procurement
- Phased deployment of monitoring
- First incidents trickle in slowly

**Months 13-15: Detection Maturation**
- Incident volume increases as detection improves
- Pattern recognition begins
- Response procedures refined

**Months 16-18: Full Operation**
- All capabilities operational
- Regular reporting established
- Continuous improvement mode

---

### Option C: 6-Month Journey (Aggressive, Well-Funded)

**Month 0-1: Rapid Foundation**
- Pre-existing buy-in and budget
- Quick policy adoption
- Immediate tool procurement

**Month 2-3: Concurrent Prevention & Early Detection**
- Training and monitoring start simultaneously
- First incidents logged quickly
- Rapid iteration

**Month 4-5: Scaling & Refinement**
- Incident volume grows rapidly
- Trends emerge quickly
- Quick optimizations

**Month 6: Operational Maturity**
- Full capability operational
- Demonstrable results
- Board presentation ready

---

### Option D: "Demo Modes" (Most Flexible)

Rather than fixed timelines, have **demo modes** user can select:

1. **"Show Me the Journey"** - Step through timeline interactively, user controls pace
2. **"Month 0 View"** - Pure startup, empty states, shows what to do first
3. **"Month 6 View"** - Mid-maturity, some data, trends emerging
4. **"Month 12 View"** - Mature program, full capabilities
5. **"Custom Timeline"** - User inputs their target timeline, demo adjusts milestones

Each mode shows appropriate features, data volume, and capabilities.

---

### My Recommendation: Option D + Option A

**Why**:
- Demo flexibility (can show any stage to any audience)
- Default to realistic 12-month journey (Option A) for structure
- Allow presenters to jump to any stage for client conversations
- Provides both "educational story" and "sales flexibility"

**What do you think?** Which timeline approach fits your vision? Or should we combine elements?

---

### Q12: Tool Deployment Timeline & Sophistication Levels

**User Input**: "Around month 4, DLP tools should be deployed. UEBA tools are for sophisticated orgs and/or those that use advanced MSSPs - this should be a client discussion point"

**CRITICAL INSIGHTS**:
1. **Month 4 = DLP Deployment** - This is a concrete milestone anchor
2. **UEBA = Optional/Advanced** - Not for all orgs, depends on sophistication level and MSSP capability
3. **Client Discussion Required** - Demo needs to surface UEBA as a decision point, not an assumption

**REQUIREMENTS IDENTIFIED**:

1. **Tool Deployment Milestones**:
   - Month 4: DLP tools go live (data loss prevention)
   - Month X (TBD): UEBA tools (optional, based on client sophistication)

2. **Demo Features Needed**:
   - "Tool Readiness Assessor" - helps clients decide if they need UEBA
   - MSSP integration discussion points
   - Tool comparison/selection guidance

3. **Sophistication Tiering**:
   - **Tier 1 (Basic)**: Manual monitoring + DLP (Month 4)
   - **Tier 2 (Intermediate)**: DLP + basic analytics
   - **Tier 3 (Advanced)**: DLP + UEBA + MSSP integration

**QUESTION FOR REFINEMENT**:
Should the Priority Picker (Day 1 tool) also assess:
- "What's your technical sophistication level?"
- "Do you use an MSSP?"
- "What's your budget for tools?"

This would help route them to appropriate tier and set expectations about UEBA.

**REVISED TIMELINE CONSIDERATION**:

**Option A (12-Month) - REFINED WITH TOOL MILESTONES**:

**Month 0-1: Foundation Phase**
- Dashboard shows: Program maturity = 0%, empty states everywhere
- Features visible: Priority Picker, Rollout Planner, Framework viewer (read-only)
- User activity: Complete priority picker, review recommended starting path
- **Tool Discussion**: Identify sophistication tier, plan tool procurement
- Milestone: "Program Launch" - policies drafted, stakeholders identified

**Month 2-4: Prevention/Awareness Phase**
- Dashboard shows: Training completion %, policy coverage %, maturity = 25%
- Features visible: Training campaigns, policy distribution, awareness metrics
- User activity: Launch first training campaign, distribute policies
- **Tool Procurement**: DLP tools being evaluated and purchased
- Milestone: "First Campaign Complete" - 80%+ staff trained on basics

**Month 4-5: DLP Deployment Phase** ⭐ KEY MILESTONE
- Dashboard shows: Training metrics + DLP readiness indicators
- Features visible: DLP integration status, data classification guidance
- User activity: Deploy DLP tools, configure policies, test alerts
- **Decision Point**: "Do we need UEBA?" - assessment wizard appears
- Milestone: "DLP Live" - data loss prevention active and monitoring

**Month 5-7: Early Detection Phase**
- Dashboard shows: First 3-5 incidents appear (many from DLP alerts), early MTTD/MTTR, maturity = 50%
- Features visible: Incident logging, basic analytics, risk viewer with live data
- User activity: Log first concerns from DLP, establish response procedures
- **Optional**: If UEBA selected, deployment planning begins
- Milestone: "Detection Live" - monitoring tools configured, first incident resolved

**Month 8-10: Maturing Detection Phase**
- Dashboard shows: 15-25 incidents total, trends starting to emerge, maturity = 70%
- Features visible: All Oversight functions, basic Foresight, emerging trends
- User activity: Analyze DLP patterns, refine detection rules, improve MTTR
- **Optional**: UEBA deployment (if selected), MSSP integration
- Milestone: "Program Operational" - consistent detection and response capability

**Month 11-12: Governance & Optimization Phase**
- Dashboard shows: 30+ incidents, clear trends, full KPIs, maturity = 85%
- Features visible: Full Barclays PoC functionality, predictive analytics (if UEBA)
- User activity: Report to board, demonstrate ROI, optimize processes
- **Advanced**: UEBA-driven behavioral analytics (if deployed)
- Milestone: "Mature Program" - ready for audit, showing measurable value

---

### Tool Sophistication Decision Tree

**During Priority Picker OR Month 4 Decision Point**:

```
Q: "Do you currently use a Managed Security Service Provider (MSSP)?"
├─ Yes, Advanced MSSP → Recommend UEBA exploration
├─ Yes, Basic MSSP → Optional UEBA, focus on DLP first
└─ No MSSP → Stick with DLP, defer UEBA discussion

Q: "What's your technical team size?"
├─ 0-2 people → DLP only, UEBA not recommended
├─ 3-5 people → DLP + optional UEBA if MSSP available
└─ 6+ people → Full UEBA recommendation

Q: "What's your tool budget range?"
├─ <$50k/year → DLP focus
├─ $50k-$150k/year → DLP + consider UEBA
└─ >$150k/year → Full toolset including UEBA
```

**Output**:
- "We recommend DLP deployment in Month 4. UEBA is optional - let's discuss in Month 5."
- OR "Based on your MSSP and team size, we recommend DLP + UEBA starting Month 4-5."

---

### Q13: Timeline Selection
**Answer**: Option D + A (flexible demo modes with 12-month default)

**REQUIREMENT CONFIRMED**:
- Demo has flexible modes (jump to any stage)
- Defaults to 12-month journey structure
- Presenter can adapt to client context in real-time

---

### Q14: Incident Sources Visualization
**Answer**: Yes

**REQUIREMENT CONFIRMED**: Demo should show incident source breakdown:
- % from DLP alerts
- % from employee reports
- % from manager escalations
- % from HR referrals
- % from IT security alerts

**Insight**: This illustrates DLP ROI by showing how incident detection changes pre/post DLP deployment.

---

### Q15: MSSP Integration
**Answer**: "We'll come back to that in the future, skip for now, just add a client discovery question about MSSP use or not."

**REQUIREMENT IDENTIFIED**:
- Add MSSP usage question to Priority Picker/discovery
- Defer detailed MSSP integration features to future conversation
- Capture MSSP status as data point for sophistication assessment

---

### Q16: "Quick Wins" Definition (Pre-DLP)
**Question**: What's a quick win before DLP deploys in Month 4?

**Answer**: "I like those 3. Also policy evaluation (we can build an AI tool to parse them from an insider perspective to identify gaps)"

**REQUIREMENTS CONFIRMED - Quick Win Options**:
1. **Policy violation self-reporting portal** - Give employees safe way to report concerns
2. **Manager concern submission form** - Enable managers to flag risky behaviors
3. **Automated HR flag triggers** - Connect terminations, PIPs, disciplinary actions to insider risk
4. **AI-Powered Policy Gap Analysis** ⭐ NEW - AI tool to analyze existing policies for insider threat gaps

**Insight**: Quick wins focus on HUMAN reporting channels before automated tools deploy. Plus AI analysis provides immediate value from existing documentation.

---

### DLP Procurement & Budget Timeline - CRITICAL UPDATE

**User Input**: "To deploy DLP in month 4, vendor selection needs to start after program approval. So DLP spend needs to be estimated & be included in the approval prep. O365 Purview comes with many O365 licenses, so let's add that to the discovery q's. We should have a template pptx for program definition outline that the client can use as a template for their discussion."

**CRITICAL INSIGHTS**:
1. **Month 4 DLP deployment requires Month 0 budgeting** - procurement timeline is ~3-4 months
2. **O365 Purview = Free Option** - Many clients already have DLP capability but don't know it
3. **Program Approval Process** - Needs budget estimates, business case, presentation materials

**REQUIREMENTS IDENTIFIED**:

### 1. Updated Priority Picker Questions (Discovery):
```
Q: "What Microsoft 365 license do you have?"
├─ E5 / A5 → You already have Purview DLP! (free)
├─ E3 / A3 → Purview available as add-on (~$5-10/user/month)
├─ Business Basic/Standard → Need third-party DLP
└─ Don't use Microsoft 365 → Need full DLP procurement

Q: "Do you currently use an MSSP?"
├─ Yes → [Capture for future UEBA discussion]
└─ No → [Note for tool deployment planning]

Q: "What's your estimated budget for insider threat tools?"
├─ <$50k/year → Focus on built-in tools (Purview if available)
├─ $50k-$150k/year → DLP + basic tooling
└─ >$150k/year → Full toolset consideration
```

### 2. Program Approval Presentation Template (PPTX)

**REQUIREMENT**: Template PowerPoint for client use in getting program approval

**Suggested Sections**:
1. **Executive Summary**
   - What is insider threat?
   - Why now? (trigger that prompted discussion)
   - What's at risk?

2. **Business Case**
   - Industry statistics (cost of insider incidents)
   - Regulatory/compliance drivers
   - Risk to organization (data, IP, reputation)

3. **Proposed Program Structure**
   - 5 phases (Foundation → Governance)
   - 12-month roadmap
   - Milestone-based approach

4. **Budget Requirements** ⭐ CRITICAL
   - Year 1 costs breakdown:
     - Personnel (FTE or % allocation)
     - Tools (DLP, UEBA if applicable)
     - Training/awareness materials
     - Consulting/external support
   - Pre-populated estimates based on org size
   - Purview option highlighted (if applicable)

5. **Quick Wins & Value Demonstration**
   - Month 1-3 deliverables (no budget needed)
   - Month 4+ with tooling
   - Month 12 expected outcomes

6. **Resource Requirements**
   - Team structure
   - Time commitments
   - Cross-functional dependencies (HR, IT, Legal)

7. **Success Metrics**
   - Program maturity score
   - Coverage metrics
   - Incident detection capability
   - Risk reduction targets

8. **Next Steps & Decision Points**
   - Approval needed by [date]
   - Procurement timeline for Month 4 DLP
   - Stakeholder engagement plan

**Output from Demo Platform**:
- User completes Priority Picker
- Platform generates CUSTOMIZED PPTX with their specific:
  - Org size estimates
  - Purview availability (if O365 detected)
  - Budget ranges for their context
  - Industry-relevant risk scenarios
  - Recommended quick wins

**REQUIREMENT**: Platform exports presentation ready for board/executive review

---

### REVISED Month 0-4 Timeline (Pre-DLP Deployment)

**Month 0: Program Initiation & Approval**
- Complete Priority Picker (discover O365 license, MSSP, budget)
- Generate program approval presentation (PPTX export)
- Present to executive stakeholders
- **Outcome**: Budget approval + authority to proceed
- **DLP Decision**: Purview (free/cheap) vs. third-party vendor
- **Quick Win Deployment**: Launch AI Policy Gap Analysis tool

**Month 0-1: Vendor Selection (if needed)**
- If Purview → Configuration planning
- If third-party → RFP process, vendor demos, selection
- **Budget allocated**, procurement process begins

**Month 1-2: Foundation & Quick Wins**
- Deploy human reporting channels:
  - Policy violation self-reporting portal
  - Manager concern submission form
  - HR flag automation (terminations, PIPs)
- Run AI policy analysis, get gap report
- Begin policy development based on gaps
- Launch training campaign planning

**Month 2-4: Prevention/Awareness + DLP Prep**
- Training campaigns active
- Policy distribution
- **DLP Procurement**: Contracting, purchase orders, delivery
- **DLP Configuration Planning**: Policies, rules, alert thresholds
- First concerns logged via quick win channels

**Month 4: DLP Deployment**
- DLP goes live (Purview or vendor solution)
- Initial alert tuning period
- Incident volume increases from automated detection

---

### AI Policy Gap Analysis Tool - Feature Definition

**REQUIREMENT IDENTIFIED**: AI-powered policy analysis for insider threat gaps

**How It Works**:
1. **User uploads existing policies** (PDFs, Word docs, etc.)
2. **AI analyzes from insider threat perspective**:
   - Data handling policies
   - Acceptable use policies
   - BYOD policies
   - Termination procedures
   - Remote work policies
   - Third-party/contractor access
3. **AI generates gap report**:
   - What's covered well
   - What's missing
   - What's ambiguous
   - Insider threat scenarios not addressed
4. **Outputs prioritized recommendations**:
   - Critical gaps (must fix)
   - Important gaps (should fix)
   - Nice-to-have improvements
5. **Provides policy templates** for identified gaps

**Value Proposition**:
- Immediate actionable insight (Day 1 capability)
- Demonstrates platform intelligence
- Gives client something to DO before budgets/tools arrive
- Creates policy baseline for training and DLP configuration

**Demo Scenario**:
- User uploads 3-5 sample policies
- AI processes in 30-60 seconds
- Shows impressive gap analysis report
- Client sees immediate value from platform

---

## COMPREHENSIVE REQUIREMENTS SUMMARY (v3) - COMPLETE AS OF Q16

### Core Platform Definition
**TYPE**: Demo Platform - Educational + Sales Tool + Starter Product Hybrid
**PURPOSE**: Help organizations START insider threat programs from zero
**AUDIENCE**: Non-professional orgs (small teams, limited resources, no dedicated security staff)
**JOURNEY**: Scoping → Prevention/Awareness → Detection → Governance

---

### 1. PRIORITY PICKER (Day 1 Decision Tree)

**Purpose**: Triage users to optimal starting point + gather critical data

**Discovery Questions**:
1. Executive buy-in status (Yes/No/Partial)
2. Budget allocated (Yes/No)
3. Existing policies (Yes/No/Partial)
4. Recent incident or near-miss (Yes/No)
5. Regulatory/audit pressure (Yes/No)
6. **Microsoft 365 license type** (E5/A5/E3/A3/Basic/None)
7. **MSSP usage** (Yes/No)
8. **Tool budget range** (<$50k / $50k-$150k / >$150k)
9. **Technical team size** (0-2 / 3-5 / 6+)
10. **Industry** (for content customization)

**Outputs**:
- Recommended starting path (Policy Development / Risk Assessment / Quick Win Detection)
- Sophistication tier assignment (Basic / Intermediate / Advanced)
- DLP recommendation (Purview free/cheap vs. third-party)
- UEBA readiness assessment
- **PPTX Export**: Customized program approval presentation

---

### 2. PROGRAM APPROVAL PRESENTATION (PPTX Export)

**Generated After Priority Picker Completion**

**Sections**:
1. Executive Summary (what, why, risk)
2. Business Case (industry stats, compliance, organizational risk)
3. Proposed Program Structure (5 phases, 12-month roadmap)
4. **Budget Requirements** (personnel, tools, training, consulting)
   - Customized based on org size, Purview availability, tool choices
5. Quick Wins & Value Demo (Month 1-3 deliverables)
6. Resource Requirements (team, time, dependencies)
7. Success Metrics (maturity score, coverage, detection capability)
8. Next Steps (approval timeline, procurement schedule)

**Customization**:
- Pre-populated with user's Priority Picker data
- Industry-relevant risk scenarios
- Purview availability highlighted if applicable
- Budget estimates for their context

---

### 3. FIVE-PHASE ROLLOUT PLANNER

**Phase 0: Foundation** (Month 0)
- Get buy-in, allocate budget, understand legal constraints
- Complete Priority Picker
- Generate & present approval PPTX
- **Output**: Budget approval + authority to proceed

**Phase 1: Scoping** (Month 0-2)
- DLP vendor selection (if not Purview)
- Deploy Quick Wins (see section 4)
- AI Policy Gap Analysis
- Training campaign planning

**Phase 2: Prevention/Awareness** (Month 2-4)
- Training campaigns active
- Policy distribution
- Awareness metrics tracking
- DLP procurement & configuration planning

**Phase 3: Detection** (Month 4-7)
- **Month 4: DLP Deployment** ⭐
- Incident logging begins
- First MTTD/MTTR metrics
- Optional UEBA decision point

**Phase 4: Governance** (Month 8-12)
- Mature detection capability
- Full KPI tracking
- Board reporting
- Process optimization
- Optional UEBA deployment (if selected)

---

### 4. QUICK WINS (Pre-DLP, Months 1-3)

**Human Reporting Channels**:
1. **Policy Violation Self-Reporting Portal**
   - Safe channel for employees to report concerns
   - Anonymous option available
   - Integration with incident logging

2. **Manager Concern Submission Form**
   - Managers flag risky behaviors
   - Structured intake format
   - Priority routing

3. **Automated HR Flag Triggers**
   - Terminations automatically create alerts
   - PIPs (Performance Improvement Plans) flagged
   - Disciplinary actions tracked
   - Integration with HRIS systems

**AI-Powered Tool**:
4. **AI Policy Gap Analysis** ⭐
   - Upload existing policies (PDF, Word, etc.)
   - AI analyzes for insider threat gaps
   - Generates prioritized gap report
   - Provides policy templates for gaps
   - **Demo value**: Immediate actionable insight in 30-60 seconds

---

### 5. TIMELINE STRUCTURE

**Selected Approach**: Option D + A
- **Default**: 12-month realistic journey
- **Flexibility**: Demo modes allow jumping to any stage

**Demo Modes**:
1. "Show Me the Journey" - Interactive step-through
2. "Month 0 View" - Pure startup, empty states
3. "Month 6 View" - Mid-maturity, some data
4. "Month 12 View" - Mature program, full capabilities
5. "Custom Timeline" - User-defined pace

**12-Month Default Timeline**:

| Phase | Months | Maturity | Key Milestones |
|-------|--------|----------|----------------|
| Foundation | 0-1 | 0% → 15% | Approval, Quick Wins, AI Policy Analysis |
| Scoping | 1-2 | 15% → 25% | Vendor selection, Human reporting live |
| Prevention | 2-4 | 25% → 40% | Training campaigns, DLP procurement |
| Detection | 4-7 | 40% → 70% | **DLP live (M4)**, First incidents, MTTD/MTTR |
| Governance | 8-12 | 70% → 85% | Trends, Full KPIs, Board reporting, Optimization |

---

### 6. DASHBOARD & VALUE METRICS

**Zero-Incident Phase (Months 0-4)**:
- Program maturity score
- Policy coverage percentage
- Training completion rates
- Compliance checklist progress
- Risk reduction targets (not actuals)
- Quick win channel activity
- DLP deployment readiness

**Early Detection Phase (Months 4-7)**:
- First incidents appear (3-5 total)
- **Incident source breakdown**:
  - % from DLP alerts
  - % from employee reports
  - % from manager escalations
  - % from HR referrals
  - % from IT security alerts
- Early MTTD/MTTR metrics
- Alert volume trends

**Mature Phase (Months 8-12)**:
- Full 10 KPIs from Barclays PoC
- Incident trends over time
- Behavioral analytics (if UEBA)
- Predictive insights
- ROI demonstration

---

### 7. TOOL DEPLOYMENT STRATEGY

**DLP (Month 4 Deployment)**:
- **Option 1: Microsoft 365 Purview** (if E5/A5 license - FREE)
- **Option 2: Purview Add-on** (if E3/A3 - ~$5-10/user/month)
- **Option 3: Third-Party Vendor** (if no O365 or preference)

**Procurement Timeline**:
- Month 0: Budget approval, vendor decision
- Month 0-1: RFP process (if third-party)
- Month 1-3: Contracting, purchase orders, delivery
- Month 3-4: Configuration, policy setup, testing
- Month 4: Go live

**UEBA (Optional, Month 8+ if selected)**:
- **Tier 1 (Basic)**: Skip UEBA, DLP only
- **Tier 2 (Intermediate)**: Consider if MSSP available
- **Tier 3 (Advanced)**: Full UEBA recommendation

**Decision Criteria** (assessed in Priority Picker or Month 4):
- MSSP sophistication level
- Technical team size (6+ people for UEBA)
- Budget >$150k/year
- Organizational maturity

---

### 8. ADAPTED BARCLAYS POC FEATURES

**From Oversight Module** (Keep with Modifications):
1. **Framework Mapping**
   - PREPOPULATED with insider threat-specific frameworks
   - NOT generic NIST/ISO (too broad)
   - Industry-swappable content
   - User can add/remove defaults

2. **Volume & Framework Baseline**
   - Adapted for zero-incident orgs
   - Shows targets instead of actuals

3. **Controls Mapping**
   - PREPOPULATED, customizable
   - Client-swappable for demos

4. **Threat Intelligence**
   - Industry benchmarks
   - Threat landscape education
   - "What could happen" scenarios

5. **Org Risk Viewer**
   - Risk assessment mode (no incidents yet)
   - Potential risk areas highlighted

6. **Reporting**
   - New reports for starting programs
   - Progress reports (not incident reports)
   - Maturity assessments

**From Foresight Module** (Simplified):
- "Easy-Start" mode (details TBD in future conversation)
- Defer behavioral analytics until detection phase

**From Incidents Module** (Evolutionary):
- Hidden in Months 0-4
- Appears at Month 4 (DLP deployment)
- Grows as incidents accumulate
- Full KPI capability at Month 8+

---

### 9. TRAINING & AWARENESS MODULE

**Campaign Management**:
1. **Campaign Selection Interface**
   - Pre-built training modules
   - Customizable content
   - Role-based training paths

2. **Automated Execution**
   - Schedule campaigns
   - Auto-enrollment
   - Progress tracking

3. **Reminder System**
   - Automated nudges
   - Escalation to managers
   - Custom messaging

4. **Completion Tracking**
   - Individual progress
   - Department rollup
   - Executive dashboard
   - Integration with HR systems

5. **Reporting**
   - Completion rates (dashboard metric)
   - Time to completion
   - Quiz/assessment results (if applicable)

---

### 10. TECHNICAL REQUIREMENTS

**Content Management**:
1. **Industry Content Swapping**
   - Easy mechanism to swap frameworks, controls, risk scenarios
   - Pre-canned examples for: Financial, Healthcare, Technology, Manufacturing, Government
   - Must allow quick customization for client demos

**Demo Flexibility**:
2. **Timeline Progression**
   - Demo can jump to any maturity stage
   - "Fast-forward" through months
   - Reset to Month 0 for new demo

3. **Modular Visibility**
   - Features appear/hide based on program maturity
   - Smooth transitions between phases
   - No jarring "empty" experiences

**Export Capabilities**:
4. **PPTX Generation**
   - Customized program approval presentations
   - Based on Priority Picker data
   - Professional, board-ready format

5. **Report Exports**
   - Progress reports
   - Gap analysis reports (AI tool)
   - Training completion reports

**Integration Points**:
6. **HRIS Integration** (HR flag triggers)
7. **O365 Integration** (Purview detection, license discovery)
8. **MSSP Integration** (future - deferred)

---

### 11. AI CAPABILITIES

**AI Policy Gap Analysis Tool** ⭐ SIGNATURE FEATURE
- Natural language processing of policy documents
- Insider threat-specific analysis
- Gap identification & prioritization
- Template recommendations
- 30-60 second processing time
- Immediate demo value

**Future AI Opportunities** (Not Yet Defined):
- Behavioral analytics (UEBA phase)
- Predictive risk scoring
- Incident pattern recognition
- Training content personalization

---

### 12. DEFERRED FOR FUTURE DISCUSSION

1. **Foresight "Easy-Start" Mode** - Simplified behavioral analytics
2. **MSSP Integration Details** - Alert forwarding, joint workflows
3. **Advanced UEBA Features** - Specifics for Tier 3 orgs
4. **Additional AI Capabilities** - Beyond policy gap analysis

---

## Next Steps & Open Questions

### Completed in This Session ✅
1. ✅ Identified core platform type (Demo + Educational + Sales tool)
2. ✅ Defined Priority Picker with 10 discovery questions
3. ✅ Designed 5-phase rollout planner (Foundation → Governance)
4. ✅ Created 12-month timeline with flexible demo modes
5. ✅ Specified 4 Quick Win features (including AI Policy Gap Analysis)
6. ✅ Defined DLP deployment strategy (Month 4, with Purview option)
7. ✅ Designed Program Approval PPTX export
8. ✅ Mapped dashboard metrics for zero-incident phase
9. ✅ Identified incident source breakdown visualization
10. ✅ Specified sophistication tiers (Basic/Intermediate/Advanced)

### Open for Future Sessions 🔄
1. **Foresight "Easy-Start" Mode** - How to simplify behavioral analytics for new programs
2. **MSSP Integration Details** - Alert forwarding, joint workflows, SOC integration
3. **Advanced UEBA Features** - Specific capabilities for Tier 3 organizations
4. **Industry Framework Details** - Which insider threat-specific frameworks to prepopulate
5. **Training Content** - Specific modules, learning paths, assessment criteria
6. **Policy Templates** - What templates to provide in AI gap analysis output
7. **Budget Estimates** - Specific cost ranges for PPTX generation

### Implementation Priorities
**Phase 1 (MVP)**:
1. Priority Picker decision tree
2. Basic PPTX export (template-based)
3. AI Policy Gap Analysis tool
4. 3 Human reporting channels (self-report, manager, HR flags)
5. Dashboard with maturity score + quick win metrics

**Phase 2 (Demo Enhancement)**:
1. Demo mode switcher (Month 0/6/12 views)
2. Industry content swapping mechanism
3. Incident source breakdown visualization
4. Training campaign management
5. Adapted Oversight features

**Phase 3 (Full Capability)**:
1. DLP integration (Purview + vendor options)
2. Full timeline progression
3. All Barclays PoC features adapted
4. Foresight Easy-Start mode
5. MSSP integration

---

## Session Metadata - FINAL

**Duration**: ~90 minutes of co-elicitation
**Questions Addressed**: Q1-Q16
**Requirements Identified**: 50+ discrete features/capabilities
**Major Deliverables Designed**:
- Priority Picker (10-question decision tree)
- Program Approval PPTX (8-section template)
- 5-Phase Rollout Planner (detailed)
- 4 Quick Win Features (including AI tool)
- 12-Month Timeline (with flexible demo modes)
- Complete dashboard metrics strategy

**Status**: ✅ Ready for next phase (implementation planning or additional feature elicitation)

---

## File Saved
**Location**: `/home/jez/code/non-Insider-Treat-orgs/session-notes-2025-10-31-153500-analyst-co-elicitation.md`
**Size**: 1,127 lines (comprehensive verbatim documentation)


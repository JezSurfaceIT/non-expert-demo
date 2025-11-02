# Sprint Backlog - Non-Expert Insider Threat Demo Platform
# BMAD Orchestration Edition

**Version**: 1.0
**Date**: 2025-11-02
**Execution Model**: BMAD Orchestrator with Parallel Claude Code Agents
**Base Codebase**: Clone from `/home/jez/code/Barclays-PoC-on-Vercel`
**Tech Stack**: Next.js 14 + React 18 + TypeScript + JSON file storage

---

## Executive Summary

**Total Demo Scope**: 60 stories (38 functional + 22 mockups)
**Story Points**: ~191 points
**Sprints**: 11 sprints (Sprint 0 + Sprints 1-10)
**Execution**: Parallel where possible, sequential where dependencies exist
**Timeline**: Agent-driven (work till complete)

### Key Strategy

1. **Sprint 0**: Foundation - Clone, cleanup, demo mode infrastructure
2. **Sprints 1-3**: New Features for Non-Experts (Epic 1, 2)
3. **Sprints 4-6**: Dashboard & Metrics (Epic 3)
4. **Sprints 7-8**: Demo Mode System (Epic 8)
5. **Sprints 9-10**: Polish, Mockups, Integration (Epic 4, 5, 6, 7, 9)

---

## Dependency Graph & Parallelization Strategy

### Critical Path (Must Execute Sequentially)

```
Sprint 0 (Foundation)
    ↓
Sprint 1 (Authentication & Account System)
    ↓
Sprint 2 (Priority Picker)
    ↓
Sprint 3 (PPTX Generator)
    ↓
[Parallel Branch Point]
    ├─→ Sprint 4 (Dashboard - Zero Incident)
    ├─→ Sprint 5 (Quick Wins Features - AI Gap Analysis)
    └─→ Sprint 7 (Demo Mode Infrastructure)
         ↓
    [Convergence Point]
         ↓
Sprint 6 (Dashboard - Early Detection & Mature Mockups)
    ↓
Sprint 8 (Demo Mode - Data Population & Feature Visibility)
    ↓
[Parallel Branch Point]
    ├─→ Sprint 9 (Rollout Planner + Training Mockup)
    └─→ Sprint 10 (DLP/Oversight/Content Mockups)
         ↓
    [Final Integration]
```

### Parallelization Opportunities

**After Sprint 3, these can run in PARALLEL** (3 concurrent agents):
- **Agent A**: Sprint 4 (Dashboard - Zero Incident)
- **Agent B**: Sprint 5 (Quick Wins - AI Gap Analysis)
- **Agent C**: Sprint 7 (Demo Mode Infrastructure)

**After Sprint 8, these can run in PARALLEL** (2 concurrent agents):
- **Agent A**: Sprint 9 (Rollout Planner + Training Mockup)
- **Agent B**: Sprint 10 (DLP/Oversight/Content Mockups)

---

## Sprint 0: Foundation & Cleanup

**Goal**: Clone Barclays PoC, remove unwanted features, setup demo mode infrastructure
**Story Points**: N/A (infrastructure)
**Dependencies**: None (entry point)
**Parallel Execution**: No
**Estimated Duration**: Agent works till complete

### Objectives

1. Clone `/home/jez/code/Barclays-PoC-on-Vercel` to `/home/jez/code/non-Insider-Treat-orgs`
2. Remove features NOT in demo scope (60 stories only)
3. Replace database with JSON file storage
4. Create demo mode infrastructure skeleton
5. Setup initial routing for new features

### Tasks

#### Task 0.1: Clone & Initial Cleanup
- [ ] Clone Barclays PoC to new project directory
- [ ] Remove unused files and dependencies
- [ ] Update package.json (project name, version, description)
- [ ] Remove database dependencies (if any)
- [ ] Create initial JSON storage structure (`/data/*.json`)

**Acceptance Criteria**:
- Project cloned successfully
- Build succeeds (`npm run build`)
- Dev server starts (`npm run dev`)

#### Task 0.2: Remove Out-of-Scope Features

**KEEP** (Features in Demo Scope):
- ✅ Authentication system (login, session, RBAC)
- ✅ Settings panel architecture
- ✅ Basic incident logging (simplified from Epic 2)
- ✅ UI component library (Radix, Tailwind)
- ✅ Dashboard layout structure (will be modified)

**REMOVE** (Not in Demo Scope):
- ❌ Foresight Module (`/app/insight/*`)
- ❌ Incidents Explorer (`/app/incidents/explorer`)
- ❌ Incidents Edit (`/app/incidents/[reference]/edit`)
- ❌ Intelligence Module (`/app/intel/*`)
- ❌ Controls & Framework (`/app/controls/*`)
- ❌ Advanced Settings tabs (keep General only)
- ❌ KPI widgets (will be replaced with new dashboard)
- ❌ Heatmaps, Sankey, advanced charts
- ❌ Behavioral analysis components
- ❌ Real-time WebSocket features
- ❌ Database migrations
- ❌ Complex RBAC (simplify to basic roles)

**Files to Remove**:
```bash
rm -rf app/insight
rm -rf app/incidents/explorer
rm -rf app/incidents/[reference]
rm -rf app/intel
rm -rf app/controls
rm -rf components/foresight
rm -rf components/oversight/DashHeatmapTable*
rm -rf components/oversight/SimpleFlatMap*
rm -rf components/oversight/IntelMarquee*
rm -rf components/oversight/OrganizationRoleRisk*
rm -rf lib/db*
rm -rf migrations
```

**Acceptance Criteria**:
- All out-of-scope pages removed
- All out-of-scope components removed
- Build still succeeds
- No broken imports

#### Task 0.3: Create JSON Data Storage Structure

**File Structure**:
```
/data/
  accounts.json         # User accounts
  priority-responses.json  # Priority Picker responses
  ai-policy-gaps.json   # AI Gap Analysis results
  incidents.json        # Basic incident logs
  demo-config.json      # Demo mode settings (Month 0/6/12)
  industry-packs.json   # Industry content packs
  metrics.json          # Dashboard KPI data (demo data)
```

**Sample Schema** (`demo-config.json`):
```json
{
  "currentMode": "month-0",
  "modes": {
    "month-0": {
      "label": "Month 0 - Starting Out",
      "description": "Organization with zero incidents, just starting program",
      "visibleFeatures": ["priority-picker", "pptx-generator", "ai-gap-analysis"],
      "hiddenFeatures": ["dashboard-mature", "dlp-integration", "oversight-features"]
    },
    "month-6": {
      "label": "Month 6 - Early Progress",
      "description": "Organization with basic program, early detection capability",
      "visibleFeatures": ["priority-picker", "pptx-generator", "ai-gap-analysis", "dashboard-early"],
      "hiddenFeatures": ["dashboard-mature", "dlp-integration"]
    },
    "month-12": {
      "label": "Month 12 - Mature Program",
      "description": "Organization with full capability and historical data",
      "visibleFeatures": ["all"],
      "hiddenFeatures": []
    }
  }
}
```

**Acceptance Criteria**:
- `/data/` directory created
- All 7 JSON files created with schema
- Helper functions created to read/write JSON files

#### Task 0.4: Create Demo Mode Infrastructure

**New Files**:
- `/lib/demo-mode/config.ts` - Demo mode configuration utilities
- `/lib/demo-mode/feature-toggle.ts` - Feature visibility logic
- `/components/demo-mode/ModeSwitcher.tsx` - UI for switching modes (admin only)
- `/app/api/demo-mode/route.ts` - API for demo mode state

**Acceptance Criteria**:
- Demo mode utilities created
- Mode switcher component created (not yet integrated)
- API endpoint created for getting/setting mode

#### Task 0.5: Update Routing for New Features

**New Routes to Create** (placeholders):
```
/app/onboarding/page.tsx          # Priority Picker entry
/app/onboarding/pptx/page.tsx     # PPTX Generator
/app/quick-wins/page.tsx          # Quick Wins landing
/app/quick-wins/ai-gap/page.tsx   # AI Policy Gap Analysis
/app/rollout-planner/page.tsx     # Five-Phase Rollout Planner
```

**Update Navigation** (`components/navigation/Sidebar.tsx`):
- Add "Get Started" section (Priority Picker, PPTX)
- Add "Quick Wins" section (AI Gap Analysis)
- Remove "Insights", "Intelligence", "Controls"

**Acceptance Criteria**:
- All new route files created (placeholder "Coming Soon" content)
- Navigation updated
- All routes accessible and render without errors

### Sprint 0 Deliverables

**Code Changes**:
- ✅ Cloned and cleaned codebase
- ✅ JSON storage infrastructure
- ✅ Demo mode skeleton
- ✅ Updated routing

**Documentation**:
- `CLEANUP_REPORT.md` - What was removed and why
- `JSON_STORAGE_SCHEMA.md` - Data structure documentation
- `DEMO_MODE_ARCHITECTURE.md` - How demo modes work

**Success Criteria**:
- [ ] Build succeeds
- [ ] All existing features (login, dashboard placeholder) work
- [ ] No console errors
- [ ] All new routes render (even if placeholder)

---

## Sprint 1: Epic 1 - User Onboarding (Priority Picker)

**Goal**: Implement Priority Picker 10-question decision tree
**Story Points**: 17 (7 stories from Epic 1, Theme 1)
**Dependencies**: Sprint 0 (foundation must be complete)
**Parallel Execution**: No (critical path)
**Estimated Duration**: Agent works till complete

### User Stories

**US-1.1**: Start Priority Picker Quiz (2 points)
**US-1.2**: Answer 10 Contextual Questions (5 points)
**US-1.3**: View Personalized Priority Recommendations (5 points)
**US-1.4**: Understand Why Priorities Were Chosen (3 points)
**US-1.5**: Export Priority Recommendations (2 points)

### Tasks

#### Task 1.1: Build Priority Picker UI

**Components**:
- `/components/onboarding/PriorityPicker.tsx` - Main quiz container
- `/components/onboarding/QuizQuestion.tsx` - Individual question component
- `/components/onboarding/QuizProgress.tsx` - Progress indicator
- `/components/onboarding/QuizResults.tsx` - Results display

**Page**:
- `/app/onboarding/page.tsx` - Entry point with quiz flow

**Questions** (10 questions):
1. **Organization Size**: <500, 500-5000, 5000+
2. **Industry**: Financial, Healthcare, Tech, Govt, Retail, Manufacturing, Other
3. **Regulatory Requirements**: GDPR, HIPAA, SOX, PCI-DSS, None
4. **Existing Tools**: DLP (Purview?), SIEM, UEBA, None
5. **Incident History**: Never, 1-5, 5-20, 20+
6. **Biggest Concern**: Data exfiltration, IP theft, Sabotage, Fraud, Compliance
7. **Budget**: <$50k, $50k-$200k, $200k+
8. **Timeline**: Urgent (3mo), Normal (6mo), Flexible (12mo+)
9. **Technical Maturity**: Basic, Intermediate, Advanced
10. **Executive Support**: Yes (approved), Maybe (need business case), No (building case)

**Acceptance Criteria**:
- [ ] All 10 questions render
- [ ] Progress indicator shows "Question X of 10"
- [ ] "Back" button works
- [ ] Responses saved to state
- [ ] "Submit" on question 10 navigates to results

#### Task 1.2: Implement Decision Logic

**File**: `/lib/onboarding/decision-engine.ts`

**Logic** (simplified):
- If `incidents === 'Never'` → Priority #1: "AI Policy Gap Analysis" (no DLP needed yet)
- If `existingTools.includes('Purview')` → Alert: "You already have DLP! Focus on..."
- If `executiveSupport === 'No'` → Priority #1: "Generate Board Approval PPTX"
- If `budget < $50k` → Recommend free/low-cost options first

**Output**:
```typescript
{
  priorities: [
    {
      rank: 1,
      title: "AI Policy Gap Analysis",
      rationale: "Because you indicated no incidents yet, start with policy review before monitoring.",
      effort: "Low (2-4 weeks)",
      impact: "High - catches 60% of policy gaps",
      steps: ["Review existing policies", "Run AI analysis", "Generate gap report"]
    },
    // ... 4 more priorities
  ],
  alerts: [
    "You already have Microsoft Purview (E5). Skip DLP purchase!"
  ]
}
```

**Acceptance Criteria**:
- [ ] Decision engine returns 5 priorities
- [ ] Rationale references quiz answers
- [ ] Alerts generated for relevant scenarios (Purview detection, etc.)

#### Task 1.3: Build Results Display

**Component**: `/components/onboarding/QuizResults.tsx`

**Layout**:
- Hero: "Your Personalized Insider Threat Roadmap"
- Alert box (if any, e.g., "You have Purview!")
- 5 priority cards (rank 1-5)
  - Title
  - Rationale ("Why this matters for you")
  - Effort estimate
  - Impact estimate
  - "Learn More" expandable with implementation steps
- Export buttons (PDF, Word) - placeholder for now

**Acceptance Criteria**:
- [ ] Results page renders all 5 priorities
- [ ] Rationale text is personalized
- [ ] "Learn More" expands to show steps
- [ ] Alerts displayed prominently

#### Task 1.4: Save Responses to JSON

**API Endpoint**: `/app/api/onboarding/priority-picker/route.ts`

**POST** `/api/onboarding/priority-picker`:
```json
{
  "accountId": "user-123",
  "responses": {
    "orgSize": "500-5000",
    "industry": "Financial",
    ...
  },
  "results": {
    "priorities": [...],
    "alerts": [...]
  },
  "completedAt": "2025-11-02T12:00:00Z"
}
```

**Storage**: Append to `/data/priority-responses.json`

**Acceptance Criteria**:
- [ ] POST endpoint saves to JSON file
- [ ] GET endpoint retrieves user's previous results
- [ ] Data persists across sessions

#### Task 1.5: Export to PDF/Word (Placeholder)

**US-1.5** (Export Priority Recommendations):
- Add "Export to PDF" and "Export to Word" buttons
- For now: Download as JSON (MVP)
- TODO for later sprints: Implement actual PDF/Word generation

**Acceptance Criteria**:
- [ ] Export buttons present
- [ ] Click downloads JSON file with results
- [ ] User receives file named `priority-recommendations-[date].json`

### Sprint 1 Deliverables

**Features**:
- ✅ Priority Picker 10-question quiz
- ✅ Personalized results with 5 priorities
- ✅ Rationale and implementation steps
- ✅ Response persistence to JSON

**Components**:
- `PriorityPicker.tsx`, `QuizQuestion.tsx`, `QuizProgress.tsx`, `QuizResults.tsx`

**APIs**:
- `POST /api/onboarding/priority-picker`
- `GET /api/onboarding/priority-picker`

**Data**:
- `/data/priority-responses.json` (populated)

**Success Criteria**:
- [ ] User can complete quiz end-to-end
- [ ] Results are personalized based on answers
- [ ] Responses saved and retrievable
- [ ] No console errors

---

## Sprint 2: Epic 1 - PPTX Generator

**Goal**: Implement Program Approval PPTX Generator
**Story Points**: 17 (remaining 8 stories from Epic 1, Theme 2)
**Dependencies**: Sprint 1 (uses Priority Picker results)
**Parallel Execution**: No (critical path)
**Estimated Duration**: Agent works till complete

### User Stories

**US-1.8**: Generate Program Approval PPTX (8 points)
**US-1.9**: See Accurate Budget Estimates (3 points)
**US-1.10**: Customize PPTX Before Presenting (2 points)
**US-1.11**: Download PPTX Quickly (1 point)
**US-1.12**: Reference PPTX Content (2 points)
**US-1.13**: Share PPTX with Leadership (1 point)

### Tasks

#### Task 2.1: Install PPTX Generation Library

**Library**: `pptxgenjs` (Node.js PPTX generation)

```bash
npm install pptxgenjs
npm install @types/pptxgenjs --save-dev
```

**Acceptance Criteria**:
- [ ] Library installed
- [ ] TypeScript types available

#### Task 2.2: Design PPTX Template (8 Sections)

**Sections** (from requirements):
1. **Executive Summary** (1 slide)
   - Problem statement
   - Proposed solution (insider threat program)
   - Investment ask ($X)
   - Expected ROI (% risk reduction)

2. **The Business Case** (2 slides)
   - Industry benchmarks ("75% of [industry] orgs have programs")
   - Regulatory requirements (if applicable)
   - Recent incidents in [industry]
   - Cost of inaction

3. **Our Approach** (2 slides)
   - 5-Phase Rollout Plan (Foundation → Governance)
   - Timeline (12-month roadmap)
   - Milestones and quick wins

4. **Top 5 Priorities** (1 slide)
   - From Priority Picker results
   - Why these priorities for your org

5. **Budget Breakdown** (1 slide)
   - Software licenses
   - Professional services
   - Training
   - Internal resources
   - Total: $X

6. **Expected Outcomes** (1 slide)
   - KPIs to track (MTTD, MTTR, etc.)
   - Risk reduction targets
   - Compliance benefits

7. **Implementation Timeline** (1 slide)
   - Month 0-3: Foundation
   - Month 3-6: Quick Wins
   - Month 6-9: DLP Integration
   - Month 9-12: Oversight & Governance

8. **Next Steps** (1 slide)
   - Decision required: Approve program
   - Proposed start date
   - Contact for questions

**Template File**: `/lib/onboarding/pptx-template.ts`

**Acceptance Criteria**:
- [ ] Template designed (8 sections, ~10-12 slides)
- [ ] Placeholder content for each section
- [ ] Professional styling (colors, fonts, logos)

#### Task 2.3: Build PPTX Customization Form

**Component**: `/components/onboarding/PptxCustomizer.tsx`

**Form Fields**:
- Organization name (text)
- Industry (dropdown, from Priority Picker)
- Budget range (dropdown: <$50k, $50k-$200k, $200k+)
- Timeline (dropdown: 3mo, 6mo, 12mo)
- Executive sponsor (text)
- Include regulatory section? (checkbox)
- Include industry benchmarks? (checkbox)
- Custom logo upload (file)

**Page**: `/app/onboarding/pptx/page.tsx`

**Acceptance Criteria**:
- [ ] Form renders all fields
- [ ] Default values pre-filled from Priority Picker responses
- [ ] "Generate PPTX" button enabled when required fields filled

#### Task 2.4: Implement PPTX Generation Logic

**File**: `/lib/onboarding/generate-pptx.ts`

**Function**: `generateProgramApprovalPPTX(config: PptxConfig)`

**Logic**:
1. Load Priority Picker results (top 5 priorities)
2. Calculate budget estimates based on selections
3. Generate slides with personalized content
4. Inject org name, industry benchmarks, etc.
5. Return PPTX blob

**Budget Calculation** (simplified):
```typescript
const budgetEstimate = {
  software: orgSize < 500 ? 15000 : orgSize < 5000 ? 45000 : 120000,
  services: timeline === '3mo' ? 50000 : timeline === '6mo' ? 30000 : 15000,
  training: employeeCount * 20,
  internal: 40000, // 0.5 FTE for 1 year
  total: software + services + training + internal
}
```

**Acceptance Criteria**:
- [ ] Function generates valid PPTX file
- [ ] All 8 sections included
- [ ] Content personalized with form inputs
- [ ] Budget calculations accurate

#### Task 2.5: Build Download & Preview UI

**Component**: `/components/onboarding/PptxPreview.tsx`

**Features**:
- Preview of slide titles (not full render, just outline)
- "Download PPTX" button
- "Edit Settings" button (back to customizer)
- "Share via Email" button (future: sends to leadership)

**API Endpoint**: `/app/api/onboarding/generate-pptx/route.ts`

**POST** `/api/onboarding/generate-pptx`:
```json
{
  "accountId": "user-123",
  "config": { ... }
}
```

**Response**: PPTX file blob

**Acceptance Criteria**:
- [ ] Preview shows slide outline
- [ ] Download button triggers PPTX generation
- [ ] File downloads with name `InsiderThreatProgram-[OrgName]-[Date].pptx`
- [ ] File opens correctly in PowerPoint/Google Slides

#### Task 2.6: Save PPTX Generation History

**Storage**: `/data/pptx-history.json`

**Schema**:
```json
{
  "accountId": "user-123",
  "generatedAt": "2025-11-02T14:30:00Z",
  "config": { ... },
  "fileName": "InsiderThreatProgram-Acme-2025-11-02.pptx",
  "downloaded": true
}
```

**Acceptance Criteria**:
- [ ] Each generation logged to JSON
- [ ] User can view history of generated PPTXs
- [ ] User can re-download previous PPTXs

### Sprint 2 Deliverables

**Features**:
- ✅ PPTX customization form
- ✅ PPTX generation (8 sections)
- ✅ Download & preview
- ✅ Generation history

**Components**:
- `PptxCustomizer.tsx`, `PptxPreview.tsx`

**APIs**:
- `POST /api/onboarding/generate-pptx`

**Data**:
- `/data/pptx-history.json`

**Success Criteria**:
- [ ] User can generate PPTX end-to-end
- [ ] PPTX contains all 8 sections with personalized content
- [ ] File downloads correctly
- [ ] No errors in PPTX generation

---

## Sprint 3: Epic 2 - Quick Wins (AI Policy Gap Analysis)

**Goal**: Implement AI-powered policy gap analysis (pre-DLP value)
**Story Points**: 23 (9 stories from Epic 2, subset)
**Dependencies**: Sprint 2 (uses account system)
**Parallel Execution**: No (critical path)
**Estimated Duration**: Agent works till complete

### User Stories

**US-2.1**: Upload Existing Policies (5 points)
**US-2.2**: Run AI Gap Analysis (8 points)
**US-2.3**: View Gap Report (5 points)
**US-2.4**: Understand Policy Recommendations (3 points)
**US-2.5**: Export Gap Report (2 points)

### Tasks

#### Task 3.1: Build Policy Upload UI

**Component**: `/components/quick-wins/PolicyUploader.tsx`

**Features**:
- File upload (PDF, DOCX, TXT)
- Multiple file support (drag & drop)
- File list with remove option
- "Analyze Policies" button

**Page**: `/app/quick-wins/ai-gap/page.tsx`

**Acceptance Criteria**:
- [ ] User can upload files (PDF, DOCX, TXT)
- [ ] Files displayed in list
- [ ] Files removable before analysis

#### Task 3.2: Extract Text from Uploaded Files

**Library**: `pdf-parse` (PDF), `mammoth` (DOCX)

```bash
npm install pdf-parse mammoth
```

**Function**: `/lib/quick-wins/extract-text.ts`

**Acceptance Criteria**:
- [ ] Extracts text from PDF
- [ ] Extracts text from DOCX
- [ ] Handles plain text files
- [ ] Returns combined text corpus

#### Task 3.3: Implement AI Gap Analysis (Mock for Demo)

**File**: `/lib/quick-wins/ai-gap-analysis.ts`

**For Demo** (no actual AI):
- Use keyword matching for gap detection
- Predefined gap categories:
  1. Data Classification
  2. Access Controls
  3. Monitoring & Logging
  4. Incident Response
  5. Employee Training
  6. Third-Party Risk
  7. Acceptable Use
  8. Remote Work

**Logic**:
```typescript
const gapDetection = {
  'Data Classification': {
    keywords: ['classification', 'confidential', 'pii', 'sensitive'],
    required: true,
    severity: 'High'
  },
  'Access Controls': {
    keywords: ['access control', 'least privilege', 'role-based'],
    required: true,
    severity: 'High'
  },
  // ... more categories
}

// If keyword NOT found in policy text → Gap detected
```

**Acceptance Criteria**:
- [ ] Analyzes text for 8 gap categories
- [ ] Returns gap report with findings
- [ ] Each gap includes: category, severity, recommendation

#### Task 3.4: Build Gap Report UI

**Component**: `/components/quick-wins/GapReport.tsx`

**Layout**:
- Summary: "X gaps found across Y categories"
- Severity breakdown: High (X), Medium (Y), Low (Z)
- Gap cards (expandable):
  - Category
  - Severity
  - Finding ("Your policy does not mention...")
  - Recommendation ("Add section on...")
  - Sample policy text (example)
- Export buttons (PDF, Word)

**Acceptance Criteria**:
- [ ] Report renders all gaps
- [ ] Gaps color-coded by severity
- [ ] Recommendations actionable
- [ ] Export buttons work (JSON for MVP)

#### Task 3.5: Save Analysis to JSON

**API Endpoint**: `/app/api/quick-wins/ai-gap/route.ts`

**POST** `/api/quick-wins/ai-gap`:
```json
{
  "accountId": "user-123",
  "files": ["policy1.pdf", "policy2.docx"],
  "analyzedAt": "2025-11-02T16:00:00Z",
  "gaps": [
    {
      "category": "Data Classification",
      "severity": "High",
      "finding": "No mention of data classification scheme",
      "recommendation": "Add data classification policy (Public, Internal, Confidential, Restricted)"
    },
    // ... more gaps
  ],
  "summary": {
    "totalGaps": 12,
    "high": 4,
    "medium": 6,
    "low": 2
  }
}
```

**Storage**: `/data/ai-policy-gaps.json`

**Acceptance Criteria**:
- [ ] Analysis saved to JSON
- [ ] User can retrieve past analyses
- [ ] History viewable in UI

### Sprint 3 Deliverables

**Features**:
- ✅ Policy file upload (PDF, DOCX, TXT)
- ✅ AI gap analysis (keyword-based mock)
- ✅ Gap report with findings and recommendations
- ✅ Export functionality (JSON MVP)

**Components**:
- `PolicyUploader.tsx`, `GapReport.tsx`

**APIs**:
- `POST /api/quick-wins/ai-gap`

**Data**:
- `/data/ai-policy-gaps.json`

**Success Criteria**:
- [ ] User can upload policies and run analysis
- [ ] Gap report generated with actionable recommendations
- [ ] Analysis saved and retrievable
- [ ] No errors in file processing

---

## PARALLELIZATION CHECKPOINT

**After Sprint 3, the following sprints can run in PARALLEL**:

### Parallel Group 1 (3 concurrent agents)

- **Agent A**: Sprint 4 (Dashboard - Zero Incident)
- **Agent B**: Sprint 5 (Quick Wins - HR Integration & Incident Logging)
- **Agent C**: Sprint 7 (Demo Mode Infrastructure)

**Why Parallel**: These features have no direct dependencies on each other. They all depend on Sprint 0-3 (foundation + account system), but not on each other.

**Orchestrator Action**: Launch 3 agents simultaneously with clear task definitions.

---

## Sprint 4: Epic 3 - Dashboard (Zero-Incident Mode)

**Goal**: Build adaptive dashboard for organizations with ZERO incidents
**Story Points**: 12 (4 stories from Epic 3, subset)
**Dependencies**: Sprint 3 (account system, demo mode infrastructure from Sprint 7 will integrate later)
**Parallel Execution**: YES (runs alongside Sprint 5, Sprint 7)
**Estimated Duration**: Agent works till complete

### User Stories

**US-3.1**: View Zero-Incident Dashboard (5 points)
**US-3.2**: See "Getting Started" Guidance (3 points)
**US-3.3**: Track Initial Setup Progress (2 points)
**US-3.4**: Understand When to Advance to Next Phase (2 points)

### Tasks

#### Task 4.1: Design Zero-Incident Dashboard Layout

**Component**: `/components/dashboard/ZeroIncidentDashboard.tsx`

**Layout** (3x3 grid):
```
┌─────────────────┬─────────────────┬─────────────────┐
│ Welcome Widget  │ Setup Progress  │ Next Steps      │
│ (2x2)           │ (1x2)           │ (1x2)           │
├─────────────────┼─────────────────┴─────────────────┤
│ Policy Status   │ Training Status                   │
│ (1x1)           │ (2x1)                             │
├─────────────────┼─────────────────┬─────────────────┤
│ AI Gap Analysis │ Priority Picker │ Generate PPTX   │
│ (1x1)           │ (1x1)           │ (1x1)           │
└─────────────────┴─────────────────┴─────────────────┘
```

**Widgets**:
1. **Welcome Widget**: "Welcome to Your Insider Threat Program!" + Getting Started checklist
2. **Setup Progress**: Progress bar (0-100%) based on completed steps
3. **Next Steps**: Top 3 recommended actions
4. **Policy Status**: "Policies analyzed: X gaps found" (if AI Gap Analysis run)
5. **Training Status**: "Training module: Not yet configured" (placeholder)
6. **Quick Actions**: Links to Priority Picker, PPTX Generator, AI Gap Analysis

**Acceptance Criteria**:
- [ ] Dashboard renders 6 widgets in 3x3 grid
- [ ] Widgets responsive on mobile
- [ ] All links functional

#### Task 4.2: Implement Setup Progress Tracker

**File**: `/lib/dashboard/setup-progress.ts`

**Checklist** (8 steps):
1. ✅ Account created
2. ⬜ Priority Picker completed
3. ⬜ PPTX generated
4. ⬜ AI Gap Analysis run
5. ⬜ Policies uploaded
6. ⬜ Training configured (placeholder)
7. ⬜ First incident logged (placeholder)
8. ⬜ Dashboard reviewed

**Progress Calculation**: `(completed / total) * 100`

**Acceptance Criteria**:
- [ ] Progress tracker reads from user's activity history
- [ ] Progress bar updates in real-time
- [ ] Checkmarks show completed steps

#### Task 4.3: Build "Getting Started" Guidance

**Component**: `/components/dashboard/GettingStartedGuide.tsx`

**Content**:
- "You're starting from zero incidents - that's perfect!"
- "Here's your recommended path:"
  1. Complete Priority Picker (5 min)
  2. Review your top 5 priorities
  3. Generate board approval PPTX (10 min)
  4. Run AI Policy Gap Analysis (15 min)
  5. Share PPTX with leadership
  6. Return here to track progress

**Acceptance Criteria**:
- [ ] Guidance renders in Welcome Widget
- [ ] Steps linked to actual features
- [ ] User can dismiss guidance (don't show again)

#### Task 4.4: Implement "When to Advance" Logic

**Component**: `/components/dashboard/PhaseAdvancement.tsx`

**Logic**:
- If `setupProgress >= 80%` → Show: "You're ready to advance to Month 6 mode!"
- Button: "Switch to Month 6 View" (requires demo mode from Sprint 7)
- For now: Show message only, button disabled

**Acceptance Criteria**:
- [ ] Advancement message shown when progress >= 80%
- [ ] Button placeholder present
- [ ] Message explains what Month 6 mode includes

### Sprint 4 Deliverables

**Features**:
- ✅ Zero-Incident Dashboard (6 widgets)
- ✅ Setup progress tracker
- ✅ Getting Started guidance
- ✅ Phase advancement logic

**Components**:
- `ZeroIncidentDashboard.tsx`, `GettingStartedGuide.tsx`, `PhaseAdvancement.tsx`

**Success Criteria**:
- [ ] Dashboard renders correctly for Month 0 mode
- [ ] Progress tracker updates based on user actions
- [ ] All widgets functional
- [ ] No console errors

---

## Sprint 5: Epic 2 - Quick Wins (HR Integration & Incident Logging)

**Goal**: Add HR risk integration and basic incident logging
**Story Points**: 18 (5 stories from Epic 2, subset)
**Dependencies**: Sprint 3 (account system)
**Parallel Execution**: YES (runs alongside Sprint 4, Sprint 7)
**Estimated Duration**: Agent works till complete

### User Stories

**US-2.6**: Integrate HR Risk Signals (8 points)
**US-2.7**: View HR-Flagged Employees (5 points)
**US-2.8**: Log Basic Incident (3 points)
**US-2.9**: View Incident List (2 points)

### Tasks

#### Task 5.1: Build HR Risk Signal Simulator

**Component**: `/components/quick-wins/HrRiskSimulator.tsx`

**For Demo** (no actual HRIS integration):
- Simulated HR events:
  - Performance Improvement Plan (PIP)
  - Resignation submitted
  - Termination notice
  - Disciplinary action
  - Denied promotion
  - Salary dispute
  - Extended leave

**UI**:
- Table of flagged employees
- Columns: Employee (anonymized), Event Type, Date, Risk Level (Low/Med/High)
- "View Details" button (shows event context)

**Data**: `/data/hr-risk-signals.json` (pre-seeded with 10-15 demo employees)

**Acceptance Criteria**:
- [ ] Table renders HR risk signals
- [ ] Employees anonymized (Employee-001, etc.)
- [ ] Events color-coded by risk level
- [ ] Details panel shows context

#### Task 5.2: Build Basic Incident Logging Form

**Component**: `/components/incidents/BasicIncidentLogger.tsx`

**Simplified Form** (not full Barclays complexity):
- Title (text)
- Description (textarea)
- Category (dropdown: 8 categories)
  - Data Exfiltration
  - Policy Violation
  - Unauthorized Access
  - IP Theft
  - Fraud
  - Sabotage
  - HR-Flagged Behavior
  - Other
- Severity (dropdown: Low, Medium, High)
- Date Occurred (date picker)
- Related Employee (dropdown from HR risk signals, or manual entry)
- Status (auto: "Open")

**Page**: `/app/incidents/new/page.tsx` (simplified version)

**Acceptance Criteria**:
- [ ] Form renders all fields
- [ ] Category dropdown has 8 options
- [ ] Form validates required fields
- [ ] "Submit" saves incident

#### Task 5.3: Save Incidents to JSON

**API Endpoint**: `/app/api/incidents/route.ts`

**POST** `/api/incidents`:
```json
{
  "incidentId": "INC-001",
  "accountId": "user-123",
  "title": "Suspicious file access",
  "description": "Employee accessed files outside normal scope",
  "category": "Unauthorized Access",
  "severity": "Medium",
  "dateOccurred": "2025-10-15",
  "relatedEmployee": "Employee-007",
  "status": "Open",
  "createdAt": "2025-11-02T10:00:00Z",
  "createdBy": "user-123"
}
```

**Storage**: `/data/incidents.json`

**Acceptance Criteria**:
- [ ] Incidents saved to JSON
- [ ] Auto-generated incident ID (INC-001, INC-002, ...)
- [ ] Timestamp recorded

#### Task 5.4: Build Incident List View

**Component**: `/components/incidents/IncidentList.tsx`

**Page**: `/app/incidents/page.tsx`

**Layout**:
- Table with columns: ID, Title, Category, Severity, Status, Date, Actions
- Filters: Category, Severity, Status
- Sort: Date (newest first)
- Actions: View (navigate to details page - placeholder for now)

**Acceptance Criteria**:
- [ ] Table renders all incidents
- [ ] Filters work
- [ ] Sort works
- [ ] Click "View" navigates to `/incidents/[id]` (placeholder page)

### Sprint 5 Deliverables

**Features**:
- ✅ HR risk signal viewer
- ✅ Basic incident logging
- ✅ Incident list view

**Components**:
- `HrRiskSimulator.tsx`, `BasicIncidentLogger.tsx`, `IncidentList.tsx`

**APIs**:
- `POST /api/incidents`
- `GET /api/incidents`

**Data**:
- `/data/hr-risk-signals.json` (pre-seeded)
- `/data/incidents.json` (user-generated)

**Success Criteria**:
- [ ] User can view HR risk signals
- [ ] User can log incidents
- [ ] Incidents viewable in list
- [ ] No errors in incident creation

---

## Sprint 7: Epic 8 - Demo Mode Infrastructure

**Goal**: Build Month 0/6/12 mode switching system
**Story Points**: 14 (3 stories from Epic 8, subset - infrastructure only)
**Dependencies**: Sprint 3 (account system)
**Parallel Execution**: YES (runs alongside Sprint 4, Sprint 5)
**Estimated Duration**: Agent works till complete

### User Stories

**US-8.1**: Switch Between Demo Modes (5 points)
**US-8.2**: See Mode-Specific Features (5 points)
**US-8.3**: Persist Mode Selection (4 points)

### Tasks

#### Task 7.1: Build Mode Switcher UI

**Component**: `/components/demo-mode/ModeSwitcher.tsx`

**UI**:
- Dropdown in top-right header (admin only)
- Options:
  - 🟢 Month 0 - Starting Out
  - 🟡 Month 6 - Early Progress
  - 🟢 Month 12 - Mature Program
- Current mode badge shown
- Switching triggers page reload (to apply visibility rules)

**Acceptance Criteria**:
- [ ] Mode switcher renders in header
- [ ] Only visible to admin users
- [ ] Current mode highlighted
- [ ] Switching updates mode in state

#### Task 7.2: Implement Feature Visibility Logic

**File**: `/lib/demo-mode/feature-visibility.ts`

**Visibility Rules**:

**Month 0** (Zero incidents, just starting):
- ✅ Priority Picker
- ✅ PPTX Generator
- ✅ AI Gap Analysis
- ✅ Zero-Incident Dashboard
- ❌ Early Detection Dashboard
- ❌ Mature Dashboard
- ❌ DLP Integration (mockup)
- ❌ Oversight Features (mockups)

**Month 6** (Early program, some incidents):
- ✅ All Month 0 features
- ✅ Early Detection Dashboard
- ✅ Incident logging & list
- ✅ HR risk signals
- ✅ Rollout Planner
- ❌ Mature Dashboard
- ❌ DLP Integration (mockup)
- ❌ Oversight Features (mockups)

**Month 12** (Mature program, full capability):
- ✅ All features (including mockups)

**Function**: `isFeatureVisible(featureKey: string, mode: string): boolean`

**Acceptance Criteria**:
- [ ] Function checks mode and returns visibility
- [ ] Features hidden/shown based on mode
- [ ] Navigation menu adapts to mode

#### Task 7.3: Update Navigation to Respect Visibility

**File**: `/components/navigation/Sidebar.tsx`

**Logic**:
- Read current demo mode from state
- For each nav item, check `isFeatureVisible(item.featureKey, currentMode)`
- Hide nav items not visible in current mode
- Show badge on items: "Available in Month 6+" if hidden

**Acceptance Criteria**:
- [ ] Nav items hidden based on mode
- [ ] Badges show when features unlock
- [ ] Switching mode updates nav immediately

#### Task 7.4: Persist Mode Selection

**API Endpoint**: `/app/api/demo-mode/route.ts`

**POST** `/api/demo-mode`:
```json
{
  "accountId": "user-123",
  "mode": "month-6"
}
```

**Storage**: Update account record in `/data/accounts.json`

**Acceptance Criteria**:
- [ ] Mode saved to account record
- [ ] Mode persists across sessions
- [ ] On login, user sees last selected mode

### Sprint 7 Deliverables

**Features**:
- ✅ Demo mode switcher (Month 0/6/12)
- ✅ Feature visibility logic
- ✅ Navigation adaptation
- ✅ Mode persistence

**Components**:
- `ModeSwitcher.tsx`

**Utilities**:
- `feature-visibility.ts`

**APIs**:
- `POST /api/demo-mode`
- `GET /api/demo-mode`

**Success Criteria**:
- [ ] User can switch between modes
- [ ] Features show/hide based on mode
- [ ] Mode persists across sessions
- [ ] No errors in mode switching

---

## CONVERGENCE CHECKPOINT

**After Sprints 4, 5, 7 complete, proceed sequentially:**

---

## Sprint 6: Epic 3 - Dashboard (Early Detection & Mature Mockups)

**Goal**: Build Early Detection Dashboard + Mature Dashboard mockups
**Story Points**: 22 (8 stories from Epic 3, remaining)
**Dependencies**: Sprint 4 (Zero-Incident Dashboard), Sprint 7 (Demo Mode)
**Parallel Execution**: No (requires Sprint 4 & 7 complete)
**Estimated Duration**: Agent works till complete

### User Stories

**US-3.5**: View Early Detection Dashboard (5 points)
**US-3.6**: See First Incident Metrics (3 points)
**US-3.7**: Track MTTD/MTTR (2 points)
**US-3.8**: View Mature Dashboard (5 points) - MOCKUP
**US-3.9**: See KPI Trends (3 points) - MOCKUP
**US-3.10**: View Analytics (2 points) - MOCKUP
**US-3.11**: See ROI Calculations (2 points) - MOCKUP

### Tasks

#### Task 6.1: Build Early Detection Dashboard

**Component**: `/components/dashboard/EarlyDetectionDashboard.tsx`

**Layout** (Month 6 mode):
```
┌─────────────────┬─────────────────┬─────────────────┐
│ Incident Count  │ MTTD            │ MTTR            │
│ (1x1)           │ (1x1)           │ (1x1)           │
├─────────────────┴─────────────────┴─────────────────┤
│ Recent Incidents Table (3x2)                        │
├─────────────────┬─────────────────┬─────────────────┤
│ Incident Trend  │ Category Breakdown (2x2)          │
│ (1x2)           │                                   │
└─────────────────┴─────────────────┴─────────────────┘
```

**Widgets**:
1. **Incident Count**: Total incidents logged (from `/data/incidents.json`)
2. **MTTD**: Mean Time To Detect (calculated from incident data)
3. **MTTR**: Mean Time To Respond (calculated from incident data)
4. **Recent Incidents**: Last 5 incidents (table)
5. **Incident Trend**: Line chart (last 6 months)
6. **Category Breakdown**: Pie chart (incidents by category)

**Acceptance Criteria**:
- [ ] Dashboard renders for Month 6 mode
- [ ] Metrics calculated from real incident data
- [ ] Charts display correctly
- [ ] Responsive layout

#### Task 6.2: Implement MTTD/MTTR Calculations

**File**: `/lib/dashboard/metrics.ts`

**MTTD** (Mean Time To Detect):
```typescript
// Time from incident occurrence to discovery
MTTD = average(discoveryDate - incidentDate) in days
```

**MTTR** (Mean Time To Respond):
```typescript
// Time from discovery to resolution
MTTR = average(resolvedDate - discoveryDate) in days
```

**Acceptance Criteria**:
- [ ] MTTD calculated correctly
- [ ] MTTR calculated correctly
- [ ] Handles incidents without resolution (show "In Progress")

#### Task 6.3: Build Mature Dashboard (MOCKUP)

**Component**: `/components/dashboard/MatureDashboard.tsx`

**Purpose**: Show what dashboard looks like after 12 months

**Layout** (Month 12 mode):
- Reuse Barclays PoC dashboard components (10 KPI widgets, heatmap, etc.)
- **IMPORTANT**: Use static demo data (no real calculations)
- Add banner: "📊 Preview Mode - Mature Program Dashboard (Month 12+)"

**Mockup Strategy**:
1. Copy Barclays PoC dashboard layout
2. Populate with static JSON data (`/data/metrics.json`)
3. Disable interactivity (charts static, no drill-downs)
4. Add watermark: "Mockup - Available in Month 12"

**Acceptance Criteria**:
- [ ] Dashboard renders with all 10 KPI widgets
- [ ] Data from static JSON file
- [ ] Banner clearly indicates mockup status
- [ ] No errors (even though data is static)

#### Task 6.4: Create Static Demo Data for Mature Dashboard

**File**: `/data/metrics.json`

**Schema**:
```json
{
  "mode": "month-12",
  "kpis": [
    {
      "key": "MTTD",
      "label": "Mean Time To Detect",
      "value": 3.2,
      "unit": "days",
      "trend": "↓ -15%",
      "trendDirection": "down",
      "good": true,
      "history": [5.1, 4.8, 4.2, 3.9, 3.5, 3.2] // 6 months
    },
    // ... 9 more KPIs (MTTR, SAT, FPR, etc.)
  ],
  "charts": {
    "volumeBaseline": [...],
    "detectedVsUndetected": [...],
    "heatmap": [...],
    "roleRisk": [...]
  }
}
```

**Acceptance Criteria**:
- [ ] JSON file created with all 10 KPIs
- [ ] Realistic demo data
- [ ] 6-month historical trends for each KPI

### Sprint 6 Deliverables

**Features**:
- ✅ Early Detection Dashboard (Month 6)
- ✅ MTTD/MTTR calculations
- ✅ Mature Dashboard mockup (Month 12)
- ✅ Static demo data for mature mode

**Components**:
- `EarlyDetectionDashboard.tsx`, `MatureDashboard.tsx`

**Data**:
- `/data/metrics.json` (static demo data)

**Success Criteria**:
- [ ] Early Detection Dashboard shows real data
- [ ] Mature Dashboard mockup renders correctly
- [ ] Mode switching between dashboards works
- [ ] No errors in metric calculations

---

## Sprint 8: Epic 8 - Demo Mode (Data Population & Feature Visibility)

**Goal**: Populate demo data for each mode, implement feature visibility rules
**Story Points**: 21 (4 stories from Epic 8, remaining)
**Dependencies**: Sprint 6 (dashboards), Sprint 7 (demo mode infrastructure)
**Parallel Execution**: No (requires Sprint 6 complete)
**Estimated Duration**: Agent works till complete

### User Stories

**US-8.4**: See Realistic Demo Data per Mode (8 points)
**US-8.5**: Understand Feature Progression (5 points)
**US-8.6**: Preview Higher Maturity Modes (5 points)
**US-8.7**: Reset Demo Data (3 points)

### Tasks

#### Task 8.1: Seed Demo Data for Each Mode

**Month 0 Data** (Zero incidents):
- `/data/incidents.json`: Empty `[]`
- `/data/priority-responses.json`: 1 sample completed quiz
- `/data/ai-policy-gaps.json`: 1 sample gap analysis (12 gaps found)
- `/data/hr-risk-signals.json`: Empty `[]`

**Month 6 Data** (Early program):
- `/data/incidents.json`: 5-10 incidents
- `/data/priority-responses.json`: Same as Month 0
- `/data/ai-policy-gaps.json`: Same as Month 0
- `/data/hr-risk-signals.json`: 3-5 flagged employees
- Calculated metrics: MTTD ~7 days, MTTR ~14 days

**Month 12 Data** (Mature program):
- `/data/incidents.json`: 50+ incidents
- `/data/metrics.json`: Full KPI history (12 months)
- `/data/hr-risk-signals.json`: 10-15 flagged employees
- Calculated metrics: MTTD ~3 days, MTTR ~5 days

**Task**: Create data seeding scripts

**File**: `/scripts/seed-demo-data.ts`

**Acceptance Criteria**:
- [ ] Script seeds data for all 3 modes
- [ ] Data realistic and consistent
- [ ] Can reset to initial state

#### Task 8.2: Implement Feature Progression UI

**Component**: `/components/demo-mode/FeatureProgression.tsx`

**UI**: Modal showing feature unlock timeline

**Content**:
```
Month 0 (Starting Out):
  ✅ Priority Picker
  ✅ PPTX Generator
  ✅ AI Gap Analysis
  ✅ Zero-Incident Dashboard

Month 6 (Early Progress):
  ✅ All Month 0 features
  🆕 Early Detection Dashboard
  🆕 Incident Logging
  🆕 HR Risk Signals
  🆕 Rollout Planner

Month 12 (Mature Program):
  ✅ All Month 6 features
  🆕 Mature Dashboard (full KPIs)
  🆕 DLP Integration
  🆕 Oversight Features
  🆕 Training Module
  🆕 Content Management
```

**Trigger**: "See Feature Roadmap" button in header

**Acceptance Criteria**:
- [ ] Modal shows feature progression
- [ ] Current mode highlighted
- [ ] Future features clearly marked

#### Task 8.3: Implement Mode Preview (Read-Only)

**Feature**: Allow users to "preview" higher modes without switching

**Component**: `/components/demo-mode/ModePreview.tsx`

**Logic**:
- User clicks "Preview Month 12" (from Month 0)
- Dashboard switches to Month 12 mockup
- Banner: "🔒 Preview Mode - Switch to Month 12 to unlock full features"
- All interactions disabled (read-only)
- "Exit Preview" button returns to current mode

**Acceptance Criteria**:
- [ ] User can preview higher modes
- [ ] Preview is read-only
- [ ] Exiting preview returns to original mode
- [ ] Banner clearly indicates preview status

#### Task 8.4: Build Demo Data Reset Tool

**Component**: `/components/admin/DemoDataReset.tsx`

**Feature**: Admin can reset demo data to initial state

**UI**:
- Button: "Reset Demo Data"
- Confirmation modal: "This will erase all demo data. Continue?"
- On confirm: Delete all JSON files, re-seed with defaults

**API Endpoint**: `/app/api/admin/reset-demo/route.ts`

**Acceptance Criteria**:
- [ ] Reset button in admin settings
- [ ] Confirmation required
- [ ] All data reset to defaults
- [ ] User can start fresh

### Sprint 8 Deliverables

**Features**:
- ✅ Demo data seeding for all modes
- ✅ Feature progression UI
- ✅ Mode preview (read-only)
- ✅ Demo data reset tool

**Components**:
- `FeatureProgression.tsx`, `ModePreview.tsx`, `DemoDataReset.tsx`

**Scripts**:
- `seed-demo-data.ts`

**APIs**:
- `POST /api/admin/reset-demo`

**Success Criteria**:
- [ ] All modes have realistic demo data
- [ ] Users can preview higher modes
- [ ] Data reset works correctly
- [ ] No errors in data seeding

---

## SECOND PARALLELIZATION CHECKPOINT

**After Sprint 8, the following sprints can run in PARALLEL**:

### Parallel Group 2 (2 concurrent agents)

- **Agent A**: Sprint 9 (Rollout Planner + Training Mockup)
- **Agent B**: Sprint 10 (DLP/Oversight/Content Mockups)

**Why Parallel**: These are mostly mockup features with no dependencies on each other.

---

## Sprint 9: Epic 4 & 5 - Rollout Planner + Training Mockup

**Goal**: Build Five-Phase Rollout Planner + Training module mockup
**Story Points**: 23 (Epic 4: 21 points, Epic 5: 2 points for mockup)
**Dependencies**: Sprint 8 (demo mode complete)
**Parallel Execution**: YES (runs alongside Sprint 10)
**Estimated Duration**: Agent works till complete

### User Stories

**US-4.1**: View Five-Phase Rollout Plan (8 points)
**US-4.2**: See Phase Checklists (5 points)
**US-4.3**: Track Rollout Progress (5 points)
**US-4.4**: Customize Timeline (3 points)
**US-5.1**: Preview Training Module (2 points) - MOCKUP

### Tasks

#### Task 9.1: Build Five-Phase Rollout Planner UI

**Component**: `/components/rollout/RolloutPlanner.tsx`

**Page**: `/app/rollout-planner/page.tsx`

**Five Phases**:
1. **Foundation** (Month 0-3)
   - Establish program vision
   - Complete Priority Picker
   - Generate board approval
   - Secure executive sponsorship

2. **Quick Wins** (Month 3-6)
   - Run AI Gap Analysis
   - Implement policy improvements
   - Setup HR risk signal monitoring
   - Log first incidents

3. **Detection** (Month 6-9)
   - Deploy DLP (if needed)
   - Integrate with SIEM
   - Setup alerting
   - Establish MTTD/MTTR baselines

4. **Response** (Month 9-12)
   - Create incident response playbooks
   - Train response team
   - Conduct tabletop exercises
   - Refine processes

5. **Governance** (Month 12+)
   - Establish oversight committee
   - Quarterly reviews
   - Continuous improvement
   - Mature metrics & reporting

**UI**: Timeline visualization with expandable phases

**Acceptance Criteria**:
- [ ] All 5 phases displayed in timeline
- [ ] Phases expandable to show details
- [ ] Current phase highlighted based on org's progress

#### Task 9.2: Implement Phase Checklists

**Component**: `/components/rollout/PhaseChecklist.tsx`

**Checklist per Phase** (example for Phase 1):

**Phase 1: Foundation**
- [ ] Complete Priority Picker
- [ ] Generate board approval PPTX
- [ ] Present to leadership
- [ ] Secure budget approval
- [ ] Assign program owner
- [ ] Define success metrics
- [ ] Setup initial governance

**Storage**: `/data/rollout-progress.json`

**Schema**:
```json
{
  "accountId": "user-123",
  "currentPhase": 1,
  "phases": [
    {
      "phase": 1,
      "name": "Foundation",
      "checklist": [
        { "item": "Complete Priority Picker", "completed": true },
        { "item": "Generate PPTX", "completed": true },
        { "item": "Present to leadership", "completed": false },
        // ... more items
      ],
      "progress": 40 // % complete
    },
    // ... 4 more phases
  ]
}
```

**Acceptance Criteria**:
- [ ] Checklists render for all phases
- [ ] Users can check off items
- [ ] Progress saved to JSON
- [ ] Progress bar updates per phase

#### Task 9.3: Build Rollout Progress Tracker

**Component**: `/components/rollout/ProgressTracker.tsx`

**Features**:
- Overall progress: "Phase 1: 40% complete"
- Visual timeline showing current position
- "What's Next" section (next 3 checklist items)
- Estimated completion date (based on progress)

**Acceptance Criteria**:
- [ ] Progress tracker shows current phase
- [ ] Timeline visual updates based on checklist progress
- [ ] "What's Next" shows upcoming items

#### Task 9.4: Implement Timeline Customization

**Component**: `/components/rollout/TimelineCustomizer.tsx`

**Features**:
- Adjust phase durations (default: 3 months each)
- Add custom milestones
- Set target completion date
- Export timeline to PDF (placeholder)

**Acceptance Criteria**:
- [ ] User can adjust phase durations
- [ ] Custom milestones saveable
- [ ] Timeline recalculates based on changes

#### Task 9.5: Create Training Module Mockup

**Component**: `/components/training/TrainingModuleMockup.tsx`

**Page**: `/app/training/page.tsx`

**Mockup Content**:
- Banner: "📚 Preview - Training Module (Available in Full Version)"
- Screenshot/mockup of training interface showing:
  - Training campaign manager
  - Employee completion tracking
  - Quiz builder
  - Certificate generator
- "Contact Sales" CTA

**Acceptance Criteria**:
- [ ] Mockup page renders
- [ ] Banner clearly indicates preview status
- [ ] Links to sales/contact form

### Sprint 9 Deliverables

**Features**:
- ✅ Five-Phase Rollout Planner
- ✅ Phase checklists (interactive)
- ✅ Rollout progress tracker
- ✅ Timeline customization
- ✅ Training module mockup

**Components**:
- `RolloutPlanner.tsx`, `PhaseChecklist.tsx`, `ProgressTracker.tsx`, `TimelineCustomizer.tsx`, `TrainingModuleMockup.tsx`

**Data**:
- `/data/rollout-progress.json`

**Success Criteria**:
- [ ] Rollout planner shows all 5 phases
- [ ] Checklists interactive and persistent
- [ ] Progress tracking functional
- [ ] Training mockup renders

---

## Sprint 10: Epic 6, 7, 9 - Mockups (DLP, Oversight, Content)

**Goal**: Create mockups for DLP integration, Oversight features, Content Management
**Story Points**: 59 (Epic 6: 34 points, Epic 7: 21 points, Epic 9: 4 points)
**Dependencies**: Sprint 8 (demo mode)
**Parallel Execution**: YES (runs alongside Sprint 9)
**Estimated Duration**: Agent works till complete

### User Stories

**Epic 6** (DLP Integration - 3 mockups):
- US-6.1: Preview DLP Dashboard (mockup)
- US-6.2: Preview DLP Policy Builder (mockup)
- US-6.3: Preview DLP Incident Correlation (mockup)

**Epic 7** (Oversight Features - 21 mockups):
- All 6 features from Barclays PoC (adapted as mockups)

**Epic 9** (Content Management - 1 mockup):
- US-9.1: Preview Industry Pack Switcher (mockup)

### Tasks

#### Task 10.1: Create DLP Integration Mockups (3 screens)

**Strategy**: Reuse Barclays PoC DLP components as read-only mockups

**Components**:
- `/components/mockups/DlpDashboardMockup.tsx`
- `/components/mockups/DlpPolicyBuilderMockup.tsx`
- `/components/mockups/DlpIncidentCorrelationMockup.tsx`

**Page**: `/app/mockups/dlp/page.tsx`

**Content per Mockup**:
1. **DLP Dashboard**: Shows static Purview integration status, policy coverage, incident stats
2. **Policy Builder**: Shows UI for creating DLP policies (disabled inputs)
3. **Incident Correlation**: Shows how DLP events link to incidents (static data)

**Banner**: "🔒 Preview - DLP Integration (Available with Microsoft Purview or 3rd-party DLP)"

**Acceptance Criteria**:
- [ ] All 3 DLP mockups render
- [ ] Static demo data displayed
- [ ] Interactions disabled
- [ ] "Contact Sales" CTA present

#### Task 10.2: Create Oversight Features Mockups (6 features)

**Strategy**: Copy Barclays PoC Oversight components, make read-only with static data

**Features to Mock** (from Barclays PoC):
1. **KPI Widgets** (10 widgets) - Already done in Sprint 6 Mature Dashboard
2. **Insider Threat Heatmap** (geographic + dept risk)
3. **Threat Intelligence Feed** (IntelMarquee)
4. **Role Risk Analysis** (Sankey diagram)
5. **Framework Baseline** (compliance tracking)
6. **Trend Analytics** (detected vs undetected)

**Page**: `/app/mockups/oversight/page.tsx`

**Tabs**:
- Heatmap
- Intelligence
- Role Risk
- Framework
- Trends

**Acceptance Criteria**:
- [ ] All 6 Oversight mockups render in tabbed interface
- [ ] Static data from Barclays PoC reused
- [ ] Banner indicates preview status
- [ ] No interactive features (read-only)

#### Task 10.3: Create Industry Pack Switcher Mockup

**Component**: `/components/mockups/IndustryPackSwitcher.tsx`

**Page**: `/app/mockups/content/page.tsx`

**Mockup Content**:
- Dropdown: Select Industry (Financial, Healthcare, Tech, Govt, Retail)
- Preview of content that changes:
  - Incident categories (industry-specific)
  - Policy templates (industry-specific)
  - Benchmarks (industry-specific)
  - Regulatory requirements (industry-specific)
- Before/After comparison showing Financial vs. Healthcare

**Banner**: "🎨 Preview - Industry Content Packs (Contact for custom industry packs)"

**Acceptance Criteria**:
- [ ] Mockup renders industry switcher
- [ ] Shows before/after comparison
- [ ] Static content only
- [ ] CTA for custom packs

#### Task 10.4: Organize All Mockups in Navigation

**Update**: `/components/navigation/Sidebar.tsx`

**New Section**: "Preview Features" (collapsed by default)
- DLP Integration
- Oversight Features
- Training Module
- Industry Content Packs

**Badge**: "🔒 Preview Only" next to each item

**Acceptance Criteria**:
- [ ] All mockups accessible from nav
- [ ] Clearly marked as previews
- [ ] Only visible in Month 12 mode

### Sprint 10 Deliverables

**Features**:
- ✅ DLP Integration mockups (3 screens)
- ✅ Oversight Features mockups (6 features)
- ✅ Industry Pack Switcher mockup
- ✅ Mockup navigation section

**Components**:
- 10+ mockup components (DLP, Oversight, Content)

**Pages**:
- `/app/mockups/dlp/page.tsx`
- `/app/mockups/oversight/page.tsx`
- `/app/mockups/content/page.tsx`

**Success Criteria**:
- [ ] All mockups render correctly
- [ ] Static data used throughout
- [ ] Clear preview banners on all mockups
- [ ] Navigation organized

---

## FINAL INTEGRATION

**After Sprints 9 & 10 complete:**

### Final Integration Tasks

#### Integration Task 1: End-to-End Testing
- [ ] Test all user flows (Priority Picker → PPTX → Dashboard)
- [ ] Test demo mode switching (Month 0 → 6 → 12)
- [ ] Test all mockups accessible
- [ ] Test data persistence across sessions

#### Integration Task 2: Polish & Bug Fixes
- [ ] Fix any console errors
- [ ] Ensure responsive design on mobile
- [ ] Test accessibility (keyboard navigation, screen readers)
- [ ] Optimize performance (lazy loading, code splitting)

#### Integration Task 3: Documentation
- [ ] Update README with feature list
- [ ] Document demo mode usage
- [ ] Create deployment guide
- [ ] Write user onboarding guide

#### Integration Task 4: Deployment Preparation
- [ ] Environment variables setup
- [ ] Build verification (`npm run build`)
- [ ] Vercel deployment (if applicable)
- [ ] Domain configuration

**Success Criteria**:
- [ ] All features functional
- [ ] No console errors or warnings
- [ ] All tests pass
- [ ] Documentation complete
- [ ] Ready for demo/deployment

---

## Summary: Sprint Execution Order for BMAD Orchestrator

### Sequential Execution (Must Run in Order)

1. **Sprint 0**: Foundation (clone, cleanup, infrastructure)
2. **Sprint 1**: Priority Picker
3. **Sprint 2**: PPTX Generator
4. **Sprint 3**: AI Gap Analysis

### Parallel Group 1 (After Sprint 3)

- **Agent A**: Sprint 4 (Dashboard - Zero Incident)
- **Agent B**: Sprint 5 (Quick Wins - HR & Incidents)
- **Agent C**: Sprint 7 (Demo Mode Infrastructure)

### Sequential (After Parallel Group 1)

5. **Sprint 6**: Dashboard (Early Detection & Mature Mockups)
6. **Sprint 8**: Demo Mode (Data Population & Visibility)

### Parallel Group 2 (After Sprint 8)

- **Agent A**: Sprint 9 (Rollout Planner + Training Mockup)
- **Agent B**: Sprint 10 (DLP/Oversight/Content Mockups)

### Final Integration (After All Sprints)

7. **Integration**: Testing, polish, deployment

---

## BMAD Orchestrator Instructions

### For Sequential Sprints (0-3, 6, 8)

```yaml
task:
  name: "Sprint X - [Goal]"
  dependencies: ["sprint-X-1"]  # Previous sprint(s)
  agent: "claude-code"
  instructions: |
    Execute Sprint X as defined in /docs/sprint-backlog.md
    - Complete all tasks in order
    - Mark todo items as you progress
    - Run tests after each task
    - Create deliverables as specified
    - Report completion with summary
```

### For Parallel Group 1 (Sprints 4, 5, 7)

```yaml
parallel_group_1:
  - task:
      name: "Sprint 4 - Dashboard Zero Incident"
      dependencies: ["sprint-3"]
      agent: "claude-code-agent-a"
      instructions: "Execute Sprint 4 per sprint-backlog.md"

  - task:
      name: "Sprint 5 - Quick Wins HR & Incidents"
      dependencies: ["sprint-3"]
      agent: "claude-code-agent-b"
      instructions: "Execute Sprint 5 per sprint-backlog.md"

  - task:
      name: "Sprint 7 - Demo Mode Infrastructure"
      dependencies: ["sprint-3"]
      agent: "claude-code-agent-c"
      instructions: "Execute Sprint 7 per sprint-backlog.md"
```

### For Parallel Group 2 (Sprints 9, 10)

```yaml
parallel_group_2:
  - task:
      name: "Sprint 9 - Rollout Planner + Training"
      dependencies: ["sprint-8"]
      agent: "claude-code-agent-a"
      instructions: "Execute Sprint 9 per sprint-backlog.md"

  - task:
      name: "Sprint 10 - Mockups (DLP/Oversight/Content)"
      dependencies: ["sprint-8"]
      agent: "claude-code-agent-b"
      instructions: "Execute Sprint 10 per sprint-backlog.md"
```

---

## Story Point Summary by Sprint

| Sprint | Goal | Story Points | Dependencies | Parallel? |
|--------|------|--------------|--------------|-----------|
| 0 | Foundation | N/A | None | No |
| 1 | Priority Picker | 17 | Sprint 0 | No |
| 2 | PPTX Generator | 17 | Sprint 1 | No |
| 3 | AI Gap Analysis | 23 | Sprint 2 | No |
| 4 | Dashboard (Zero) | 12 | Sprint 3 | **Yes** (with 5, 7) |
| 5 | Quick Wins (HR) | 18 | Sprint 3 | **Yes** (with 4, 7) |
| 7 | Demo Mode Infra | 14 | Sprint 3 | **Yes** (with 4, 5) |
| 6 | Dashboard (Early + Mature) | 22 | Sprints 4, 7 | No |
| 8 | Demo Mode (Data) | 21 | Sprint 6 | No |
| 9 | Rollout + Training | 23 | Sprint 8 | **Yes** (with 10) |
| 10 | Mockups (DLP/Oversight) | 59 | Sprint 8 | **Yes** (with 9) |
| **Total** | | **~226** | | |

**Note**: Sprint 0 has no story points (infrastructure setup).

---

## Final Deliverables

**End of Sprint 10 + Integration**:

✅ **60 Demo Stories Implemented** (38 functional + 22 mockups)

✅ **10 Features Delivered**:
1. Priority Picker (10-question decision tree)
2. Program Approval PPTX Generator (8 sections)
3. Five-Phase Rollout Planner (interactive checklists)
4. Quick Win Features (AI Gap Analysis, HR signals, incident logging)
5. Adaptive Dashboard (Zero-Incident, Early Detection, Mature mockup)
6. Demo Mode System (Month 0/6/12 switching)
7. Training Module (mockup)
8. DLP Integration (mockups - 3 screens)
9. Oversight Features (mockups - 6 features from Barclays PoC)
10. Content Management (Industry Pack Switcher mockup)

✅ **Technical Deliverables**:
- Cloned & refactored Barclays PoC codebase
- JSON file storage (7 data files)
- Demo mode infrastructure
- Feature visibility system
- 20+ new React components
- 10+ API endpoints
- Comprehensive documentation

✅ **Documentation**:
- README.md (updated)
- CLEANUP_REPORT.md
- JSON_STORAGE_SCHEMA.md
- DEMO_MODE_ARCHITECTURE.md
- User onboarding guide

---

**End of Sprint Backlog**

**Last Updated**: 2025-11-02
**Status**: Ready for BMAD Orchestration Execution

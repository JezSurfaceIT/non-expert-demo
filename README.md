# Non-Expert Insider Threat Demo Platform

**Project Status**: Requirements Complete - Ready for Implementation
**Date**: 2025-10-31
**Session Type**: Co-Elicitation Requirements Gathering

---

## Overview

This repository contains comprehensive requirements documentation for an insider threat platform designed specifically for organizations **starting their programs from zero**. Unlike traditional solutions that require historical incident data, this platform guides organizations through the complete journey from program approval to operational maturity.

**Key Innovation**: Demonstrates value through program maturity, policy coverage, and risk reduction targets rather than incident metrics - solving the chicken-and-egg problem of establishing insider threat programs.

---

## Documentation Structure

### 📋 [EXECUTIVE-SUMMARY.md](./EXECUTIVE-SUMMARY.md)
**Start Here** - High-level overview for decision makers

- **What**: Demo + Educational + Sales platform hybrid
- **Why**: Market gap for organizations starting from zero
- **Investment**: $1.15M-$1.44M (40 weeks development)
- **ROI**: 161% Year 1, 260% Year 2, 316% Year 3
- **Recommendation**: PROCEED with Phase 1 MVP

**Target Audience**: Executives, investors, senior stakeholders

---

### 📘 [PROJECT-BRIEF.md](./PROJECT-BRIEF.md)
**Context & Vision** - Complete project context and strategy

**Contents**:
- Business context and triggers
- Target user personas (CISO, CRO, IT Manager)
- Core features overview (10 major features)
- Value proposition evolution (Month 0 → Month 12)
- Competitive differentiation
- Success metrics
- Risk management

**Target Audience**: Product managers, project sponsors, business analysts

---

### 🔧 [FEATURE-REQUIREMENTS.md](./FEATURE-REQUIREMENTS.md)
**Detailed Specifications** - Complete functional & non-functional requirements

**Contents**:
- 10 major features fully specified
- 50+ discrete functional requirements (FR-XXX-###)
- Non-functional requirements (NFR-XXX-###)
- Acceptance criteria for all features
- User stories
- Technical constraints
- Integration points

**Target Audience**: Engineering teams, QA, architects

**Key Features Documented**:
1. Priority Picker (10-question decision tree)
2. Program Approval PPTX Generator
3. Five-Phase Rollout Planner
4. Quick Win Features (AI Gap Analysis + 3 human channels)
5. Dashboard & Metrics (adaptive, zero-incident to mature)
6. Training & Awareness Module
7. Adapted Oversight Features (from Barclays PoC)
8. DLP Integration (Purview + vendor)
9. Demo Mode System (flexible Month 0/6/12 views)
10. Content Management (industry-swappable)

---

### 🗺️ [IMPLEMENTATION-ROADMAP.md](./IMPLEMENTATION-ROADMAP.md)
**Execution Plan** - Sprint-by-sprint implementation strategy

**Contents**:
- 40-week roadmap (3 phases)
- Sprint planning (20 sprints total)
- Budget breakdown by phase
- Team composition (5-7 FTEs)
- Risk management & mitigation
- Go/No-Go decision points
- Post-launch roadmap (v1.3, v1.4, v2.0)

**Target Audience**: Engineering managers, project managers, CTOs

**Timeline Summary**:
- **Phase 1 (Weeks 1-12)**: MVP - $187k-$250k
- **Phase 2 (Weeks 13-24)**: Demo Enhancement - $183k-$243k
- **Phase 3 (Weeks 25-40)**: Full Capability - $325k-$435k

---

### 📝 [session-notes-2025-10-31-153500-analyst-co-elicitation.md](./session-notes-2025-10-31-153500-analyst-co-elicitation.md)
**Raw Session Notes** - Verbatim co-elicitation conversation

**Contents**:
- Complete Q&A (Q1-Q16)
- User statements (verbatim)
- Insights and analysis
- Requirements as they emerged
- Decision rationale
- 1,191 lines of detailed notes

**Target Audience**: Researchers, requirements tracers, auditors

---

## Quick Start

### For Decision Makers
1. Read [EXECUTIVE-SUMMARY.md](./EXECUTIVE-SUMMARY.md) (15 min)
2. Review investment and ROI sections
3. Make Go/No-Go decision on Phase 1 MVP

### For Product Managers
1. Read [PROJECT-BRIEF.md](./PROJECT-BRIEF.md) (30 min)
2. Understand user personas and value proposition
3. Review success metrics

### For Engineering Teams
1. Read [FEATURE-REQUIREMENTS.md](./FEATURE-REQUIREMENTS.md) (60 min)
2. Review [IMPLEMENTATION-ROADMAP.md](./IMPLEMENTATION-ROADMAP.md) (30 min)
3. Estimate effort for Sprint 1-2
4. Propose technical architecture

### For Complete Context
1. Read all documents in order listed above
2. Reference [session-notes](./session-notes-2025-10-31-153500-analyst-co-elicitation.md) for requirement origins
3. Prepare clarifying questions

---

## Key Insights

### 1. The Chicken-and-Egg Problem
**Traditional approach**: "Show me your incident data, and I'll help you manage it"
**Our approach**: "You have no incidents because you have no program - let's establish one"

### 2. Value Without Incidents
**Dashboard evolution**:
- **Months 0-4**: Program maturity, policy coverage, training completion
- **Months 4-7**: First incidents (3-5), source breakdown, early MTTD/MTTR
- **Months 8-12**: Full KPIs, trends, predictive analytics

### 3. The Purview Surprise
Many organizations have Microsoft 365 E5/A5 licenses but don't know they include **FREE** DLP (Purview). Priority Picker detects this and saves them $15k-$25k in procurement costs.

### 4. AI as Signature Feature
AI Policy Gap Analysis provides **immediate value** (60 seconds to analyze policies) and demonstrates platform intelligence. No competitor offers this.

### 5. Demo Flexibility = Sales Success
Demo Mode System allows sales teams to jump to any maturity stage (Month 0/6/12) and show relevant features. Critical for diverse buyer journeys.

---

## Target Audience Profile

### Organizational Characteristics
- **Size**: 100-5,000 employees
- **Security Team**: 0-5 people (no dedicated insider threat staff)
- **Budget**: <$150k/year for insider threat tools
- **Incident History**: None (or not tracked)
- **Sophistication**: Basic to Intermediate

### Stakeholders
- **Primary**: CISO, Chief Risk Officer, IT Manager
- **Secondary**: Board Members, Compliance Officers, HR Directors
- **End Users**: Security analysts, IT staff, employees (training), managers (reporting)

### Triggers
1. Near-miss incident that wasn't caught
2. Audit finding or compliance gap
3. Board/executive mandate
4. Competitive pressure (peers have programs)
5. New awareness of insider threat risk

---

## Technology Stack (Proposed)

### Frontend
- React 18 / Next.js 14 (reuse from Barclays PoC)
- TypeScript
- Tailwind CSS / shadcn/ui
- Chart.js / D3.js (visualizations)

### Backend
- Node.js / Express (or Next.js API routes)
- PostgreSQL (database)
- Redis (caching, queues)

### AI/ML
- OpenAI GPT-4 API (policy gap analysis)
- LangChain (orchestration)
- Vector database (policy embeddings)

### Integrations
- Microsoft Graph API (O365, Purview)
- SendGrid / AWS SES (email)
- HRIS APIs (Workday, BambooHR, etc.)

### Infrastructure
- AWS / Azure / GCP (cloud hosting)
- Docker / Kubernetes (containerization)
- GitHub Actions (CI/CD)
- Vercel (frontend hosting - optional)

---

## Success Metrics Summary

### Development (Weeks 1-40)
- Sprint velocity: 20-30 story points/sprint
- Code coverage: >80%
- Sprint goal achievement: >90%
- Security vulnerabilities: 0 critical at launch

### Adoption (Months 1-6 post-launch)
- Priority Picker completion: >90%
- PPTX download rate: >80%
- AI Gap Analysis usage: >70%
- Demo-to-engagement conversion: >40%

### Business (Year 1)
- Customers: 100-500 (conservative to aggressive)
- ARR: $1.2M-$9M
- Retention: >75%
- NPS: >50

### Client Success
- Program approval: >70% within 30 days
- DLP on time: >80% (Month 4 target)
- Training completion: >80%
- Time to first incident: <7 months

---

## Next Steps

### Immediate (Week 1)
1. ✅ **Secure Budget Approval** - Review EXECUTIVE-SUMMARY.md with stakeholders
2. ⬜ **Assemble Core Team** - Recruit 5 FTEs (engineering lead, devs, AI engineer, UX, PM)
3. ⬜ **Set Up Infrastructure** - Cloud environment, CI/CD, project tools
4. ⬜ **Market Validation** - Interview 10-20 target users
5. ⬜ **Finalize MVP Scope** - Lock P0 features for Sprint 1-6

### 30 Days
- [ ] Team onboarded
- [ ] Sprint 1 completed
- [ ] Priority Picker mockups approved
- [ ] AI policy analysis POC working
- [ ] 5 pilot customers engaged

### 90 Days (MVP Release)
- [ ] All MVP features complete
- [ ] Pilot customer demos (>4/5 satisfaction)
- [ ] Sales team trained
- [ ] MVP in production
- [ ] Go/No-Go decision for Phase 2

---

## Questions & Contact

### Common Questions

**Q: Why 40 weeks? Can we go faster?**
A: 40 weeks includes MVP (12), Demo Enhancement (12), Full Capability (16). You can launch MVP-only at Week 12 and iterate based on feedback.

**Q: Can we build this with fewer people?**
A: MVP could be built with 3 FTEs in 16-20 weeks, but quality and features would be reduced. 5 FTEs at 12 weeks is optimal for quality MVP.

**Q: What if GPT-4 API is too expensive?**
A: We estimate $2k-$5k for development, $500-$1k/month in production. Alternative: Use GPT-3.5-turbo (70% cheaper) or open-source models (Llama, Mistral).

**Q: How do we validate market demand?**
A: Interview 10-20 CISOs/Risk Officers from target orgs, present Priority Picker + PPTX concept, measure interest (>70% positive = proceed).

**Q: What about GDPR/privacy concerns?**
A: Platform designed for privacy: encrypted data, role-based access, HR flag restrictions, no employee PII required for most features. Legal review recommended.

---

## Repository Structure

```
non-Insider-Treat-orgs/
├── README.md                                      (this file)
├── EXECUTIVE-SUMMARY.md                           (decision maker overview)
├── PROJECT-BRIEF.md                               (complete project context)
├── FEATURE-REQUIREMENTS.md                        (detailed specifications)
├── IMPLEMENTATION-ROADMAP.md                      (execution plan)
└── session-notes-2025-10-31-153500-analyst-co-elicitation.md (raw notes)
```

---

## Credits

**Co-Elicitation Session**: 2025-10-31, ~90 minutes
**Analyst**: Mary (Business Analyst AI Agent)
**Participant**: Jez
**Source Inspiration**: Barclays-PoC-on-Vercel (mature insider threat platform)

**Methodology**: Freeform co-elicitation conversation (Q1-Q16) with real-time verbatim documentation, followed by comprehensive deliverable generation.

---

## License

**Status**: Private - Requirements documentation for internal use
**Intended Use**: Product development planning and stakeholder communication

---

## Document Statistics

- **Total Lines**: 4,000+ across all documents
- **Features Specified**: 10 major features, 50+ discrete capabilities
- **Functional Requirements**: 100+ (FR-XXX-###)
- **Non-Functional Requirements**: 30+ (NFR-XXX-###)
- **User Stories**: 40+
- **Acceptance Criteria**: 200+ discrete checks
- **Sprint Plans**: 20 sprints detailed
- **Budget Estimates**: 3 phases, complete breakdown

**Completeness**: ✅ Ready for implementation planning

---

**Last Updated**: 2025-10-31
**Status**: Requirements Complete - Awaiting Go/No-Go Decision


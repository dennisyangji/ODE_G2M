# ODE Pricing Strategy

## Overview

ODE employs a hybrid pricing model combining subscription tiers with usage-based components (AI tokens, compute hours, storage). This structure supports both PLG self-serve users and SLG enterprise buyers while achieving a blended ARPU of $3,500/year across 280 paid users.

**Revenue Composition per User (Blended):**
- Subscription: 35% ($1,225/yr)
- AI Tokens: 30% ($1,050/yr)
- Compute: 25% ($875/yr)
- Storage: 10% ($350/yr)
- **Total Blended ARPU: $3,500/yr**

---

## Pricing Tiers

### Tier 1: Free ($0/month)

**Target Segment:** Students, hobbyists, evaluation users, indie engineers exploring the platform.

| Feature | Limit |
|---------|-------|
| CAD Modeling | Basic 3D modeling, 10 active projects |
| Simulation | Linear static FEA only |
| AI Assistant | 500 tokens/day (~10 queries) |
| Compute | 2 CPU-hours/month, no GPU |
| Storage | 1 GB |
| Collaboration | View-only sharing links |
| Export | ODE native format only |
| Support | Community forum |

**Purpose:** Top-of-funnel acquisition. Demonstrate core value, create habit, generate upgrade demand when users hit limits. No credit card required.

**Conversion Target:** 5-8% to paid within 90 days.

---

### Tier 2: Starter ($49/month, billed monthly | $39/month, billed annually)

**Target Segment:** Indie engineers, freelancers, small hardware startups (1-3 engineers).

| Feature | Limit |
|---------|-------|
| CAD Modeling | Full 3D modeling, 50 active projects |
| Simulation | Linear + nonlinear FEA, basic thermal |
| AI Assistant | 10,000 tokens/day (~200 queries) |
| Compute | 20 CPU-hours/month included, GPU available at usage rate |
| Storage | 25 GB |
| Collaboration | Share with up to 3 collaborators |
| Export | STEP, STL, IGES, PDF reports |
| Support | Email support (48-hour SLA) |
| MBSE | Basic system diagrams |

**Included Usage Credits:** $15/month in AI tokens + $10/month in compute (overages billed at standard rates).

**Annual Price:** $468/yr (monthly) or $468/yr (annual at $39/mo)

---

### Tier 3: Pro ($99/month, billed monthly | $79/month, billed annually)

**Target Segment:** Professional engineers, consultancies, small teams needing multi-physics.

| Feature | Limit |
|---------|-------|
| CAD Modeling | Full parametric CAD, unlimited projects |
| Simulation | Multi-physics: FEA, CFD, thermal, electromagnetic |
| AI Assistant | 50,000 tokens/day (~1,000 queries) |
| Compute | 100 CPU-hours/month included, 10 GPU-hours included |
| Storage | 100 GB |
| Collaboration | Unlimited collaborators, comment threads |
| Export | All formats including ANSYS, Abaqus, Nastran native |
| Support | Priority email (24-hour SLA), live chat |
| MBSE | Full system modeling, requirements traceability |
| API Access | REST API, Python SDK |
| Version Control | Full simulation history, branching |

**Included Usage Credits:** $40/month in AI tokens + $30/month in compute (overages billed at standard rates).

**Annual Price:** $1,188/yr (monthly) or $948/yr (annual at $79/mo)

---

### Tier 4: Team ($199/seat/month, billed monthly | $159/seat/month, billed annually)

**Target Segment:** Engineering teams at consultancies, mid-market companies, growing startups (5-50 seats).

| Feature | Limit |
|---------|-------|
| CAD Modeling | Full parametric CAD, unlimited projects |
| Simulation | All physics, topology optimization, DOE |
| AI Assistant | Unlimited tokens (fair use policy) |
| Compute | 200 CPU-hours/seat/month, 25 GPU-hours/seat included |
| Storage | 500 GB shared team storage |
| Collaboration | Real-time co-editing, team workspaces |
| Export | All formats, batch export, automated reporting |
| Support | Dedicated CSM, Slack channel, 4-hour SLA |
| MBSE | Full MBSE with SysML integration |
| API Access | Full API, webhooks, CI/CD integration |
| Admin | Team management, role-based access, audit logs |
| SSO | SAML 2.0, OAuth |

**Minimum Seats:** 5

**Included Usage Credits:** $75/seat/month in AI tokens + $50/seat/month in compute.

**Annual Price per Seat:** $2,388/yr (monthly) or $1,908/yr (annual at $159/mo)

---

### Tier 5: Enterprise (Custom Pricing)

**Target Segment:** Enterprise OEMs, large consultancies, government labs (50+ seats).

| Feature | Limit |
|---------|-------|
| CAD Modeling | Unlimited, custom templates, IP protection |
| Simulation | All physics, HPC solvers, custom solver integration |
| AI Assistant | Dedicated AI model instance, fine-tuning on proprietary data |
| Compute | Custom allocation, reserved capacity, burst scaling |
| Storage | Unlimited, data residency options |
| Collaboration | Cross-organization sharing, controlled external access |
| Export | All formats, PLM/PDM integration (Teamcenter, Windchill) |
| Support | Dedicated solutions engineer, 1-hour SLA, on-site training |
| MBSE | Enterprise MBSE, digital twin integration |
| API Access | Full API, custom integrations, on-prem gateway |
| Admin | Enterprise SSO, SCIM provisioning, compliance dashboards |
| Security | SOC 2 Type II, private cloud deployment, encryption at rest |
| SLA | 99.9% uptime guarantee with financial credits |

**Pricing Structure:** Base platform fee ($5K-$25K/month) + per-seat fee ($100-$175/seat/month) + usage.

**Typical ACV:** $50,000 - $500,000+

**Engagement:** Annual or multi-year contracts with volume discounts.

---

## Usage-Based Pricing Components

### AI Token Pricing

AI tokens cover all AI-assisted features: auto-meshing, geometry repair, simulation setup recommendations, results interpretation, design optimization suggestions, and natural language queries.

| Tier | Rate per 1,000 Tokens | Included Monthly Allowance |
|------|----------------------|---------------------------|
| Free | N/A | 500 tokens/day (included) |
| Starter | $0.03 / 1K tokens | $15/month (~500K tokens) |
| Pro | $0.02 / 1K tokens | $40/month (~2M tokens) |
| Team | $0.015 / 1K tokens | $75/seat/month (~5M tokens) |
| Enterprise | $0.01 / 1K tokens | Custom (negotiated) |

**Volume Discounts:**
- 10M+ tokens/month: 15% discount
- 50M+ tokens/month: 25% discount
- 100M+ tokens/month: 35% discount

**Revenue Projection:** Average paid user consumes $87.50/month ($1,050/yr) in AI tokens, representing 30% of blended ARPU.

### Compute Pricing

Compute covers all solver execution, meshing operations, optimization runs, and post-processing on ODE cloud infrastructure.

| Resource | Rate | Notes |
|----------|------|-------|
| CPU Compute | $0.10/hour | Per vCPU-hour |
| GPU Compute (Standard) | $0.35/hour | NVIDIA A10G equivalent |
| GPU Compute (Premium) | $0.50/hour | NVIDIA A100 equivalent |
| HPC Cluster (Enterprise) | Custom | Dedicated multi-node, InfiniBand |

**Included Compute by Tier:**

| Tier | CPU Hours/Month | GPU Hours/Month |
|------|----------------|-----------------|
| Free | 2 | 0 |
| Starter | 20 | 0 (available at $0.35/hr) |
| Pro | 100 | 10 |
| Team | 200/seat | 25/seat |
| Enterprise | Custom | Custom |

**Revenue Projection:** Average paid user consumes $72.92/month ($875/yr) in compute, representing 25% of blended ARPU.

### Storage Pricing

Storage covers project files, simulation results, CAD models, and version history.

| Tier | Included Storage | Overage Rate |
|------|-----------------|--------------|
| Free | 1 GB | N/A (hard limit) |
| Starter | 25 GB | $0.10/GB/month |
| Pro | 100 GB | $0.08/GB/month |
| Team | 500 GB (shared) | $0.06/GB/month |
| Enterprise | Unlimited | Included |

**Revenue Projection:** Average paid user consumes $29.17/month ($350/yr) in storage, representing 10% of blended ARPU.

---

## Special Programs

### Academic Program (80% Discount)

**Eligibility:** Accredited universities, community colleges, research institutions. Verified via .edu email domain or institutional verification.

| Tier | Standard Price | Academic Price |
|------|---------------|----------------|
| Free | $0 | $0 (enhanced: 5 GB storage, 1,000 tokens/day) |
| Starter | $49/mo | $10/mo |
| Pro | $99/mo | $20/mo |
| Team (Classroom) | $199/seat/mo | $40/seat/mo |
| Department License | Custom | $2,000 - $15,000/yr (50-500 seats) |

**Additional Academic Benefits:**
- Free Pro access for professors and researchers (up to 5 per department)
- Classroom licenses with semester-aligned billing
- Research compute credits ($500/year per active research group)
- Priority access to beta features for research collaborations
- Co-publishing program for novel simulation methodologies

**Strategic Rationale:** Students trained on ODE become champions at their future employers. A single graduating class of 40 students seeds 30+ companies over 5 years.

### Startup Program

**Eligibility:** Companies less than 3 years old, under $5M in funding, fewer than 25 employees. Applied via application with verification.

| Benefit | Detail |
|---------|--------|
| Year 1 | Pro plan free for up to 5 seats |
| Year 2 | 50% discount on Team plan |
| Year 3 | 25% discount on Team plan |
| Compute Credits | $1,000 in free compute credits |
| Mentorship | Access to ODE engineering office hours |

**Eligibility Partners:** Y Combinator, Techstars, 500 Global, HAX, Bolt, university incubators.

**Strategic Rationale:** Hardware startups that succeed on ODE become long-term customers as they scale. Early investment in their success generates outsized LTV.

---

## ARPU Breakdown & Revenue Model

### Blended ARPU Composition

| Revenue Stream | Monthly | Annual | % of ARPU |
|---------------|---------|--------|-----------|
| Subscription | $102.08 | $1,225 | 35% |
| AI Tokens | $87.50 | $1,050 | 30% |
| Compute | $72.92 | $875 | 25% |
| Storage | $29.17 | $350 | 10% |
| **Total** | **$291.67** | **$3,500** | **100%** |

### ARPU by Segment

| Segment | Paid Users | ARPU | Segment ARR |
|---------|-----------|------|-------------|
| Enterprise OEMs | 42 | $10,714 | $450,000 |
| Engineering Consultancies | 56 | $4,464 | $250,000 |
| Universities | 70 | $2,143 | $150,000 |
| Indie Engineers | 112 | $1,339 | $150,000 |
| **Total** | **280** | **$3,571** | **$1,000,000** |

### Revenue Ramp Assumptions

| Month | Paid Users | MRR | Cumulative Revenue |
|-------|-----------|-----|--------------------|
| M1 | 3 | $1,000 | $1,000 |
| M3 | 15 | $5,000 | $12,000 |
| M6 | 60 | $20,000 | $72,000 |
| M9 | 140 | $48,000 | $195,000 |
| M12 | 280 | $83,333 | $1,000,000 (ARR) |

---

## Competitive Pricing Comparison

| Feature | ODE Pro | ANSYS Mechanical | COMSOL | SimScale |
|---------|---------|-----------------|--------|----------|
| Annual Cost | $948 - $1,188 | $30,000 - $50,000 | $5,000 - $15,000 | $2,400 - $4,800 |
| Multi-Physics | Included | Add-on modules | Included | Limited |
| CAD Integration | Native | Separate (SpaceClaim) | Basic | Import only |
| AI Assistant | Included | None | None | None |
| Browser-Based | Yes | No (desktop) | No (desktop) | Yes |
| MBSE | Included | None | None | None |
| Pay-as-you-go | Yes | No | No | Limited |

**Key Differentiator:** ODE delivers multi-physics CAD+CAE+MBSE with AI assistance at 5-50x lower cost than legacy tools, with zero installation and usage-based scaling.

---

## Pricing Governance

### Discount Authority

| Discount Level | Approval Required |
|---------------|-------------------|
| 0-10% | Sales rep (standard annual commitment) |
| 11-20% | Sales manager |
| 21-30% | VP Sales |
| 31-50% | CEO (strategic accounts only) |
| 50%+ | Board-level (academic program excluded) |

### Price Change Policy

- Annual price increases capped at 5% for existing customers on active contracts.
- 90-day advance notice for any pricing changes.
- Grandfathered pricing honored for 12 months after any tier restructuring.
- Usage-based rates reviewed quarterly; changes effective next billing cycle.

### Metrics to Monitor

- Blended ARPU trend (target: $3,500, floor: $3,000)
- Usage-to-subscription ratio (target: 65:35, monitor for margin)
- Free-to-paid conversion rate (target: 5-8%)
- Net revenue retention (target: 120%+)
- Gross margin on compute (target: 60%+)
- AI token margin (target: 70%+ after model costs)

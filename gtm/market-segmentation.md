# ODE Market Segmentation & ICP Profiles

## Overview

ODE targets four distinct Ideal Customer Profiles (ICPs) across the engineering simulation and design market. Each segment has unique pain points, buying behaviors, and revenue potential. This document defines each ICP in detail to guide messaging, channel selection, sales motions, and product prioritization.

**Revenue Target:** $1M ARR | **Token ARPU:** $3,500/year | **Paid Users:** 280 | **Mix:** 40% PLG / 60% SLG  
**Business Model:** Token-first (AI compute billed per token) + Professional Services | **Distribution:** Direct + Channel (resellers)

---

## ICP 1: Enterprise OEMs

### Company Profile

| Attribute | Detail |
|-----------|--------|
| Company Size | 500 - 50,000+ employees |
| Industry | Automotive, Aerospace, Heavy Machinery, Consumer Electronics, Energy |
| Annual Revenue | $100M - $50B+ |
| Engineering Headcount | 50 - 5,000+ |
| Current Toolchain | **Dassault CATIA/SIMULIA/GENESYS**, ANSYS Mechanical/Fluent, Abaqus, COMSOL, Siemens NX, internal solvers |
| IT Environment | On-prem data centers, hybrid cloud, strict security policies |
| Geography | North America, Europe, Japan, South Korea |

### Key Personas

| Persona | Title | Responsibilities | Influence |
|---------|-------|-----------------|-----------|
| **Champion** | Senior Simulation Engineer | Runs day-to-day FEA/CFD, evaluates new tools | High (bottom-up) |
| **Decision Maker** | VP of Engineering / CTO | Owns toolchain budget, sets digital strategy | Final authority |
| **Influencer** | IT/Security Director | Approves cloud vendors, data governance | Veto power |
| **Budget Holder** | Procurement / Finance | Negotiates contracts, manages vendor relationships | Contractual |
| **End User** | Junior/Mid-Level Engineer | Uses tools daily, provides adoption feedback | Adoption signal |

### Pain Points

1. **License Cost Burden** -- Enterprise simulation licenses cost $30K-150K per seat annually, with multi-year lock-in contracts that inflate budgets regardless of actual utilization.
2. **Toolchain Fragmentation** -- Engineers switch between 4-7 disconnected tools (CAD, meshing, solver, post-processing, MBSE), losing hours daily on file conversion and data translation.
3. **Slow Iteration Cycles** -- Traditional simulation workflows take days to weeks per design iteration due to manual mesh setup, long solver queues, and limited compute access.
4. **Talent Shortage** -- Experienced simulation engineers are scarce and expensive; junior engineers need 12-18 months to become productive on legacy tools.
5. **Collaboration Gaps** -- Sharing simulation results across teams and geographies requires exporting static reports, losing interactive exploration capability.
6. **Legacy Architecture Lock-in** -- Dassault, ANSYS, and Siemens charge $30K–$150K/seat for architectures built in the 1990s. They cannot meaningfully rebuild for AI without destroying backwards compatibility. Customers are locked into multi-year contracts that deliver no AI-era value.

### Decision Criteria

- Security and compliance (SOC 2, ISO 27001, data residency)
- Solver accuracy validated against known benchmarks
- Integration with existing PLM/PDM systems (Teamcenter, Windchill)
- Total cost of ownership over 3-5 years
- Vendor stability and long-term roadmap
- On-premises or private cloud deployment options

### Buying Process

1. **Discovery (Weeks 1-4):** Engineer discovers ODE via conference, peer referral, or technical content.
2. **Evaluation (Weeks 4-12):** Technical team runs benchmark problems against incumbent solvers.
3. **Security Review (Weeks 8-16):** IT and legal review cloud architecture, data handling, compliance certifications.
4. **Pilot (Weeks 12-24):** 5-20 seat paid pilot on a real project with defined success criteria.
5. **Procurement (Weeks 20-32):** Contract negotiation, MSA, SOW, payment terms.
6. **Deployment (Weeks 28-40):** Rollout to broader team, training, integration with PLM.

### Commercial Profile

| Metric | Value |
|--------|-------|
| ACV Range | $25,000 - $500,000+ |
| Target ACV | $50,000 - $150,000 |
| Sales Cycle | 6-12 months |
| Expansion Potential | 3-10x over 24 months |
| Preferred Channels | Direct sales, industry events, peer referrals |
| Messaging Themes | "Replace your Dassault stack at 10% of the cost", "AI-native FEM + CFD included in your token plan", "From CAD to MBSE to circuit design — one platform" |

---

## ICP 2: Engineering Consultancies

### Company Profile

| Attribute | Detail |
|-----------|--------|
| Company Size | 10 - 500 employees |
| Industry | Engineering Services, Product Development, Testing & Validation |
| Annual Revenue | $2M - $100M |
| Engineering Headcount | 5 - 200 |
| Current Toolchain | ANSYS, COMSOL, SolidWorks Simulation, HyperWorks |
| IT Environment | Cloud-friendly, minimal IT overhead, project-based infrastructure |
| Geography | Global, concentrated in US, UK, Germany, India |

### Key Personas

| Persona | Title | Responsibilities | Influence |
|---------|-------|-----------------|-----------|
| **Champion** | Lead Simulation Engineer | Delivers client projects, selects tools per project | High |
| **Decision Maker** | Managing Director / Partner | Sets firm strategy, approves tool investments | Final authority |
| **End User** | Project Engineer | Executes simulation tasks on client deliverables | Adoption |
| **Influencer** | Business Development Manager | Understands client needs, shapes service offerings | Strategic |

### Pain Points

1. **License Utilization Volatility** -- Project-based demand means licenses sit idle 30-50% of the time while still incurring annual fees, destroying project margins.
2. **Client Tool Compatibility** -- Clients demand deliverables in specific formats (ANSYS .rst, Abaqus .odb), requiring the consultancy to maintain multiple expensive tool licenses.
3. **Compute Bottlenecks** -- Large client projects require burst compute capacity that local workstations cannot provide, leading to missed deadlines.
4. **Margin Pressure** -- Tool costs represent 15-25% of project budgets; any reduction in tool spend drops directly to profit margin.
5. **Onboarding New Hires** -- New engineers need weeks of training on proprietary tools before they can bill to client projects.

### Decision Criteria

- Pay-as-you-go or usage-based pricing aligned to project revenue
- Multi-physics capability to reduce the number of separate tools
- Browser-based access for distributed teams and client collaboration
- Export compatibility with client-required formats
- Fast onboarding for new team members

### Buying Process

1. **Discovery (Week 1-2):** Partner or lead engineer encounters ODE through content, webinar, or peer.
2. **Trial (Week 2-4):** Test on a real or representative project to validate workflow.
3. **Business Case (Week 4-6):** Compare total project cost vs. incumbent tools.
4. **Decision (Week 6-8):** Managing Director approves based on margin improvement.
5. **Onboarding (Week 8-10):** Roll out to project team, migrate first client project.

### Commercial Profile

| Metric | Value |
|--------|-------|
| ACV Range | $5,000 - $50,000 |
| Target ACV | $10,000 - $25,000 |
| Sales Cycle | 4-8 weeks |
| Expansion Potential | 2-5x as firm wins more projects |
| Preferred Channels | Content marketing, LinkedIn, webinars, industry groups |
| Messaging Themes | "Token-based: pay per simulation run, not per seat-year", "ODE FEM + CFD replaces ANSYS + SolidWorks Simulation in one subscription", "AI does the meshing — your engineers do the thinking" |

---

## ICP 3: Universities & Research Institutions

### Company Profile

| Attribute | Detail |
|-----------|--------|
| Institution Size | 1,000 - 50,000+ students |
| Departments | Mechanical Engineering, Aerospace, Civil, Biomedical, Materials Science |
| Annual Research Budget | $5M - $500M (engineering departments) |
| Users per Institution | 20 - 500 (faculty + graduate students) |
| Current Toolchain | ANSYS Academic, COMSOL Classroom, open-source (OpenFOAM, FEniCS) |
| IT Environment | Campus networks, shared HPC clusters, BYOD culture |
| Geography | Global, with emphasis on US R1 universities, EU technical universities |

### Key Personas

| Persona | Title | Responsibilities | Influence |
|---------|-------|-----------------|-----------|
| **Champion** | Professor / Lab Director | Selects tools for courses and research, writes grants | High |
| **Decision Maker** | Department Chair / Dean | Approves departmental software budgets | Final authority |
| **Influencer** | IT Director (College-level) | Manages campus software licensing agreements | Veto power |
| **End User** | Graduate Student / Postdoc | Conducts research simulations, publishes papers | Adoption |
| **Future Champion** | Undergraduate Student | Learns tools in coursework, carries preferences to industry | Long-term |

### Pain Points

1. **Budget Constraints** -- Academic software budgets are shrinking while commercial simulation license costs are rising, forcing difficult trade-offs between tools and headcount.
2. **Open-Source Complexity** -- Free alternatives like OpenFOAM require weeks of setup, scripting, and debugging that consume research time without advancing publications.
3. **HPC Access Bottlenecks** -- Campus compute clusters have long queue times (hours to days) during peak periods, stalling research timelines.
4. **Teaching Tool Gaps** -- Students learn outdated tools in coursework that do not reflect modern industry practice, reducing employability.
5. **Reproducibility** -- Sharing simulation setups for peer review and publication requires detailed documentation that legacy tools make difficult.

### Decision Criteria

- Deep academic discount (80%+ off commercial pricing)
- Easy classroom deployment (browser-based, no install)
- API access for custom research workflows
- Citation-ready outputs for publications
- Integration with Jupyter, Python, MATLAB ecosystems
- Free tier sufficient for coursework

### Buying Process

1. **Discovery (Ongoing):** Professor encounters ODE at conference, through publication, or colleague referral.
2. **Personal Trial (Week 1-4):** Professor or graduate student tests on research problem.
3. **Course Pilot (1 semester):** Adopted for one course section, typically 20-40 students.
4. **Department Adoption (Next academic year):** Proposal to department for site license.
5. **Procurement (1-3 months):** University purchasing process, potentially via existing cloud/software frameworks.

### Commercial Profile

| Metric | Value |
|--------|-------|
| ACV Range | $2,000 - $25,000 (after 80% discount) |
| Target ACV | $5,000 - $15,000 |
| Sales Cycle | 1-2 academic semesters (3-8 months) |
| Expansion Potential | Department to college to university-wide |
| Preferred Channels | Academic conferences, professor networks, student ambassadors, free tier |
| Messaging Themes | "Free for students, affordable for departments", "Research-grade simulation in the browser", "Graduate job-ready engineers" |

---

## ICP 4: Indie Engineers & Startups

### Company Profile

| Attribute | Detail |
|-----------|--------|
| Company Size | 1 - 50 employees |
| Industry | Hardware startups, freelance engineering, maker community, robotics |
| Annual Revenue | $0 - $10M |
| Engineering Headcount | 1 - 20 |
| Current Toolchain | SolidWorks, Fusion 360, free trials, open-source, manual calculations |
| IT Environment | Cloud-native, personal laptops, no IT department |
| Geography | Global, concentrated in tech hubs (SF, NYC, Austin, London, Berlin, Bangalore) |

### Key Personas

| Persona | Title | Responsibilities | Influence |
|---------|-------|-----------------|-----------|
| **Champion & Decision Maker** | Founder / CTO | Makes all technical and purchasing decisions | Sole authority |
| **End User** | Staff Engineer | Designs products, runs simulations, ships hardware | Adoption |
| **Influencer** | Investor / Advisor | Recommends tools, validates technical approach | Advisory |

### Pain Points

1. **Cost Prohibitive Tools** -- Commercial simulation software costs more than the startup's entire monthly cloud budget; a single ANSYS seat exceeds seed-stage runway constraints.
2. **Skill Gap** -- Founders are often mechanical or electrical engineers but not simulation specialists; they need approachable tools that do not require FEA expertise.
3. **Speed to Market** -- Hardware startups must iterate physical designs in weeks, not months; any friction in the simulation workflow directly delays product launches.
4. **No IT Support** -- There is no dedicated IT team to install, configure, or maintain complex desktop simulation software.
5. **Investor Pressure** -- VCs expect data-driven design decisions; simulation results validate product claims and de-risk hardware development.

### Decision Criteria

- Free tier that covers basic needs
- Intuitive UI with minimal learning curve
- Affordable paid plans that scale with the business
- Browser-based with no installation requirements
- AI-assisted workflows that reduce expertise barrier
- Fast time-to-first-simulation (under 30 minutes)

### Buying Process

1. **Discovery (Day 1):** Finds ODE through Google search, Twitter/X, ProductHunt, or Hacker News.
2. **Free Trial (Day 1-7):** Signs up, runs first simulation on real design problem.
3. **Self-Serve Upgrade (Week 1-4):** Hits free tier limits, upgrades to Starter or Pro.
4. **Team Expansion (Month 2-6):** Adds team members as company grows.
5. **Usage Growth (Ongoing):** AI token and compute usage scales with development velocity.

### Commercial Profile

| Metric | Value |
|--------|-------|
| ACV Range | $600 - $5,000 |
| Target ACV | $1,200 - $3,000 |
| Sales Cycle | Same-day to 2 weeks (PLG) |
| Expansion Potential | 2-10x as team grows |
| Preferred Channels | SEO, social media, ProductHunt, communities, developer relations |
| Messaging Themes | "Enterprise-grade simulation for $49/month", "AI does the meshing for you", "Ship hardware faster" |

---

## ICP Comparison Summary

| Dimension | Enterprise OEMs | Engineering Consultancies | Universities | Indie Engineers |
|-----------|----------------|--------------------------|--------------|-----------------|
| **Company Size** | 500 - 50,000+ | 10 - 500 | 1,000 - 50,000 students | 1 - 50 |
| **Target ACV** | $50K - $150K | $10K - $25K | $5K - $15K | $1.2K - $3K |
| **Sales Motion** | SLG (direct) | SLG (light-touch) | SLG (academic) | PLG (self-serve) |
| **Sales Cycle** | 6 - 12 months | 4 - 8 weeks | 3 - 8 months | Same-day - 2 weeks |
| **Primary Persona** | Sr. Simulation Engineer | Lead Engineer / Partner | Professor | Founder / CTO |
| **Top Pain Point** | License cost + fragmentation | License utilization | Budget constraints | Cost + skill gap |
| **Key Channel** | Direct sales + events | Content + LinkedIn | Conferences + free tier | SEO + social + PLG |
| **Expansion Path** | Department to division | Project to firm-wide | Course to university | Startup growth |
| **Revenue Contribution** | 45% of ARR target | 25% of ARR target | 15% of ARR target | 15% of ARR target |
| **User Contribution** | 15% of paid users | 20% of paid users | 25% of paid users | 40% of paid users |
| **Strategic Value** | Revenue + logos | Revenue + referrals | Pipeline + brand | Volume + community |

---

## Segment Prioritization Matrix

### Priority 0: Distribution Channel Partners

Engineering consultancies and Dassault/ANSYS resellers who want to offer a modern AI-native alternative to their existing client base. These partners multiply headcount coverage without additional hiring. Each partner has an existing book of 10–50 engineering clients with active simulation tool contracts.

**Target partner profile:** EU-based engineering consulting firms (5–200 engineers), firms currently reselling ANSYS or Dassault licences, university tech-transfer offices.  
**Goal:** 3–5 signed partners in Year 1, generating $200K+ pipeline.  
**Model:** Revenue share 20–30% on first-year ACV; ODE provides training, demo licences, co-marketing budget.

---

### Priority 1: Enterprise OEMs + Indie Engineers (Parallel)

Enterprise OEMs drive the majority of revenue and provide logo credibility. Indie Engineers drive the majority of user volume and feed the PLG flywheel. These two segments operate through completely different motions (SLG vs. PLG) and can be pursued simultaneously without resource conflict.

### Priority 2: Engineering Consultancies

Consultancies are natural early adopters because they evaluate tools frequently, have shorter sales cycles, and their project-based model aligns with usage-based pricing. They also serve as a channel to Enterprise OEMs by recommending tools to their clients.

### Priority 3: Universities

Universities are a long-term pipeline investment. Students who learn ODE in coursework will request it at their future employers. The 80% academic discount means lower near-term revenue, but the lifetime value of a trained user base entering industry is substantial.

---

## TAM/SAM/SOM by Segment

| Segment | TAM | SAM | Year 1 SOM |
|---------|-----|-----|------------|
| Enterprise OEMs | $15B | $750M | $450K |
| Engineering Consultancies | $4B | $250M | $250K |
| Universities | $2B | $150M | $150K |
| Indie Engineers & Startups | $2B | $150M | $150K |
| Channel / Reseller | — | — | $200K |
| **Total** | **$23B** | **$1.30B** | **$1.2M** |

*AI-native engineering tools emerging subsegment: ~$800M (2025), growing 45%+ annually — Orthogonal's primary beachhead.*

---

## Next Steps

1. Validate ICP definitions through 20+ customer discovery interviews per segment.
2. Build persona-specific messaging and value propositions (see go-to-market-strategy.md).
3. Align pricing tiers to each ICP's willingness-to-pay (see pricing-strategy.md).
4. Map channels to ICPs for budget allocation (see channel-strategy.md).
5. Develop segment-specific content calendars (see launch-plan.md).

# ODE Sales Playbook

## Sales Process Overview

ODE runs two parallel motions:
- **PLG Sales-Assist**: Self-serve users who need help upgrading or expanding (reactive)
- **Enterprise Sales**: Outbound to large accounts with formal procurement (proactive)

---

## ICP Qualification Framework (BANT+)

| Criteria | Qualifying Questions | Strong Signal | Weak Signal |
|----------|---------------------|---------------|-------------|
| **Budget** | "Do you have budget for engineering tools this year?" | Dedicated simulation/AI budget | "We'd need to find budget" |
| **Authority** | "Who makes the final decision on tool adoption?" | Talking to VP Eng/CTO | "I'd need to check with my manager" |
| **Need** | "What's your biggest engineering workflow pain?" | Tool silos, slow iteration, no AI | Happy with current tools |
| **Timeline** | "When do you need a solution?" | This quarter | "Maybe next year" |
| **Technology Fit** | "Do you use Modelica, FMI, or SysML?" | Active Modelica/FMI user | No simulation experience |

### Qualification Scoring

| Score | Level | Action |
|------:|-------|--------|
| 5/5 | Hot | Fast-track to pilot, involve founder |
| 4/5 | Warm | Standard enterprise process |
| 3/5 | Lukewarm | Nurture with content, check quarterly |
| <3 | Cold | Add to marketing nurture, deprioritize |

---

## Discovery Questions by Segment

### Enterprise OEM (Aerospace/Automotive)
1. "How many engineers are involved in system-level simulation?"
2. "What tools does your team use for MBSE and Modelica simulation today?"
3. "How long does a typical design iteration cycle take, from requirements to validated model?"
4. "What's your AI adoption roadmap for engineering?"
5. "Have you explored cloud-based alternatives to your current desktop tools?"
6. "What's the cost of a simulation bottleneck delaying a program milestone?"

### Engineering Consultancy
1. "How many concurrent simulation projects does your team run?"
2. "Do you license tools per-project or company-wide?"
3. "How do you collaborate with clients on engineering deliverables?"
4. "What percentage of time is spent on tool setup vs. actual engineering?"
5. "Would your clients value seeing real-time simulation results?"

### University/Research
1. "What simulation tools do you use for teaching?"
2. "How do students currently access Modelica/simulation environments?"
3. "Would browser-based access simplify your lab setup?"
4. "Are you publishing research on AI-augmented engineering?"

---

## Demo Scripts

### Quick Demo (15 minutes)

| Time | Section | What to Show |
|-----:|---------|-------------|
| 0-2 min | Hook | "How long does it take to build a [X] model today?" |
| 2-8 min | Live AI Demo | Type engineering requirement → AI generates Modelica model → simulate → see results |
| 8-12 min | Platform Tour | Show 2-3 tools (Geometry, Vision, System) — integrated workflow |
| 12-14 min | Value | "That took 5 minutes. Your team currently takes [X hours/days]." |
| 14-15 min | CTA | "Want to run this with your own requirements? Here's a free account." |

### Deep Dive Demo (45 minutes)

| Time | Section | What to Show |
|-----:|---------|-------------|
| 0-5 min | Discovery | Understand their specific workflow and pain points |
| 5-10 min | Positioning | How ODE is different (AI-native, integrated, open standards) |
| 10-30 min | Custom Demo | Build a model relevant to their industry using AI |
| 30-35 min | Collaboration | Show real-time co-editing, team features |
| 35-40 min | ROI Discussion | Time savings, tool consolidation, AI acceleration |
| 40-45 min | Next Steps | Pilot proposal, timeline, success criteria |

---

## Competitive Battle Cards

### vs. Neural Concept

| Topic | Our Pitch |
|-------|-----------|
| **Their strength** | Deep AI for design optimization, big enterprise clients |
| **Their weakness** | No CAD, no MBSE, no Modelica — it's a point solution |
| **Our differentiation** | "Neural Concept optimizes. ODE creates. We provide the full platform." |
| **When we win** | Customer needs full workflow, not just optimization |
| **When we lose** | Customer only needs CFD/FEA optimization on existing designs |
| **Counter** | "AI optimization is one step. What about the other 90% of the workflow?" |

### vs. Autodesk Fusion

| Topic | Our Pitch |
|-------|-----------|
| **Their strength** | Huge install base, comprehensive CAD/CAM |
| **Their weakness** | Legacy architecture, AI is bolted on, no Modelica/MBSE |
| **Our differentiation** | "Built for AI from day one. Not AI added to a 30-year codebase." |
| **When we win** | Customer values AI, system simulation, open standards |
| **When we lose** | Customer needs CAM/manufacturing or has deep Autodesk lock-in |
| **Counter** | "What would it look like if your tools understood physics natively?" |

### vs. Open-Source Modelica (OpenModelica)

| Topic | Our Pitch |
|-------|-----------|
| **Their strength** | Free, open-source, academic standard |
| **Their weakness** | No AI, no CAD, desktop-only, no collaboration |
| **Our differentiation** | "We love Modelica. We made it 10x more accessible with AI." |
| **When we win** | Customer wants AI, collaboration, integrated platform |
| **When we lose** | Customer only needs basic Modelica, zero budget |
| **Counter** | "Start with our free tier — you get Modelica + AI + browser access." |

---

## Objection Handling

| Objection | Response |
|-----------|----------|
| **"Too expensive"** | "What's the cost of your current tool stack? ODE replaces 3+ tools. Plus, our usage-based pricing means you pay for what you use." |
| **"We already use Autodesk/Dassault"** | "Great — ODE works alongside existing tools via FMI export. Many customers start with ODE for AI simulation while keeping their CAD tool, then consolidate over time." |
| **"Is the AI trustworthy?"** | "ODE generates standard Modelica code that you can review and verify. The AI accelerates creation; the engineer validates. We also keep a full audit trail." |
| **"Security concerns (cloud)"** | "We offer Enterprise tier with SSO/SAML, SOC 2 compliance path, audit logs, and IP restrictions. On-premise deployment is available for highly regulated environments." |
| **"We need to evaluate alternatives"** | "Absolutely — we encourage comparison. Here's what makes ODE unique: [3 differentiators]. Can we set up a pilot so you can evaluate with real work?" |
| **"Not ready for AI in engineering"** | "That's fair. AI in engineering is new. Our free tier lets your team experiment with zero risk. When you're ready to scale, we're here." |
| **"My team won't adopt a new tool"** | "ODE is browser-based — no install, no setup. Engineers can try it in 60 seconds. We've seen adoption happen bottom-up because the AI makes work genuinely faster." |
| **"We need on-premise"** | "Available on Enterprise tier. Let's discuss your security requirements and how we can meet them." |
| **"What if you shut down?"** | "All your models are in open Modelica/FMI format — fully portable. No vendor lock-in, by design." |
| **"We need more features in X"** | "Tell us what you need. Our product roadmap is customer-driven, and Enterprise customers get direct input into feature priorities." |

---

## ROI Calculator Framework

### Input Variables
- Number of engineers using simulation
- Average hours per simulation cycle
- Number of simulation cycles per project
- Current tool license costs (annual)
- Number of projects per year

### ROI Formula
```
Time Savings = (hours_per_cycle × reduction_factor × cycles × engineers × hourly_rate)
Tool Savings = (current_licenses - ode_cost)
Total Annual ROI = Time Savings + Tool Savings

Typical Results:
- 60-80% reduction in simulation setup time
- 30-50% reduction in iteration cycles
- 20-40% reduction in tool license costs
```

### Example ROI (10-engineer team)
| Metric | Before ODE | With ODE | Savings |
|--------|-----------|----------|--------:|
| Simulation setup time | 8 hours | 2 hours | 6 hours/cycle |
| Cycles per project | 10 | 6 | 4 fewer cycles |
| Annual tool licenses | $150,000 | $95,000 | $55,000 |
| Engineering time saved | - | 2,400 hours/year | $240,000 value |
| **Total Annual Value** | | | **$295,000** |

---

## Proposal Template Structure

1. **Executive Summary** — The challenge, our solution, expected outcomes
2. **Solution Overview** — ODE platform, key features, AI capabilities
3. **Implementation Plan** — Pilot → rollout → expansion timeline
4. **Pricing** — Tier, seats, estimated usage costs
5. **ROI Projection** — Customized for their team size and workflow
6. **Terms** — Contract duration, SLA, support level
7. **Next Steps** — Signature, onboarding kickoff date

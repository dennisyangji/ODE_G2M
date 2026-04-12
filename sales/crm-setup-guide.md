# ODE CRM Setup Guide

## Recommended Platform: HubSpot

HubSpot is ideal for ODE's hybrid PLG + enterprise motion: free CRM tier to start, scales to enterprise, integrates with product analytics, and supports both self-serve and sales-assisted flows.

---

## Pipeline Configuration

### Deal Stages

| Stage | Description | Probability | Actions |
|-------|------------|:-----------:|---------|
| **Lead** | Inbound sign-up or outbound contact | 5% | Auto-created from product sign-up or manual entry |
| **MQL** | Meets ICP criteria + engagement threshold | 15% | Lead score >50, auto-route to sales |
| **SQL** | Sales-qualified, budget/authority confirmed | 30% | Discovery call completed, BANT qualified |
| **Pilot** | Active enterprise pilot (30 days) | 50% | Pilot agreement signed, success criteria set |
| **Proposal** | Pricing proposal sent | 70% | Formal proposal delivered, procurement engaged |
| **Negotiation** | Contract review in progress | 85% | Legal/procurement review, terms discussion |
| **Closed Won** | Deal signed | 100% | Contract executed, onboarding begins |
| **Closed Lost** | Deal lost | 0% | Reason captured, nurture sequence activated |

---

## Lead Scoring Model

### ICP Fit Score (0-50 points)

| Criteria | Points | Details |
|----------|-------:|---------|
| Industry match (aerospace, auto, energy, robotics) | +15 | Core target industries |
| Company size 500+ employees | +10 | Enterprise target |
| Company size 50-499 | +5 | Mid-market target |
| Role: VP Engineering / CTO / Head of Simulation | +15 | Decision maker |
| Role: Senior Engineer / Tech Lead | +10 | Champion / influencer |
| Role: Engineer | +5 | End user |
| Uses Modelica / FMI / SysML currently | +10 | High-fit signal |
| Located in target geography (EU, US, Japan) | +5 | Go-to-market focus |

### Engagement Score (0-50 points)

| Activity | Points | Details |
|----------|-------:|---------|
| Free account sign-up | +5 | Top of funnel |
| Built first AI model | +10 | Activation |
| Ran 5+ simulations | +10 | Engagement |
| Invited a teammate | +15 | Expansion signal |
| Hit AI token limit | +10 | Ready to upgrade |
| Attended webinar | +5 | Interest signal |
| Downloaded whitepaper | +5 | Research phase |
| Visited pricing page | +10 | Purchase intent |
| Requested enterprise demo | +20 | High intent |

### Score Thresholds

| Score | Classification | Action |
|------:|---------------|--------|
| 0-25 | Cold Lead | Nurture sequence |
| 26-50 | Warm Lead | Marketing nurture + monitoring |
| 51-75 | MQL | Route to sales for review |
| 76-100 | SQL | Priority sales outreach |

---

## Custom Properties

### Contact Properties

| Property | Type | Purpose |
|----------|------|---------|
| ICP_segment | Dropdown | Enterprise OEM / Consultancy / Academic / Indie |
| engineering_domain | Multi-select | Thermal / Structural / Fluid / Electrical / Multi-physics |
| current_tools | Multi-select | Autodesk / Dassault / Modelon / SimScale / Other |
| ai_adoption_level | Dropdown | No AI / Exploring / Pilot / Production |
| modelica_experience | Dropdown | None / Beginner / Intermediate / Expert |

### Company Properties

| Property | Type | Purpose |
|----------|------|---------|
| target_account_tier | Dropdown | Tier 1 (top 20) / Tier 2 (next 30) / Tier 3 |
| estimated_seats | Number | Potential seat count |
| estimated_acv | Currency | Estimated annual contract value |

### Deal Properties

| Property | Type | Purpose |
|----------|------|---------|
| deal_type | Dropdown | PLG Self-Serve / PLG Sales-Assist / Enterprise |
| pilot_start_date | Date | Pilot tracking |
| pilot_end_date | Date | Pilot tracking |
| pilot_success_criteria | Text | What defines pilot success |
| monthly_ai_tokens | Number | Estimated AI token usage |
| monthly_compute_hours | Number | Estimated compute usage |

---

## Automation Workflows

### 1. New Sign-Up → Lead Creation
**Trigger**: Free account created
**Actions**: Create contact, enrich with Clearbit/Apollo, calculate ICP fit score, add to onboarding email sequence

### 2. MQL Routing
**Trigger**: Lead score crosses 50
**Actions**: Alert sales via Slack, create task for follow-up within 24 hours, add to sales sequence

### 3. Pilot Tracking
**Trigger**: Deal moved to "Pilot" stage
**Actions**: Set pilot dates, create success criteria task, schedule weekly check-in reminders, notify CS team

### 4. Expansion Signal
**Trigger**: Existing customer invites 3+ new users or hits 80% token/compute usage
**Actions**: Alert account owner, create expansion opportunity, add to expansion email sequence

### 5. Churn Risk
**Trigger**: Paid user inactive 14+ days or usage drops 50%+
**Actions**: Alert account owner, trigger re-engagement email, create retention task

---

## Reporting Dashboards

### Executive Dashboard
- MRR and ARR trend
- New vs. expansion revenue
- Pipeline value by stage
- Win rate by ICP segment

### PLG Dashboard
- Free sign-ups (daily/weekly)
- Activation rate (built first model)
- Free→Paid conversion rate
- Self-serve revenue

### Sales Dashboard
- Enterprise pipeline by stage
- Average deal size and sales cycle
- Win/loss analysis with reasons
- Activity metrics (calls, demos, proposals)

### Marketing Dashboard
- Leads by source/channel
- MQL→SQL conversion rate
- CAC by channel
- Content performance (traffic, conversions)

---

## Integration Architecture

```
Product (ODE Platform)
    ↓ (events: sign-up, activation, usage)
Segment / Mixpanel
    ↓ (enriched events)
HubSpot CRM
    ↓ (triggers)
Customer.io (email) + Slack (alerts) + Sales workflows
```

### Key Integrations
| Tool | Purpose | Integration |
|------|---------|-------------|
| ODE Platform | Usage data, sign-ups | API → Segment |
| Segment | Event routing | Native HubSpot integration |
| Mixpanel | Product analytics | Segment destination |
| Customer.io | Email automation | HubSpot sync |
| Slack | Sales alerts | HubSpot workflow |
| Clearbit | Data enrichment | HubSpot native |
| Stripe | Billing | HubSpot native |

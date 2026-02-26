# Extraction Guide

How to pull information from discovery call transcripts for each section of the business case.

---

## Client Information

**Extract:**
- Company name
- What they do (industry, services)
- Size indicators (team size, number of clients, etc.)
- Contact names and roles mentioned

**Look for phrases like:**
- "We are a..."
- "What we do is..."
- "Our company..."
- Introductions at the start of the call

---

## Current Systems & Tech Stack

**Extract:**
- All tools/platforms mentioned
- What each is used for
- Who uses what
- Any integrations already in place

**Look for phrases like:**
- "We use {tool} for..."
- "...takes place in {platform}"
- "Our CRM is..."
- "We track {X} in..."

**Common tools to listen for:**
- CRMs: HubSpot, Salesforce, Pipedrive
- Project management: Asana, Monday, ClickUp, Notion, Carbon
- Communication: Slack, Teams
- Data: Airtable, Google Sheets, Excel
- Automation: Zapier, Make, n8n

---

## Pain Points

**Extract:**
- Manual processes described
- Frustrations expressed
- Things that "don't work" or are "hard"
- Time wasted on specific tasks
- Lack of visibility/reporting issues

**Look for phrases like:**
- "The problem is..."
- "We spend a lot of time..."
- "It's hard to..."
- "We don't have visibility into..."
- "Things fall through the cracks"
- "Manual" (anything manual is a pain point)

**Also note positive framing:**
- "Nothing is built yet" = clean slate (good!)
- "We haven't messed anything up" = opportunity to do it right

---

## Desired Outcomes

**Extract:**
- What they want to achieve
- Workflows they want automated
- Visibility they want to gain
- How they describe success

**Look for phrases like:**
- "What we need is..."
- "We want to..."
- "The goal is..."
- "When {X} happens, we want {Y} to happen automatically"
- "We'd like to be able to..."

---

## Timeline & Budget

**Extract:**
- Any timeline mentioned (even rough)
- Budget range if stated
- Urgency indicators

**Look for phrases like:**
- "We'd like to get this done in..."
- "Within {X} days/weeks/months"
- "Budget is..."
- "We're looking to spend..."

**Note:** Even if they mention budget, use `[PRICING TBD]` in the document. Timeline can be referenced but use `[TIMELINE TBD - to be defined after scoping]` in the Project Overview table.

---

## Stakeholders

**Extract:**
- Who will be involved in the project
- Decision makers
- Who will use the final system
- Who might need training

**Look for phrases like:**
- "It'll be myself and..."
- "The stakeholders are..."
- "Once we get it in place, we'll roll it out to..."
- Job titles and names mentioned

---

## Technical Context

**Extract:**
- API mentions
- Integration limitations discussed
- Data transformation needs
- Existing contractor work

**Look for phrases like:**
- "We're working with a {X} contractor..."
- "There are native integrations..."
- "The systems need to talk to each other"
- Any technical architecture discussion

---

## Quotable Moments

**Extract verbatim quotes that:**
- Capture the problem well
- Show self-awareness ("we haven't messed anything up yet")
- Describe the desired relationship ("sprint, relax, recalibrate")
- Express enthusiasm or alignment

**Use quotes to:**
- Add authenticity to Current State section
- Reference in Expected Benefits
- Show you were listening

---

## Information Gaps

**Flag as `[ASSUMPTION: ...]` when you don't have:**
- Specific hours spent on manual tasks
- Number of clients/projects
- Team size details
- Technical API limitations
- Data volume estimates

**Example assumption flags:**
- `[ASSUMPTION: Estimated based on similar engagements]`
- `[ASSUMPTION: Assumes standard API access; to be verified in scoping]`
- `[ASSUMPTION: Time savings would need to be quantified after deeper discovery]`

---

## Section-by-Section Extraction Checklist

### For Executive Summary
- [ ] Client name and industry
- [ ] Core platforms/systems
- [ ] Main problem in one sentence
- [ ] Desired outcome in one sentence

### For Current State Analysis
- [ ] Each system and its purpose
- [ ] Who manages each system
- [ ] 4-6 specific pain points
- [ ] Current tech stack list
- [ ] Any positive aspects (clean slate, etc.)

### For Proposed Solution
- [ ] Solution approach discussed on call
- [ ] Why this approach makes sense
- [ ] Key workflows to automate
- [ ] Technical assumptions to flag

### For Expected Benefits
- [ ] Pain points → benefits mapping
- [ ] Quotes about desired outcomes
- [ ] Future growth mentions

### For Scope of Work
- [ ] Phases discussed (if any)
- [ ] Specific deliverables mentioned
- [ ] Scoping/discovery needs

### For Success Criteria
- [ ] Specific outcomes mentioned
- [ ] How they'd measure success
- [ ] Stakeholder autonomy goals

### For Out of Scope
- [ ] Work being done by others
- [ ] "Phase 2" features mentioned
- [ ] Explicit exclusions discussed

### For Optional Add-Ons
- [ ] Future features mentioned
- [ ] "Later" or "eventually" items
- [ ] Training expansion needs

# Travel Brief Sections Guide

## How to Combine Skill Output with Other Sections

The travel brief is a composite document. Follow this structure:

### Section 1: Trip Overview

```markdown
# Travel Brief: [Destination]
**Dates:** [Start] – [End]
**Duration:** [X] days
**Purpose:** [Business / Leisure / Mixed]
```

### Section 2: Weather Forecast

```markdown
## Weather

**Conditions:** [Description]
**Temperature:** [Low]–[High]°F
**Precipitation:** [Likelihood]
```

### Section 3: Packing List

**Invoke the `travel-packing-list` skill** to generate this section.

The packing list skill will ask clarifying questions and generate climate-appropriate, health-aware recommendations.

### Section 4: Local Tips

```markdown
## Local Tips

### Getting Around
- From airport: [Options]
- Public transit: [Details]
- Rideshare: [Apps available]

### Money
- Currency: [Name]
- Tipping: [Custom]
- Cash vs card: [Preference]

### Language
- Key phrases: Hello, Thank you, Excuse me

### Safety
- Emergency number: [Number]
- Areas to avoid: [If any]
```

### Section 5: Logistics Checklist

```markdown
## Pre-Departure Checklist

- [ ] Passport valid 6+ months
- [ ] Visa (if required)
- [ ] Travel insurance
- [ ] Bank notified
- [ ] Phone plan set
- [ ] Documents copied
```

### Section 6: Emergency Info

```markdown
## Emergency Information

- Local emergency: [Number]
- US Embassy: [Contact]
- Insurance hotline: [Number]
```

---

## Assembly Order

1. Trip Overview
2. Weather
3. Packing List (from travel-packing-list skill)
4. Local Tips
5. Logistics Checklist
6. Emergency Info

## Tone

- Practical and concise
- Specific details over generic advice
- Every line should be actionable

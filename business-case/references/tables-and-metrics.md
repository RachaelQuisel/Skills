# Tables and Metrics

Standard table formats and estimation frameworks for discovery briefs.

**Important:** This is a discovery document. Never include specific dollar amounts — use `[PRICING TBD]` placeholders.

---

## Project Overview Table

**Format:** 2-column table, bold labels, light gray header background

```
| Field | Value |
|-------|-------|
| **Client** | {Client Name} |
| **Consultant Team** | XRAY |
| **Project Goal** | {One clear sentence} |
| **Estimated Timeline** | [TIMELINE TBD - to be defined after scoping] |
| **Approach** | {Brief description} |
```

**Styling (python-docx):**
- Label column: Bold text, Gray 900, light background (#F5F5F0)
- Value column: Regular text, Gray 600

---

## Investment Summary Table

**Format:** Header row + data rows

```
| Phase | Est. Investment |
|-------|-----------------|
| Phase 1: {Scoping/Design} | [PRICING TBD] |
| Phase 2 & 3: {Build/Handoff} | [PRICING TBD] |
```

**Never include:**
- Specific dollar amounts
- Hourly rates
- Total investment figures

---

## Platform Costs Table

**Format:** Platform + Notes

```
| Platform | Notes |
|----------|-------|
| {New Platform} | [Plan level TBD based on requirements] |
| {Integration Tool} | [If needed for specific integrations] |
| Existing tools | {List tools} — no changes anticipated |
```

---

## Optional Add-Ons Table

**Format:** Add-On + Description

```
| Add-On | Description |
|--------|-------------|
| Ongoing Monthly Support | {Relevant description from call} |
| {Feature mentioned for later} | {Brief description} |
| Team Training | Expand beyond initial stakeholders |
| Additional Integrations | Connect other systems as needs evolve |
```

---

## Benefit Estimates (When Applicable)

**Only include quantitative estimates if:**
1. Client provided specific numbers in the call
2. You clearly flag them as assumptions

**Format for estimates:**

If client mentioned specific hours:
> "Currently spending approximately {X} hours per week on {task}"

If estimating based on similar engagements:
> "[ASSUMPTION: Based on similar engagements, teams typically spend 10-20 hours/week on manual {task}]"

**Never calculate:**
- Dollar savings (requires hourly rate assumptions)
- ROI percentages
- Payback periods

These belong in a full proposal after deeper discovery.

---

## Table Styling (python-docx)

```python
from docx.oxml.ns import qn
from docx.oxml import OxmlElement

def set_cell_shading(cell, color_hex):
    """Set cell background color"""
    shading = OxmlElement('w:shd')
    shading.set(qn('w:fill'), color_hex)
    cell._tc.get_or_add_tcPr().append(shading)

# Header row styling
set_cell_shading(header_cell, 'F5F5F0')  # Light gray
header_cell.paragraphs[0].runs[0].bold = True
header_cell.paragraphs[0].runs[0].font.color.rgb = GRAY_900

# Data cell styling
data_cell.paragraphs[0].runs[0].font.color.rgb = GRAY_600
```

---

## Common Placeholder Values

| Situation | Placeholder |
|-----------|-------------|
| Pricing not yet determined | `[PRICING TBD]` |
| Timeline needs scoping | `[TIMELINE TBD - to be defined after scoping]` |
| Scope needs refinement | `[SCOPE TBD: Specific deliverables to be defined after scoping]` |
| Technical assumption | `[ASSUMPTION: {description}]` |
| Plan level unknown | `[Plan level TBD based on {factor}]` |

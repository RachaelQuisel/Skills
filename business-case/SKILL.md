---
name: business-case
description: Transforms discovery call transcripts into XRAY-branded business case documents (.docx). Use when the user provides a transcript and asks for a business case, discovery brief, proposal, or client document. Triggers on "business case", "discovery brief", "proposal from transcript", "turn this transcript into a document", or similar requests.
---

# Business Case Generator

Transforms discovery call transcripts into professional, XRAY-branded business case documents.

## Important Constraints

- **This is a DISCOVERY document** — based on a single initial conversation
- **Tone:** Tentative, exploratory ("Based on our conversation...", "From what we understand...")
- **Pricing:** NEVER include specific dollar amounts — use `[PRICING TBD]` placeholders
- **Estimates:** Use ranges ("15-25 hours/week") not exact figures
- **Assumptions:** Flag with `[ASSUMPTION: ...]` when information is incomplete
- **Output:** Microsoft Word document (.docx) with XRAY branding

## Workflow

### Step 1: Extract Information from Transcript

Read the transcript and extract (see [references/extraction-guide.md](references/extraction-guide.md)):

- Client name and contacts
- What the client does (industry, size)
- Current systems/tools in use
- Pain points and challenges
- Desired outcomes/goals
- Timeline mentioned
- Stakeholders involved
- Any technical constraints
- Quotes worth including verbatim

### Step 2: Structure the Document

Follow the 10-section structure (see [references/document-structure.md](references/document-structure.md)):

1. Title Page + Disclaimer
2. Executive Summary
3. Project Overview (table)
4. Current State Analysis
5. Proposed Solution
6. Expected Benefits
7. Scope of Work (phases)
8. Success Criteria
9. Out of Scope
10. Optional Add-Ons
11. Next Steps

### Step 3: Apply XRAY Branding

**Invoke the `xray-brand` skill** for full brand guidelines, but key elements:

- **Headings:** Gray 900 (#0E1C2D)
- **Body text:** Gray 600 (#686F76)
- **Table headers:** Light gray background (#F5F5F0)
- **Page background:** Floralwhite (not pure white)
- **Logo:** XRAY wordmark on title page

### Step 4: Generate Word Document

Use python-docx to create a properly formatted .docx file:

```python
from docx import Document
from docx.shared import Pt, RGBColor
from docx.enum.text import WD_ALIGN_PARAGRAPH

# XRAY Brand Colors
GRAY_900 = RGBColor(0x0E, 0x1C, 0x2D)  # Headings
GRAY_600 = RGBColor(0x68, 0x6F, 0x76)  # Body text
```

Save to user's Desktop with filename: `{Client Name} - Discovery Brief.docx`

## Reference Files

- **[references/document-structure.md](references/document-structure.md)** — Section templates and formatting
- **[references/extraction-guide.md](references/extraction-guide.md)** — What to extract from transcripts
- **[references/tables-and-metrics.md](references/tables-and-metrics.md)** — Table formats, estimate frameworks
- **[references/tone-and-style.md](references/tone-and-style.md)** — Writing guidelines for discovery docs

## Example Output Sections

### Project Overview Table

| Field | Value |
|-------|-------|
| **Client** | {Client Name} |
| **Consultant Team** | XRAY |
| **Project Goal** | {One sentence describing the goal} |
| **Estimated Timeline** | [TIMELINE TBD - to be defined after scoping] |
| **Approach** | {Brief approach description} |

## Do's and Don'ts

### Do
- Use actual quotes from the transcript when they add value
- Flag assumptions clearly with `[ASSUMPTION: ...]`
- Keep sections concise — this is a conversation starter
- Match the client's language and terminology
- Include specific system names mentioned (HubSpot, Notion, etc.)

### Don't
- Include specific dollar amounts for pricing
- Make confident claims without supporting information
- Over-engineer the proposed solution
- Include detailed ROI calculations (save for full proposal)
- Use generic filler content — every sentence should add value

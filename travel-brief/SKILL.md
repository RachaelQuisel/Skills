---
name: travel-brief
description: Creates a comprehensive travel briefing document including packing list, weather forecast, local tips, and logistics. Use when the user asks for a complete travel guide, trip planning, travel brief, or wants to fully prepare for a trip.
---

## When to use this skill

Use this skill when the user:
- Asks for a complete travel brief or travel guide
- Wants comprehensive trip preparation
- Says "help me plan my trip" or "prepare me for my trip"
- Needs more than just a packing list

## How to use this skill

### Step 1: Gather Basic Information

Ask the user for:
1. **Destination(s)** — Where are you traveling?
2. **Dates** — When are you going? (specific dates help with weather)
3. **Duration** — How many days?
4. **Purpose** — Business, leisure, adventure, mixed?
5. **Health concerns** — Any conditions to account for?

### Step 2: Generate Packing List

**First, invoke the `travel-packing-list` skill** to generate the packing section.

Load the skill from `~/.claude/skills/travel-packing-list/SKILL.md` and follow its instructions to create a personalised packing list based on the user's destination, duration, purpose, and health concerns.

### Step 3: Research Weather

Based on the destination and travel dates:
- Look up typical weather for that time of year
- Note temperature ranges (highs/lows)
- Precipitation likelihood
- Any seasonal considerations (monsoon, hurricane season, etc.)

Present as a simple forecast summary.

### Step 4: Compile Local Tips

Research and include:
- **Transportation** — How to get around (metro, rideshare, walking)
- **Money** — Currency, tipping customs, cash vs card
- **Language** — Key phrases if non-English speaking
- **Cultural norms** — Dress codes, etiquette, customs
- **Safety** — Areas to avoid, common scams, emergency numbers
- **Food & drink** — Local specialties, water safety, dietary options

### Step 5: Logistics Checklist

Include practical reminders:
- [ ] Passport valid 6+ months?
- [ ] Visa required?
- [ ] Travel insurance?
- [ ] Notify bank of travel?
- [ ] Phone plan / international roaming?
- [ ] Accommodation confirmed?
- [ ] Transportation booked?
- [ ] Emergency contacts shared?
- [ ] Copies of documents (physical + digital)?

### Step 6: Assemble the Brief

Load `references/brief-sections.md` for the output format.

Combine all sections into a single comprehensive document.

## Output Format

The travel brief should be organised as:

1. **Trip Overview** — Destination, dates, purpose
2. **Weather Forecast** — What to expect
3. **Packing List** — (from travel-packing-list skill)
4. **Local Tips** — Transportation, money, culture, safety
5. **Logistics Checklist** — Pre-departure tasks
6. **Emergency Info** — Important contacts and numbers

## Keywords

travel brief, trip planning, travel guide, prepare for trip, complete travel plan, trip preparation, travel document

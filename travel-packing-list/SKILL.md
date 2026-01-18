---
name: travel-packing-list
description: Creates personalised packing lists based on destination, duration, and trip purpose. Use when the user asks for help packing, creating a packing list, preparing for a trip, or mentions travel planning.
---

## When to use this skill

Use this skill when the user:
- Asks for a packing list
- Needs help preparing for a trip
- Mentions packing for travel
- Wants to know what to bring on a trip

## How to use this skill

### Step 1: Gather Information

Before generating a packing list, **always ask the user** for these essential details:

1. **Destination** — Where are you traveling to?
2. **Duration** — How many days/nights?
3. **Purpose** — Business, leisure, or mixed?

Optional follow-up questions based on context:
- Any planned activities? (hiking, swimming, formal dinners)
- Will you have laundry access?
- Any specific concerns? (medications, electronics)
- Any known health conditions or allergies?

### Step 2: Load Reference

Load `references/packing-categories.md` for comprehensive packing categories and climate considerations.

### Step 3: Generate Personalised List

Based on the user's answers:
1. Determine climate-appropriate clothing
2. Adjust quantities based on duration and laundry access
3. Include purpose-specific items (business attire, leisure gear)
4. Add destination-specific essentials (adapters, visa docs)
5. Include health and safety items based on destination risks

### Step 4: Present the List

Organise the list by category:
- Clothing
- Toiletries
- Electronics
- Documents
- Health & Safety
- Miscellaneous

### Step 5: Health Risks & Vaccination Suggestions

Based on the destination, provide:
- Recommended vaccinations (check CDC/WHO guidelines)
- Common health risks for the region (mosquito-borne illness, altitude sickness, water safety)
- Suggested health items to pack (antimalarials, water purification, insect repellent)

## Example Interaction

**User:** Help me pack for my trip

**Claude:** I'd be happy to help you create a packing list! Let me ask a few questions:

1. **Where are you traveling to?**
2. **How many days will you be gone?**
3. **What's the purpose of your trip?** (business, leisure, or mixed)

**User:** Going to Tokyo for 10 days, mostly leisure but one business meeting

**Claude:** Great! A 10-day trip to Tokyo with mostly leisure and one business meeting. Let me create a personalised list...

*[Generates climate-appropriate list for Tokyo's current season, includes one business outfit, comfortable walking shoes for sightseeing, and Japan-specific items like pocket wifi recommendation and cash for smaller shops]*

**Health & Vaccination Notes for Japan:**
- No special vaccinations required for most travellers
- Routine vaccinations should be up to date
- Japan has excellent healthcare; travel insurance recommended
- Pack any regular medications with original packaging

## Keywords

packing list, travel packing, what to pack, trip preparation, pack for vacation, travel checklist, suitcase, luggage, vaccinations, travel health

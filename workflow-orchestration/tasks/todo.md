# Fix Ad_Orders Table Field Options

## Problem
CSV import polluted singleSelect fields with garbage data (dollar amounts, random text, section names added as dropdown options).

## Affected Fields
- [ ] **Ad Type** - Has $136K, $195K values mixed in
- [ ] **Production Status** - Has dollar amounts, "PRIME POSITION", "DISPLAY"
- [ ] **Ad Size** - Has dollar amounts, "x", section names
- [ ] **Guaranteed Position** - Has 100+ junk values

## Strategy
Since MCP `update_field` only updates name/description (not options), we must:
1. Delete the polluted fields
2. Recreate them with correct options only

## Execution Plan

### Phase 1: Document Current Field IDs
- Ad Type: `fld095CGuaWc0enaY`
- Production Status: `fldDwdz9wgqdf2UNH`
- Ad Size: `fldLImpv0UKT3LTBp`
- Guaranteed Position: `fldI81qaz6lKtDVZr`
- Artwork Status: `fldymEJd8kmt0RXkE` (looks OK, keep)
- Ad Status: `fldP42LqSNmPug9Q9` (looks OK, keep)

### Phase 2: Create NEW fields with correct options
- [ ] Create `Ad Type (New)` with 5 correct options
- [ ] Create `Production Status (New)` with 7 correct options
- [ ] Create `Ad Size (New)` with 25 correct options
- [ ] Create `Guaranteed Position (New)` with 6 correct options

### Phase 3: User deletes old fields in Airtable UI
(Cannot delete fields via MCP API)

### Phase 4: Rename new fields
- [ ] Rename `Ad Type (New)` → `Ad Type`
- [ ] Rename `Production Status (New)` → `Production Status`
- [ ] Rename `Ad Size (New)` → `Ad Size`
- [ ] Rename `Guaranteed Position (New)` → `Guaranteed Position`

## Correct Options Reference

### Ad Type
1. Display
2. Advertorial
3. Enhanced Listing
4. Presenting Sponsorship
5. Web Ad

### Production Status
1. New Entry
2. Awaiting Jay Approval
3. In Production
4. Client has proof
5. Client has changes
6. Responded w/CR
7. Ad Done

### Ad Size (Print)
1. Full Page
2. 2/3 Vertical
3. 1/2 Horizontal
4. 1/2 Vertical
5. 1/2 Island
6. 1/3 Square
7. 1/3 Vertical
8. 1/3 Horizontal
9. 1/4 Square
10. 1/4 Vertical
11. 1/6 Page
12. 1/8 Horizontal
13. 1/12 Page
14. 2 Page Spread
15. 4 Page Spread
16. 5 Page Spread
17. 6 Page Spread
18. Full Page + 1/2 Vertical
19. Full Page + 1/3 Vertical

### Ad Size (Digital)
20. 300 x 250
21. 300 x 600
22. 800 x 150
23. 1161 x 250
24. 728 x 90
25. 1000 x 1000

### Guaranteed Position
1. Back Cover
2. Inside Front Cover
3. Inside Back Cover
4. Page 3
5. Far Forward
6. Run of Book

---
## Review
(To be completed after execution)

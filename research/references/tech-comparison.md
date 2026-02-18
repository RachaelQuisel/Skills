# Technology Comparison Research

## Research Checklist

1. **Define requirements** - What must it do?
2. **Identify candidates** - 2-4 options max
3. **Research each independently** - Avoid bias
4. **Compare on consistent criteria** - Same rubric
5. **Consider total cost** - Time, money, maintenance

## Comparison Criteria

### Functionality
- Does it do what you need?
- Missing features?
- Overkill features?

### Integration
- Works with existing stack?
- API quality?
- Community connectors?

### Cost
- Free tier limits
- Pricing at scale
- Hidden costs (support, plugins)

### Maintenance
- Learning curve
- Documentation quality
- Community support
- Update frequency

## Subagent Prompts

Deploy in parallel for each option:

```
"[Tool A] features overview 2025"
"[Tool A] vs [Tool B] comparison"
"[Tool A] pricing tiers"
"[Tool A] limitations drawbacks"
```

## Comparison Matrix Template

```
| Criteria      | Tool A | Tool B | Tool C |
|---------------|--------|--------|--------|
| Core feature  | Y/N    | Y/N    | Y/N    |
| Integration   | Good   | Fair   | Good   |
| Free tier     | X req  | Y req  | Z req  |
| Learning      | Easy   | Medium | Hard   |
```

## Output Template

```
## Options Evaluated
1. [Tool A] - [One-line summary]
2. [Tool B] - [One-line summary]

## Comparison Matrix
[Table above]

## Recommendation
[Winner] because [reasons]

## Trade-offs
- Choosing [X] means [trade-off]
```

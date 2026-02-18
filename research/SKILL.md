---
name: research
description: Conducts thorough research using subagents for API integrations, data processing, debugging, and technical documentation. Use when the user asks to research, investigate, find, look up, compare, or understand technologies, APIs, error messages, or integration approaches. Triggers on phrases like "research this", "find out how", "what's the best way to", "help me understand", or "investigate why".
---

# Research Skill

Orchestrate systematic research using parallel subagents to gather comprehensive information efficiently.

## Core Workflow

1. **Clarify the research question** - Understand what's being asked
2. **Decompose into parallel tracks** - Break research into independent queries
3. **Deploy subagents** - Launch focused research agents in parallel
4. **Synthesize findings** - Combine results into actionable insights
5. **Present with sources** - Always cite where information came from

## Research Values

- **Depth over speed** - Thorough understanding beats quick answers
- **Multiple sources** - Cross-reference findings when possible
- **Practical focus** - Research should lead to actionable solutions
- **Honest uncertainty** - Clearly state when information is unclear or conflicting

## When to Use Subagents

Deploy subagents for:
- Exploring codebases (`subagent_type: Explore`)
- Web searches for documentation
- Parallel investigation of multiple technologies
- Comparing different approaches

## Research Categories

### API & Integration Research
When researching APIs or integrations, read `references/api-research.md`.

### Data Processing Research
When researching CSV, PDF, or data transformation, read `references/data-processing.md`.

### Debugging & Error Research
When investigating errors or bugs, read `references/debugging.md`.

### Technology Comparison
When comparing tools or approaches, read `references/tech-comparison.md`.

## Output Format

```
## Research Summary
[Key findings in 2-3 sentences]

## Details
[Organized findings by topic]

## Recommendations
[Actionable next steps]

## Sources
- [Source 1](url)
- [Source 2](url)
```

## Example Usage

User: "Research how to connect Airtable to Wix"

Agent response:
1. Deploy subagent to search Airtable API docs
2. Deploy subagent to search Wix Velo documentation
3. Deploy subagent to find integration examples
4. Synthesize into recommendation with code examples

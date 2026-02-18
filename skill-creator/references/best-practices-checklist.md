# Best Practices Checklist

Use this checklist when creating or reviewing skills.

## Structure and Size

- [ ] Keep SKILL.md under 500 lines (<5000 tokens)
- [ ] SKILL.md starts with `---` on line 1 (no blank lines before YAML)
- [ ] Use spaces, not tabs, in YAML
- [ ] Directory name matches the `name` field exactly

## Descriptions

- [ ] Description answers "when would this activate?"
- [ ] Include action verbs (extracts, generates, converts)
- [ ] Include specific file types or formats
- [ ] List concrete use cases
- [ ] Include keywords the user might say
- [ ] Stay under 1024 characters
- [ ] Keep descriptions distinct to avoid collisions between skills
- [ ] Test with various trigger phrasings

## Instructions

- [ ] Include examples of expected input/output in SKILL.md
- [ ] Write instructions that tell the agent when to read each reference
- [ ] Use imperative/infinitive form

## References

- [ ] Keep references one level deep (no chains A → B → C)
- [ ] All references link directly from SKILL.md
- [ ] Keep reference files focused and small
- [ ] Use for detailed documentation, not core instructions
- [ ] For files >100 lines, include table of contents at top

## Scripts

- [ ] Provide clear error messages with solutions
- [ ] Test scripts by actually running them
- [ ] Delete example files not needed for the skill

## Testing

- [ ] Test skills with various trigger phrasings
- [ ] Verify references load correctly
- [ ] Check scripts execute without errors
- [ ] Iterate based on real usage

## Common Mistakes to Avoid

- Wrong filename: `SKILLS.md` instead of `SKILL.md`
- Wrong case: `skill.md` instead of `SKILL.md`
- Bad YAML indentation (tabs instead of spaces)
- Directory name doesn't match `name` field
- Blank line before YAML frontmatter
- "When to use" info in body instead of description
- Deeply nested reference chains

## The Skill Development Mindset

- **Start simple** - First version doesn't need every feature
- **Show don't tell** - Work through tasks collaboratively, then create skills from successful approaches
- **Think from agent's perspective** - How will it know when to use this? What info does it need?
- **Monitor and iterate** - Watch real performance, refine based on observations

# Skills

A library of **AI agent skills**—modular, self-contained instruction bundles that can be reused across multiple tools (Cursor, Claude Code, Gemini CLI, Codex, etc.).

Each skill lives in its own folder and contains a `SKILL.md` plus optional `references/`, `scripts/`, and `examples/`.

This repo follows the **Agent Skills** pattern so the same skill folders can be symlinked/copied into different agents’ “skills” directories.

## What this repo is for

- **Teach the agent how to work**: `explore-first` → `create-plan` → `execute`, plus `review`, `create-issue`, `workflow-orchestration`.
- **Domain expertise**: research workflows, internal comms, etc.
- **Project-specific guardrails**: e.g. `vibe-safe*`, travel workflows.
- **Meta**: `skill-creator` to generate + validate new skills.

Agents typically use the **name + description** frontmatter in `SKILL.md` to decide when to load a skill; the body and referenced files are loaded when the skill triggers.

## Skills in this repo

| Skill | Purpose |
|-------|---------|
| **explore-first** | Understand codebase and requirements before implementing |
| **create-plan** | Produce a markdown execution plan with status tracking |
| **execute** | Implement the plan step by step |
| **workflow-orchestration** | Plan-first, verification, lessons, subagents for non-trivial tasks |
| **review** | Code review checklist and output format |
| **create-issue** | Fast capture of bugs/features mid-development |
| **explain-code** | Explain code to the user |
| **peer-review** | Peer review workflow |
| **research** | Research using subagents (APIs, data, debugging, comparisons) |
| **internal-comms** | Internal comms (3P updates, newsletters, FAQs, etc.) |
| **skill-creator** | Create and package new skills (init, edit, package) |
| **vibe-safe** (+ auth, errors, upload) | Secure API development (RAILGUARD, validation, auth, errors); related skills installed together |
| **travel-brief** / **travel-packing-list** | Travel prep workflows |

## Quickstart

Clone this repo somewhere stable:

```bash
git clone <this-repo-url> ~/src/skills
cd ~/src/skills
```

Then set a reusable environment variable (optional, but makes commands copy/paste-friendly):

```bash
export SKILLS_REPO="$(pwd)"
```

On macOS/Linux you can add that export to your shell profile (e.g. `~/.zshrc`).

## Using these skills in different tools

### Cursor

Cursor discovers skills in either:

- `~/.cursor/skills/<skill-name>/` (global)
- `.cursor/skills/<skill-name>/` (per-project)

#### Global install

From the repo root:

```bash
SKILLS_REPO="${SKILLS_REPO:-$(pwd)}"
mkdir -p "$HOME/.cursor/skills"

for s in explore-first create-plan execute workflow-orchestration review create-issue research internal-comms explain-code peer-review vibe-safe vibe-safe-auth vibe-safe-errors vibe-safe-upload travel-brief travel-packing-list skill-creator; do
  # -n: do not dereference, -f: replace, -s: symlink
  ln -sfn "$SKILLS_REPO/$s" "$HOME/.cursor/skills/$s"
done
```

#### Per-project install

```bash
SKILLS_REPO="${SKILLS_REPO:-$(pwd)}"
mkdir -p .cursor/skills
ln -sfn "$SKILLS_REPO/workflow-orchestration" .cursor/skills/workflow-orchestration
ln -sfn "$SKILLS_REPO/review" .cursor/skills/review
```

### Claude Code (Anthropic)

Claude Code supports skills and treats them as slash commands (e.g. `/review`). Skills live in:

- `~/.claude/skills/<skill-name>/SKILL.md` (global)
- `.claude/skills/<skill-name>/SKILL.md` (per-project)

Install by copying or symlinking each skill folder into one of those locations:

```bash
SKILLS_REPO="${SKILLS_REPO:-$(pwd)}"
mkdir -p ~/.claude/skills
ln -sfn "$SKILLS_REPO/review" ~/.claude/skills/review
ln -sfn "$SKILLS_REPO/explore-first" ~/.claude/skills/explore-first
```

Tip: Claude Code also supports project-level shared context via `CLAUDE.md` (checked into git) and local overrides via `.claude/settings.local.json`.

### Gemini CLI (Google)

Gemini CLI supports:

- **Project instructions** via `GEMINI.md`
- **Custom slash commands** stored as files:
  - `~/.gemini/commands/` (global)
  - `.gemini/commands/` (per-project)

A practical pattern is to convert a skill’s core workflow into a Gemini slash command file (e.g. `plan.toml` or another supported format) and keep shared team rules in `GEMINI.md`.

### OpenAI Codex

Codex supports Agent Skills and can install skills into `$CODEX_HOME/skills/`.

If you’re using the Codex CLI/app, you can typically:

- clone this repo
- copy or symlink desired skill folders into `$CODEX_HOME/skills/<skill-name>/`

(If your Codex environment provides a skill installer, prefer that—skills are then tracked and updated more cleanly.)

### “Prompt-only” tools (Claude web, Gemini web, ChatGPT, etc.)

If a tool doesn’t have a native skills directory, you can still reuse this repo:

- Pick a skill and copy the **body** of `SKILL.md` into a “Project instructions / System instructions / Custom GPT” field.
- Keep the skill folder as the source of truth; treat the prompt-only version as a synced copy.

## Structure of a skill

```text
skill-name/
├── SKILL.md          # Required: YAML frontmatter (name, description) + body
├── references/       # Optional: loaded when the skill says to read them
├── scripts/          # Optional: runnable helpers
├── examples/         # Optional: examples (e.g. internal-comms)
└── assets/           # Optional: templates, images (skill-creator pattern)
```

## Creating new skills

See **skill-creator**:

```bash
python3 skill-creator/scripts/init_skill.py <name> --path <dir>
# edit the skill
python3 skill-creator/scripts/package_skill.py <path>
```

---

*Tested on macOS.*

# claude-thinking-tools

Sharper decisions with Claude — tools that **counter its agreeableness** and stress-test your thinking.

- **skill/SKILL.md** — `council`: spawns 5 advisor personas (contrarian, first-principles, optimist, outsider, executor) that pressure-test a decision, then a chair gives a verdict + the hardest truth.
- **commands/** — drop into `~/.claude/commands/`: `/brutal` (no-flattery assessment), `/premortem` (assume it failed, work back), `/redteam` (5 strongest attacks), `/pressure-test` (YC-style fatal-flaw test for an idea).
- **prompts/business-builder.md** — an ordered idea → offer → sales → first-customers prompt chain.

Install commands: `cp commands/*.md ~/.claude/commands/`. The skill: copy `skill/SKILL.md` into a `council/` skill folder.

## Use in Claude chat (claude.ai)

These tools are also packaged as **Agent Skills** under `skills/`, so they work in
**claude.ai**, not just Claude Code:

1. Grab a ready-to-upload zip from `skills/dist/` (one per skill).
2. In claude.ai → **Settings → Capabilities → Skills**, upload the zip (Pro/Max/Team/
   Enterprise). Or add it to a **Project** so it's available in that project's chats.
3. Each skill auto-triggers from its description — e.g. ask *"make this sound human"*
   and the `humanize` skill kicks in; no slash command needed.

In **Claude Code**, copy a skill folder into `~/.claude/skills/` (global) or the
project's `.claude/skills/`. The slash commands in `commands/` remain the quick path there.


---

_Curated/built from techniques shared by creators on Instagram (May 2026); marketing hype and inflated stats stripped out. Prompt text is rewritten, not copied; source handles are credited in the pack files._

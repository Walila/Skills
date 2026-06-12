# Personal Skills

This repository contains reusable agent skills:

- `divergent-thinking`: breaks assumptions and explores unexpected directions before choosing or planning.
- `designing-sessions`: brainstorms ideas or creates complete workshop, talk, presentation, and ideation-session plans.

## Repository Layout

```text
skills/
  divergent-thinking/
    SKILL.md
    agents/openai.yaml
  designing-sessions/
    SKILL.md
    agents/openai.yaml
```

Each skill directory is self-contained. Install the whole directory, not only `SKILL.md`, so platform-specific metadata is preserved.

## Install

Clone or download this repository first:

```bash
git clone git@github.com:Walila/Skills.git skills
cd skills
```

Use the HTTPS URL instead if your environment does not have GitHub SSH access configured.

### ChatGPT

ChatGPT does not use a local skill directory. Use these skills as Custom GPT or Project knowledge:

1. Open ChatGPT.
2. Create or edit a Custom GPT, or open a Project.
3. Upload each skill folder, or upload the two `SKILL.md` files and their matching `agents/openai.yaml` files.
4. Add an instruction telling ChatGPT to follow the relevant skill when the user references `$divergent-thinking` or `$designing-sessions`.

Suggested instruction:

```text
When the user references $divergent-thinking, follow the Divergent Thinking skill.
When the user references $designing-sessions, follow the Designing Sessions skill.
```

### Claude Code

Install into the Claude Code user skills directory:

```bash
mkdir -p ~/.claude/skills
cp -R divergent-thinking designing-sessions ~/.claude/skills/
```

Restart Claude Code, or start a new session, then reference the skills by name.

### Codex

Install into the Codex agent skills directory:

```bash
mkdir -p ~/.agents/skills
cp -R divergent-thinking designing-sessions ~/.agents/skills/
```

Restart Codex, or start a new agent session, then reference the skills by name.

### Claude Code Desktop

If Claude Code Desktop runs in the same environment as Claude Code, use the same directory:

```bash
mkdir -p ~/.claude/skills
cp -R divergent-thinking designing-sessions ~/.claude/skills/
```

If the desktop app runs outside WSL or a container, run the commands in the host environment where the desktop app reads its user files.

### Cursor

Install into the Cursor user skills directory:

```bash
mkdir -p ~/.cursor/skills-cursor
cp -R divergent-thinking designing-sessions ~/.cursor/skills-cursor/
```

Reload Cursor or start a new chat after installation.

## Usage

### Divergent Thinking

Use this skill when you want to explore before choosing a direction.

Example prompts:

```text
Use $divergent-thinking to generate unexpected directions for a Tech Day theme.
```

```text
Use $divergent-thinking to challenge assumptions behind our onboarding process.
```

Good fit:

- Early-stage exploration
- Assumption breaking
- Unusual angles
- Product, process, workshop, retrospective, teaching, or team-activity ideas

Avoid using it when you already need ranking, planning, agenda design, or final recommendations.

### Designing Sessions

Use this skill when you want to brainstorm or design a session.

Example prompts:

```text
Use $designing-sessions to brainstorm 20 workshop ideas about incident review culture.
```

```text
Use $designing-sessions to create a complete 60-minute team workshop about improving code review.
```

Good fit:

- Workshop design
- Talk or presentation planning
- Facilitated ideation
- Mixed speaking-and-activity sessions
- Complete timed session plans

Use Fast Start for rough ideas. Use Complete Design when you need a ready-to-run plan.

## Quick Smoke Test

After installation, start a new agent session and try:

```text
Use $divergent-thinking to rethink how a team retrospective could work.
```

Then try:

```text
Use $designing-sessions to create a fast-start list of workshop ideas for technical onboarding.
```

The first response should avoid ranking or final decisions. The second response should provide workshop or talk ideas and ask what direction to develop next.

# Personal Skills

This repository contains reusable agent skills:

- `divergent-thinking`: breaks assumptions and explores unexpected directions before choosing or planning.
- `designing-sessions`: brainstorms ideas or creates complete workshop, talk, presentation, and ideation-session plans.
- `structured-divergence`: explores traceable possibilities by transforming problem-specific surfaces with explicit methods.

## Repository Layout

```text
skills/
  divergent-thinking/
    SKILL.md
    agents/openai.yaml
  designing-sessions/
    SKILL.md
    agents/openai.yaml
  structured-divergence/
    SKILL.md
    methods.md
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
3. Upload each complete skill folder, including supporting files such as `methods.md`.
4. Add an instruction telling ChatGPT to follow the relevant skill when the user references its `$skill-name`.

Suggested instruction:

```text
When the user references $divergent-thinking, follow the Divergent Thinking skill.
When the user references $designing-sessions, follow the Designing Sessions skill.
When the user references $structured-divergence, follow the Structured Divergence skill.
```

### Claude Code

Install into the Claude Code user skills directory:

```bash
mkdir -p ~/.claude/skills
cp -R divergent-thinking designing-sessions structured-divergence ~/.claude/skills/
```

Restart Claude Code, or start a new session, then reference the skills by name.

### Codex

Install into the Codex agent skills directory:

```bash
mkdir -p ~/.agents/skills
cp -R divergent-thinking designing-sessions structured-divergence ~/.agents/skills/
```

Restart Codex, or start a new agent session, then reference the skills by name.

### Claude Code Desktop

If Claude Code Desktop runs in the same environment as Claude Code, use the same directory:

```bash
mkdir -p ~/.claude/skills
cp -R divergent-thinking designing-sessions structured-divergence ~/.claude/skills/
```

If the desktop app runs outside WSL or a container, run the commands in the host environment where the desktop app reads its user files.

### Cursor

Install into the Cursor user skills directory:

```bash
mkdir -p ~/.cursor/skills-cursor
cp -R divergent-thinking designing-sessions structured-divergence ~/.cursor/skills-cursor/
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

### Structured Divergence

Use this skill when you want explicit, reusable transformations rather than a
flat idea list.

Example prompt:

```text
Use $structured-divergence to rethink how a platform engineering team defines
success. Challenge the frame without choosing a final direction.
```

Good fit:

- Method-transparent brainstorming
- SCAMPER-style transformations without fixed checklist coverage
- Problem-specific transformation surfaces
- Diverse exploration portfolios before convergence

Avoid using it for comparisons, final recommendations, implementation plans,
or execution.

## Quick Smoke Test

After installation, start a new agent session and try:

```text
Use $divergent-thinking to rethink how a team retrospective could work.
```

Then try:

```text
Use $designing-sessions to create a fast-start list of workshop ideas for technical onboarding.
```

Finally try:

```text
Use $structured-divergence to rethink what an intern retrospective is for.
```

The first response should avoid ranking or final decisions. The second should
provide workshop or talk ideas and ask what direction to develop next. The
third should expose transformation surfaces, methods, traceable directions,
and a non-ranked exploration portfolio.

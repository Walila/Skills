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

ChatGPT on the web does not currently install Agent Skills directories or
`SKILL.md` packages directly. Use a Custom GPT for the closest reusable
equivalent:

1. Open **Explore GPTs > Create** in ChatGPT on the web.
2. Copy the behavioral content from `SKILL.md` into the GPT's
   **Instructions**.
3. Upload supporting reference files such as `methods.md` under
   **Knowledge**.
4. Test the GPT in Preview, then save it.

Create a separate GPT for each skill unless you deliberately want one GPT to
combine all three workflows. GPT creation and editing require a paid plan or
workspace permission.

A ChatGPT Project can also hold project instructions and uploaded reference
files, but those instructions apply only inside that project. Uploading
`SKILL.md` as a project file does not register it as an invocable skill.

Official documentation: [Creating and editing GPTs](https://help.openai.com/en/articles/8554397)
and [Projects in ChatGPT](https://help.openai.com/en/articles/10169521)

### Claude Code

Claude Code stores its general configuration under `~/.claude/`. The personal
skills directory is `~/.claude/skills/`; it is normal for this subdirectory not
to exist until you create your first skill.

On Linux, macOS, or WSL:

```bash
mkdir -p ~/.claude/skills
cp -R divergent-thinking designing-sessions structured-divergence ~/.claude/skills/
```

On native Windows PowerShell:

```powershell
New-Item -ItemType Directory -Force "$HOME\.claude\skills"
Copy-Item -Recurse divergent-thinking, designing-sessions, structured-divergence "$HOME\.claude\skills\"
```

Claude Code detects changes inside an existing skills directory automatically.
Restart Claude Code if the top-level `skills` directory was created after the
session started.

Official documentation: [Claude Code skills](https://code.claude.com/docs/en/skills)

### Codex

Codex supports two personal skill locations:

- `~/.codex/skills/`: Codex-native location and the default destination used
  by its built-in `$skill-installer`.
- `~/.agents/skills/`: cross-agent location that can also be shared with
  Cursor.

Use `~/.codex/skills/` when the skills are only for Codex. Use
`~/.agents/skills/` when you want one installation shared by supporting tools.

On Linux, macOS, or WSL:

```bash
mkdir -p ~/.codex/skills
cp -R divergent-thinking designing-sessions structured-divergence ~/.codex/skills/
```

On native Windows PowerShell:

```powershell
New-Item -ItemType Directory -Force "$HOME\.codex\skills"
Copy-Item -Recurse divergent-thinking, designing-sessions, structured-divergence "$HOME\.codex\skills\"
```

For project-only installation, copy the directories to `.agents/skills/` in
the repository instead. Codex detects skill changes automatically; restart it
only if a new skill does not appear.

Codex can also install the skills directly from GitHub. Ask Codex:

```text
Use $skill-installer to install these paths from Walila/Skills:
divergent-thinking, designing-sessions, and structured-divergence.
```

The built-in installer downloads each directory into `$CODEX_HOME/skills`,
which defaults to `~/.codex/skills/`.

Official documentation: [Codex Agent Skills](https://developers.openai.com/codex/skills)

### Claude.ai and Claude Desktop

Claude.ai and the Claude Desktop app use account-level skills rather than the
local `~/.claude/skills/` directory used by Claude Code:

1. Create one ZIP file for each complete skill directory.
2. Open **Customize > Skills**.
3. Click **+ > Create skill > Upload a skill**.
4. Upload the ZIP file and enable the skill.

The same account-level skills are available in supported Claude surfaces. They
are not installed by copying files into the Desktop application's local data
directory.

Official documentation: [Use skills in Claude](https://support.claude.com/en/articles/12512180-use-skills-in-claude)

### Cursor

Cursor supports both `~/.cursor/skills/` and the cross-agent
`~/.agents/skills/` directory. If these skills are already installed for Codex
under `~/.agents/skills/`, Cursor can use the same installation and no second
copy is needed.

Do not install custom skills into `~/.cursor/skills-cursor/`. Cursor creates
and updates that directory for its built-in and managed skills.

Cursor-specific installation on Linux, macOS, or WSL:

```bash
mkdir -p ~/.cursor/skills
cp -R divergent-thinking designing-sessions structured-divergence ~/.cursor/skills/
```

On native Windows PowerShell:

```powershell
New-Item -ItemType Directory -Force "$HOME\.cursor\skills"
Copy-Item -Recurse divergent-thinking, designing-sessions, structured-divergence "$HOME\.cursor\skills\"
```

On native Windows, `$HOME` normally resolves to
`C:\Users\<username>`. When Cursor is operating in WSL, install in the Linux
home directory used by that WSL environment instead.

Cursor also discovers project skills from `.cursor/skills/` or
`.agents/skills/`. View detected skills under **Cursor Settings > Rules**.

Cursor can import content from GitHub through **Cursor Settings > Rules > Add
Rule > Remote Rule (GitHub)**. For this repository, which contains multiple
skills, cloning the repository and copying the three skill directories remains
the most explicit installation method.

Official documentation: [Cursor Agent Skills](https://cursor.com/docs/skills)

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

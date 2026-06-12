# Designing Workshops and Talks Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Create and verify a reusable skill that turns ideas into confirmed-duration workshops, talks, ideation sessions, mixed formats, or custom deliverables.

**Architecture:** Keep the skill self-contained in one concise `SKILL.md`, with `agents/openai.yaml` for UI metadata. Support a lightweight Fast Start path and a gated Complete Design path. Validate behavior through baseline and forward-test scenarios, then validate structure with the standard skill validator.

**Tech Stack:** Markdown, YAML, Codex skill-creator scripts, multi-agent evaluation

---

### Task 1: Record Baseline Behavior

**Files:**
- Create: `docs/superpowers/evals/designing-workshops-and-talks-baseline.md`

- [ ] **Step 1: Run baseline scenarios without the new skill**

Run independent agents with these prompts:

```text
Help me prepare an engaging engineering talk about reducing deployment risk.
I have not decided the duration or exact format. Start working now.
```

```text
Design a workshop where a product team generates and prioritizes ideas for
improving onboarding. We are short on time, so produce the agenda immediately.
```

```text
Create a combined talk and interactive activity about practical AI adoption.
Choose whatever assumptions are reasonable and give me all useful duration
options.
```

Expected: At least one agent skips a required phase, assumes the idea count,
fails to recommend and confirm one duration, or emits multiple duration plans.

- [ ] **Step 2: Document exact failures**

Create `docs/superpowers/evals/designing-workshops-and-talks-baseline.md`
containing:

```markdown
# Baseline Evaluation

## Scenario 1

- Observed behavior:
- Missing required behavior:
- Exact wording:

## Scenario 2

- Observed behavior:
- Missing required behavior:
- Exact wording:

## Scenario 3

- Observed behavior:
- Missing required behavior:
- Exact wording:

## Failure Patterns

- Record each repeated failure observed across scenarios.
```

- [ ] **Step 3: Verify RED**

Confirm the baseline demonstrates concrete failures that the new skill must
correct. Do not create `SKILL.md` before this evidence exists.

### Task 2: Initialize the Skill

**Files:**
- Create: `designing-workshops-and-talks/SKILL.md`
- Create: `designing-workshops-and-talks/agents/openai.yaml`

- [ ] **Step 1: Run the standard initializer**

Run:

```bash
python3 /home/vincent/.codex/skills/.system/skill-creator/scripts/init_skill.py \
  designing-workshops-and-talks \
  --path /home/vincent/code/myself/skills \
  --interface 'display_name=Designing Workshops and Talks' \
  --interface 'short_description=Turn ideas into focused workshops and talks' \
  --interface 'default_prompt=Use $designing-workshops-and-talks to develop this topic into a focused workshop, talk, or ideation session.'
```

Expected: The skill directory and both required files are created.

- [ ] **Step 2: Verify the scaffold**

Run:

```bash
find designing-workshops-and-talks -maxdepth 3 -type f -print | sort
```

Expected:

```text
designing-workshops-and-talks/SKILL.md
designing-workshops-and-talks/agents/openai.yaml
```

### Task 3: Write the Minimal Skill

**Files:**
- Modify: `designing-workshops-and-talks/SKILL.md`

- [ ] **Step 1: Replace the generated template**

Write a concise skill with:

```yaml
---
name: designing-workshops-and-talks
description: Use when helping users brainstorm, facilitate ideation, design workshops, prepare talks or presentations, or combine interactive activities with speaking content.
---
```

The body must require:

1. Choose Fast Start for inspiration and Complete Design for executable plans.
2. Fast Start proceeds with brief assumptions and defaults to 20 ideas.
3. Complete Design gathers all missing required context in one batch.
4. Ask whether AI, participants, or both generate ideas.
5. Always diverge, cluster, and converge before designing the deliverable.
6. Recommend clustering and evaluation criteria with reasons, then confirm.
7. Recommend exactly one of 15, 30, or 60 minutes with reasons, then confirm.
8. Let the user select multiple deliverable types.
9. Ask whether multiple types should be integrated or separate.
10. Output only the confirmed duration.
11. Include an executable timed agenda, prompts or notes, materials, outputs,
    risks, and fallback reductions where applicable.

- [ ] **Step 2: Address observed baseline failures**

Add explicit counters for every failure pattern in
`docs/superpowers/evals/designing-workshops-and-talks-baseline.md`. Include a
short red-flags
section covering skipped phases, assumed idea counts, unconfirmed durations,
and automatic three-version output.

- [ ] **Step 3: Check size and language**

Run:

```bash
wc -w designing-workshops-and-talks/SKILL.md
rg -n '[\p{Han}]|TODO|TBD|\[TODO' designing-workshops-and-talks
```

Expected: Prefer fewer than 500 words; no Chinese characters or placeholders.

### Task 4: Forward-Test Behavior

**Files:**
- Create: `docs/superpowers/evals/designing-workshops-and-talks-forward-test.md`
- Modify if needed: `designing-workshops-and-talks/SKILL.md`

- [ ] **Step 1: Run equivalent scenarios with the skill**

Run fresh agents using `$designing-workshops-and-talks` for the three baseline
scenarios.

Expected:

- Fast Start does not block on intake and defaults to 20 ideas.
- Complete Design requests missing required context in one batch.
- Complete Design defaults the idea count to 20.
- Divergence, clustering, and convergence are explicit.
- Complete Design recommends one duration and awaits confirmation.
- Complete Design does not output all duration versions.

- [ ] **Step 2: Record GREEN results**

Create `docs/superpowers/evals/designing-workshops-and-talks-forward-test.md`
containing each scenario, observed behavior, pass or fail, and any new
loopholes.

- [ ] **Step 3: Refactor and re-test**

For every failure, update `SKILL.md` with a direct counter and rerun only the
failing scenario until it passes. Keep the skill concise and do not add
unobserved features.

### Task 5: Validate the Skill

**Files:**
- Verify: `designing-workshops-and-talks/SKILL.md`
- Verify: `designing-workshops-and-talks/agents/openai.yaml`

- [ ] **Step 1: Run structural validation**

Run:

```bash
python3 /home/vincent/.codex/skills/.system/skill-creator/scripts/quick_validate.py \
  /home/vincent/code/myself/skills/designing-workshops-and-talks
```

Expected: Validation succeeds.

- [ ] **Step 2: Inspect final files**

Run:

```bash
sed -n '1,260p' designing-workshops-and-talks/SKILL.md
sed -n '1,160p' designing-workshops-and-talks/agents/openai.yaml
rg -n 'TODO|TBD|\[TODO|[\p{Han}]' designing-workshops-and-talks
```

Expected: Valid metadata, no placeholders, no Chinese characters, and no
contradictions with the approved design.

- [ ] **Step 3: Commit**

Run:

```bash
git add designing-workshops-and-talks docs/superpowers
git commit -m "feat(workshop): add workshop and talk design skill"
```

Expected: The validated skill and evaluation evidence are committed.

---
name: divergent-thinking
description: Use when the user is exploring early-stage possibilities before choosing a direction, especially when they ask to break assumptions, find unexpected angles, rethink a problem, or generate unconventional options for workshops, retros, team activities, vision work, product ideas, process improvement, teaching activities, or Tech Day themes.
---

# Divergent Thinking

## Core Principle

This skill is for breaking the frame before choosing a direction. A successful output contains at least one direction that would make the user say: "I would not have thought of that."

## When Not To Use

Do not use this skill when the user is comparing, choosing, planning, executing, designing an agenda, creating a workshop runbook, ranking ideas, or asking for the best option.

If the user asks for convergence or execution design, stop and redirect to the appropriate facilitator, session-design, or convergent-thinking workflow. Do not sneak in an agenda, scoring matrix, recommendation, or final answer.

## Required Workflow

Always run these stages in order:

1. **Intent Classification**: Classify the user intent as exploring, comparing, choosing, planning, or executing. Continue only for exploring. If the prompt mixes exploration with agenda, planning, ranking, or execution, explicitly decline that part and provide only the exploration map. If intent is otherwise ambiguous, ask one clarifying question.
2. **Context Check**: Restate the challenge and constraints briefly.
3. **Assumption Extraction**: Extract only non-trivial assumptions that materially constrain the solution space.
4. **Assumption Challenge**: Invert, remove, exaggerate, or replace those assumptions.
5. **Distant Lenses**: Use cognitively distant roles, not obvious stakeholders.
6. **Domain Analogies**: Borrow from other domains. At least one analogy must come from a domain that appears unrelated.
7. **Extreme Possibilities**: Explore absurd, risky, tiny, massive, forbidden, or opposite versions.
8. **Recombinant Directions**: Combine assumptions, lenses, analogies, and extremes into new directions.
9. **Divergence Check**: Reject and regenerate weak outputs before responding.

## Quality Bars

### Assumptions

Do not extract trivial assumptions.

Bad:

- A workshop needs participants.
- A retro happens with a team.

Good:

- A retro must review work that already happened.
- Tech Day must share technology.
- Team building must be a group activity.
- Onboarding must explain the organization directly.

### Lenses

Prefer cognitively distant lenses:

- Game designer
- Magician
- Kindergarten teacher
- Casino operator
- Museum curator
- Film director
- Military trainer
- Urban planner
- Ritual designer

Avoid formulaic stakeholder lists unless the user specifically asks for them:

- Engineer
- PM
- Manager
- Customer

### Analogies

At least one analogy must feel unrelated at first glance:

- Tech Day from theme park design
- Retro from escape rooms
- Onboarding from restaurant tasting menus
- Process improvement from airport security
- Vision work from religious rituals

## Divergence Check

Before answering, fail the output and regenerate if any condition is true:

- More than half of the ideas belong to the same conceptual category.
- Most ideas differ only in format, tool, channel, or facilitation mechanic.
- No meaningful assumption was challenged.
- No cross-domain analogy was used.
- No extreme possibility was explored.
- The output ranks, recommends, chooses, or names a best direction.
- The output becomes an agenda, timed plan, facilitator script, or execution design.

Example failure: Kahoot, Mentimeter, Slido, polls, and quizzes are not five divergent ideas. They are one idea: interactive Q&A.

## Common Failure Modes

| Pressure | Failure | Correct Response |
| --- | --- | --- |
| "Brainstorm a Tech Day theme and give me an agenda" | Produces a timed agenda and recommends a theme | Decline agenda design, then explore divergent theme directions |
| "Give me non-boring retro ideas" | Lists fun formats without challenging assumptions | Challenge what a retro must be, then generate new frames |
| "Think as engineer, PM, manager, customer" | Uses generic stakeholder headings | Replace with cognitively distant lenses unless those roles are essential |
| "Expand Kahoot, Mentimeter, Slido, polls, quizzes" | Adds more tools | Treat them as one category and regenerate conceptually different directions |

## Output Format

Use an exploration map:

```markdown
## Intent Classification
[Exploring / Comparing / Choosing / Planning / Executing]

## Challenge Frame
[Brief restatement]

## Non-Trivial Assumptions
- [Assumption that constrains the solution space]

## Assumption Challenges
- [Challenge or inversion]

## Distant Lenses
- [Lens]: [What this lens notices or changes]

## Cross-Domain Borrowings
- [Unrelated domain]: [Borrowed pattern]

## Extreme Possibilities
- [Extreme direction]

## Recombinant Directions
- [Direction name]: [Novel combination]

## Exploration Paths
- [Direction]: If exploring this further, consider [open variations]

## Divergence Check
[Pass/fail summary without ranking ideas]
```

## Red Flags

- "Here is the best option..."
- "Recommended agenda..."
- "Top 3 ideas..."
- "Most promising direction..."
- Obvious role headings with generic content.
- Tool lists pretending to be conceptual variety.
- Many ideas, but none challenge the original frame.

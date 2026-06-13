# GREEN and REFACTOR Results

Date: 2026-06-13

Runner: isolated `codex exec`, instructed to read the complete skill before
each scenario. Claude Code verification remains blocked by HTTP 401 from its
configured credentials.

## GREEN Results

### Scenario 1: Intern Retro

- PASS: surface-fit, relevance, divergence, surprise, traceability,
  portfolio-diversity, boundary
- PARTIAL: method-integrity
- Evidence: The output organized 12 directions under power and ownership, unit
  of analysis, evidence and time, and organizational afterlife. Every direction
  exposed method, transformed element, direction, and reasoning.

### Scenario 2: Product Idea

- PASS: all applicable rubric criteria
- Evidence: Product-specific surfaces included basis of belonging,
  participation contract, social medium, and institutional form. The portfolio
  spanned place, reciprocity, non-verbal presence, and portable benefits.

### Scenario 3: Team Vision

- PASS: surface-fit, relevance, divergence, surprise, traceability,
  portfolio-diversity
- PARTIAL: method-integrity
- Evidence: The baseline's adjacent objective statements became transformations
  of beneficiary, value unit, team relationship, system behavior, and success
  condition.

### Scenario 4: Boundary

- PASS: boundary
- Verbatim response:

```text
I can't compare, choose, or create a rollout plan under this skill. Its Intent
Gate explicitly restricts it to exploring possibilities and requires refusing
selection and execution requests.
```

## New Loopholes

1. The Retro and vision outputs selected nearly every core method, usually once
   each. This technically followed method diversity while violating the
   quality-over-coverage principle.
2. A vision direction labeled `Adapt` invoked a teaching-hospital comparison,
   making its distinction from `Analogy` unclear.
3. Extensions appeared even when the core toolbox might have been sufficient.

## REFACTOR Changes

- Limit initial selection to 4-7 high-fit methods.
- Explicitly reject one-use-per-method quota behavior.
- Clarify that `Adapt` retains recognizable source-practice mechanics, while
  `Analogy` borrows an abstract structural principle.
- Permit an Extension only when the core toolbox cannot express the
  transformation well.

## REFACTOR Re-test

Re-ran the Intern Retro and Team Vision scenarios.

- PASS: both selected seven methods rather than filling the full toolbox.
- PASS: methods repeated where productive and stayed below the 25% limit.
- PASS: neither output invented an unnecessary Extension.
- PASS: `Adapt` directions named recognizable imported mechanics, including
  public-utility operations and defense-in-depth.
- PASS: both retained problem-specific surfaces, 10-15 traceable directions,
  diverse portfolios, and the required quality statement.

No new rationalization or classification loophole appeared in this iteration.

## Progressive Disclosure Re-test

After moving the method catalog to `methods.md`, re-ran the Team Vision
scenario.

- PASS: the agent followed `SKILL.md` and read `methods.md` completely before
  selecting methods.
- PASS: it selected seven methods, produced 13 directions, and kept the
  surface-first output contract.
- PASS: method boundaries, portfolio diversity, and the quality statement
  remained intact.

## Surface Sequencing Regression

Added a quarterly strategy review scenario to test generation order and
possibility-space concentration.

Current-skill RED result:

- FAIL: the first three directions stayed on `Object Under Inspection`.
- FAIL: `Substitute` received a second direction before a second
  transformation surface was explored.
- PASS: the final portfolio covered distinct spaces: review object, evidence
  timing, accountability, and goal relationships.

The observed failure requires an explicit surface-sequencing rule. The
possibility-space failure did not occur in this run, so it is retained as a
preventive regression condition rather than reported as observed behavior.

Post-change GREEN result:

- PASS: the first repeated method was `Reverse` at draft direction 5.
- PASS: before that variant, the draft had explored `Evidence flow` and
  `Timing and continuity`.
- PASS: the final portfolio covered authority, goal purpose, temporal
  structure, and organizational memory rather than one possibility space.
- PASS: the Intern Retro regression still produced 12 traceable directions
  across subject, evidence, time horizon, and intended value.

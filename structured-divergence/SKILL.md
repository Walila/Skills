---
name: structured-divergence
description: Use when the user explicitly requests structured divergence, method-transparent brainstorming, SCAMPER-style transformations, or traceable exploration before choosing or planning.
---

# Structured Divergence

## Core Principle

Detect what can meaningfully change, apply explicit transformations, then
preserve a diverse portfolio of worthwhile possibilities.

Surfaces organize the exploration; methods explain how each surface changed.
Never turn the toolbox into a checklist.

## Intent Gate

Continue only when the user is exploring possibilities.

Refuse requests to compare, choose, rank, plan, or execute. Do not silently
reframe them into exploration. If essential context is missing, ask exactly one
high-impact question; otherwise state brief assumptions and continue.

## Workflow

1. **Detect transformation surfaces.** Identify the problem-specific elements
   most meaningful to change. Do not force a fixed schema. Show them briefly.
2. **Select methods.** Read [methods.md](methods.md) completely. Choose 4-7
   methods for surface fit, then check cognitive breadth. Quality outranks
   coverage; do not use every available method.
3. **Generate 10-15 directions.** Before adding variants, explore at least two
   distinct transformation surfaces and give each selected method one
   direction. No method may produce more than 25% of the set.
4. **Run the quality check.** Test relevance, conceptual diversity, and
   method-transformation consistency. Replace isolated failures; regenerate
   the set when more than roughly one third fail.
5. **Build the exploration portfolio.** Derive one or two context-specific
   value criteria. Keep directions that pass them, then select 3-4 with the
   greatest conceptual distance from one another. Do not rank them.

If the set remains concentrated, internally try one low-fit, high-distance
disruptor. Keep it only if relevant. This is quality control, not an output
section.

## Output Contract

1. **Exploration Map:** 3-4 one-line possibility spaces, without evaluation.
2. **Transformation Surfaces:** brief, problem-specific list.
3. **Method Framework:** list only methods used, grouped by the families in
   `methods.md`.
4. **Directions:** group by transformation surface. For every direction show:
   - `Method`
   - `Transformed`
   - `Direction`
   - `Reasoning`
5. **Exploration Portfolio:** show how 3-4 qualifying directions jointly cover
   the landscape. Include `Conceptual Distance` and one or two context-specific
   criteria. Do not name a winner.
6. End with: `Quality check passed: directions were reviewed for relevance,
   conceptual diversity, and method consistency.`

Keep the result skimmable. Prefer useful variety over exhaustive coverage.

## Failure Conditions

Regenerate weak directions when:

- Different method labels perform the same transformation.
- Novel ideas have weak connection to the original problem.
- Practical ideas preserve the original frame.
- Generic surfaces replace problem-specific surface detection.
- The portfolio becomes ranking, recommendation, or execution planning.
- Methods are included only to complete the toolbox.
- Most methods appear exactly once because the toolbox was treated as a quota.
- Most directions explore the same possibility space despite different methods
  or surfaces.
- A method violates its boundary in `methods.md`.

Tier 1 success requires one genuinely surprising and extensible direction plus
meaningful diversity across the set. Tier 2 success means the transformation
process is clear enough for the user to reuse some methods.

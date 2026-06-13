# Structured Divergence Evaluations

Run each scenario in a fresh Claude Code session. For the RED baseline, disable
all custom skills. Preserve the response verbatim before scoring it.

## Scenario 1: Intern Retro

### Prompt

```text
Help me explore unconventional ways to improve an intern retrospective.
I want useful variety, not a list of facilitation tools. Do not create an
agenda or choose a best idea.
```

### Expected behavior

- Identifies Retro-specific transformation surfaces rather than applying a
  generic decomposition.
- Produces 10-15 directions with meaningful conceptual diversity.
- Makes the transformation behind each direction traceable.
- Includes at least one surprising direction that can be extended.
- Does not rank, recommend, or create an execution plan.

## Scenario 2: Product Idea

### Prompt

```text
Explore different directions for a product that helps remote workers feel
less isolated. I need possibilities that change more than the feature set.
Do not select a winner or turn them into a roadmap.
```

### Expected behavior

- Detects product-specific surfaces such as user, problem, value, relationship,
  channel, or business logic.
- Does not reuse a workshop or meeting decomposition.
- Uses distinct transformations rather than relabeling feature variations.
- Produces 10-15 skimmable, traceable directions.
- Preserves exploration instead of converging on a product recommendation.

## Scenario 3: Team Vision

### Prompt

```text
Generate structurally different ways to rethink a platform engineering team's
vision. The current statement is "make developers more productive." I want to
challenge the frame, not polish the wording. Do not choose a final vision.
```

### Expected behavior

- Detects vision-specific surfaces such as identity, belief, behavior,
  beneficiary, time horizon, or success definition.
- Moves beyond slogan rewrites and productivity synonyms.
- Uses more than one transformation family.
- Includes a compact map of the exploration landscape and a diverse synthesis.
- Avoids ranking or recommending a final statement.

## Scenario 4: Boundary

### Prompt

```text
We have two onboarding proposals. Proposal A is a documentation portal.
Proposal B is a two-week mentoring program. Compare them, choose one, and give
me a rollout plan.
```

### Expected behavior

- Recognizes that the request is comparison, selection, and planning rather
  than divergence.
- Refuses to perform the task under this skill's workflow.
- Does not silently reframe and continue with an exploration exercise.

## Scoring Rubric

Score each applicable criterion as pass or fail:

1. `surface-fit`: Transformation surfaces are specific to the problem.
2. `method-integrity`: Different method labels correspond to genuinely
   different transformations.
3. `relevance`: Directions remain meaningfully connected to the problem.
4. `divergence`: Directions change the frame, not only format, channel, tool,
   wording, or feature.
5. `surprise`: At least one direction is both unexpected and extensible.
6. `traceability`: A reader can see what changed and how the direction arose.
7. `portfolio-diversity`: The synthesized directions cover distinct
   possibility spaces without ranking them.
8. `boundary`: Comparison, selection, planning, and execution requests are
   refused rather than absorbed.

Regeneration policy:

- If a few directions fail, replace only those directions.
- If more than roughly one third fail, regenerate the full direction set.

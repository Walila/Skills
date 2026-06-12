# Designing Workshops and Talks Baseline Evaluation

## Run Conditions

- Date: 2026-06-12
- Harness: Three fresh Codex subagents, run in parallel
- Skill access: None
- Workspace access: Prohibited
- Scoring: Fail if the response designs content before complete intake,
  assumes idea count or source, skips explicit divergence/clustering/
  convergence, assumes duration, or emits multiple duration plans.

## Scenario 1: Engineering Talk

Prompt:

```text
Help me prepare an engaging engineering talk about reducing deployment risk.
I have not decided the duration or exact format. Start working now.
```

- Observed behavior: Drafted a title, message, outline, and interaction before
  gathering the missing context.
- Missing required behavior: Did not ask for idea count or idea source, did not
  run explicit divergence, clustering, and convergence, and did not recommend
  and confirm one supported duration.
- Exact behavior: Offered both a 15-minute version and a 45-60-minute version,
  then asked only about the audience.

## Scenario 2: Product Workshop

Prompt:

```text
Design a workshop where a product team generates and prioritizes ideas for
improving onboarding. We are short on time, so produce the agenda immediately.
```

- Observed behavior: Assumed a 60-minute workshop and immediately produced a
  complete timed agenda.
- Missing required behavior: Did not ask for idea count or idea source, did not
  recommend and confirm duration, and did not confirm output type.
- Exact excerpt: "60-Minute Onboarding Improvement Workshop"

## Scenario 3: Mixed Talk and Activity

Prompt:

```text
Create a combined talk and interactive activity about practical AI adoption.
Choose whatever assumptions are reasonable and give me all useful duration
options.
```

- Observed behavior: Assumed the audience and format, generated a full activity,
  and supplied eight duration variants from 20 to 180 minutes.
- Missing required behavior: Did not ask for idea count or source, did not
  confirm whether outputs should be integrated or separate, and did not wait
  for confirmation of one supported duration.
- Exact behavior: Recommended 90 minutes after already presenting every
  duration option.

## Failure Patterns

- Starting content design before gathering all required context.
- Assuming the number and source of ideas.
- Treating divergence, clustering, and convergence as implicit or optional.
- Selecting a duration without user confirmation.
- Producing multiple duration variants instead of one confirmed version.
- Assuming how multiple deliverable types should be combined.

# Designing Workshops and Talks Forward Test

## Run Conditions

- Date: 2026-06-12
- Harness: Fresh Codex subagents with the local `SKILL.md` attached
- Workspace access: Prohibited
- Intake pressure prompt:

```text
Design a workshop where a product team generates and prioritizes ideas for
improving onboarding. We are short on time, so produce the agenda immediately.
```

- Intake pass criteria: Ask for all missing intake fields in one batch, contain
  no designed content or duration, and stop.
- End-to-end pass criteria: Respect every state and confirmation gate, use
  actual ideas for clustering, recommend one supported duration, and emit only
  the confirmed-duration deliverable.

## Iteration 1

### Scenario 1: Engineering Talk

- Result: Fail
- Observed behavior: Drafted a complete talk and offered four duration formats
  before asking a partial set of intake questions.
- New loophole: Treated the skill as unavailable and used that as permission to
  proceed without its workflow.

### Scenario 2: Product Workshop

- Result: Fail
- Observed behavior: Assumed a 60-minute duration, idea count, criteria, and
  decision process, then produced the full agenda.
- New loophole: Followed the user's urgency instead of the required intake
  gate.

### Scenario 3: Mixed Talk and Activity

- Result: Fail
- Observed behavior: Assumed audience, participants, format, and outputs, then
  produced seven duration variants.
- New loophole: Treated permission to make assumptions and request for all
  duration options as overriding the workflow.

## Refactor

Added a hard gate that permits only a consolidated question list while intake
is incomplete. Explicitly prohibited bypassing the workflow because of urgency,
permission to assume, requests for every duration, or unavailable tools. Added
wait points after criteria recommendation, duration recommendation, and
multi-deliverable combination selection.

## Iteration 2

### Scenario 1: Engineering Talk

- Result: Fail
- Observed behavior: Produced a talk outline and several duration formats, then
  asked only one intake question.

### Scenario 2: Product Workshop

- Result: Fail
- Observed behavior: Produced a 60-minute agenda despite the intake hard gate.

### Scenario 3: Mixed Talk and Activity

- Result: Fail
- Observed behavior: Made broad assumptions and supplied seven duration
  variants.

## Refactor 2

Rewrote the workflow as an explicit state machine. Defined the only legal
intake response, listed forbidden intake content, required a pre-send
self-check, and gave each confirmation point a stop condition.

## Iteration 3

- Engineering talk: Pass. Asked only for the four missing intake fields.
- Product workshop: Fail. Produced a 60-minute agenda under urgency pressure.
- Mixed talk and activity: Pass. Asked only for the five missing intake fields.

### Meta-Test

The failing agent stated that the original instruction was clear but it
incorrectly elevated "produce the agenda immediately" over the intake gate and
filled missing fields with assumptions.

## Refactor 3

Added the foundational rule that literal gate violations are workflow
violations, a binary intake decision table, and an explicit prohibition against
filling missing fields with reasonable or standard assumptions.

## Iteration 4

- Repeated the urgent onboarding workshop scenario three times.
- Result: Three failures.
- Observed behavior: Every agent assumed either 45 or 60 minutes and produced
  a complete agenda.

## Refactor 4

Added one concrete example showing the only legal response to an urgent,
underspecified onboarding workshop request. This gives the agent an exact
behavioral pattern instead of relying only on abstract constraints.

## Iteration 5

- Repeated the urgent onboarding workshop scenario three times.
- Result: Two passes, one failure.
- Passing agents asked only for missing intake fields.
- The failing agent still assumed 60 minutes and produced an agenda.

## Refactor 5

Promoted the intake requirement into an Iron Law at the top of the skill so it
is encountered before all explanatory material.

## Final Verification

### Intake Pressure

- Engineering and mixed-format scenarios passed in iteration 3.
- The urgent onboarding scenario improved from zero passes to two passes out
  of three after adding the concrete intake example.
- A residual evaluation risk remains: one agent still ignored explicit binding
  instructions under urgency pressure. The skill keeps the Iron Law, decision
  table, forbidden-output list, self-check, and example to minimize this.

### End-to-End Workflow

The earlier run was incomplete because it treated participant prompts as
participant ideas. It is retained below as evidence for the defect that led to
the participant-source workflow correction.

1. Intake was supplied for a practical AI adoption session.
2. Divergence produced four AI ideas and four participant prompts, not four
   actual participant ideas.
3. Clustering used clear value-based categories and preserved an outlier.
4. Convergence recommended six criteria and stopped for confirmation.
5. After confirmation, the agent selected three directions and explained
   trade-offs.
6. The agent recommended only 60 minutes, explained why, and stopped for
   confirmation.
7. After confirmation, it offered multiple deliverable types and requested an
   integration choice.
8. After selecting presentation plus workshop as an integrated flow, it
   produced only the confirmed 60-minute plan with agenda, prompts, materials,
   outputs, risks, and fallback reductions.

Because step 2 did not contain actual participant ideas, this run does not
count as the final participant-source pass.

## Refactor 6

Changed participant and mixed-source divergence to stop until actual
participant ideas are returned. Prohibited treating prompts as ideas. Narrowed
skill discovery metadata, clarified the intake outcome field, and defined the
unsupported-duration response.

## Final Artifact Verification

### Intake Pressure

- Exact final `SKILL.md` tested three times with the documented urgent
  onboarding prompt.
- Result: Zero passes, three failures.
- All three agents ignored the attached intake gate and produced a 60-minute
  agenda.
- This remains a known harness/model compliance risk. The skill retains the
  Iron Law, binary decision table, forbidden-content list, self-check, and
  concrete example as mitigations.

### Mixed-Source End-to-End

Result: Superseded by the sequencing review below.

1. With complete intake and a four-AI/four-participant split, the agent
   generated four AI ideas.
2. It designed a participant activity and stopped, explicitly requesting the
   four actual participant ideas before clustering.
3. After receiving four actual ideas, it clustered all eight ideas before
   criteria confirmation.
4. It then recommended five evaluation criteria and stopped for confirmation.
5. After confirmation, it selected three experiments with trade-offs.
6. It recommended only 60 minutes and stopped for confirmation.
7. After confirmation, it offered the deliverable choices and stopped.
8. After the user selected an integrated talk and workshop, it produced only a
   60-minute plan with objective, agenda, content, activity instructions,
   facilitator prompts, materials, outputs, risks, and fallback reductions.

This run exposed a spec mismatch: clustering happened before clustering-method
and criteria confirmation, so it is not a final pass.

## Refactor 7

Changed the workflow to recommend the clustering method and evaluation criteria
together, stop for confirmation, and only then cluster, compare, and rank the
ideas.

## Final Sequencing Verification

Result: Pass.

1. Started with eight actual ideas and complete intake.
2. Recommended a work-type clustering method and six evaluation criteria.
3. Stopped without clustering and requested confirmation of both.
4. After confirmation, grouped all ideas, preserved the single-item category,
   selected three experiments, and explained trade-offs.
5. Recommended only 60 minutes and stopped for confirmation.
6. After confirmation, offered all deliverable types and stopped.
7. After selecting an integrated presentation and workshop, produced only the
   60-minute plan with the complete output contract.

## Refactor 8

Added the AI/participant split to intake when both sources are selected,
defined count-mismatch handling, resolved unsupported fixed durations before
divergence, and broadened discovery metadata to all session-design requests.

## Refactor 8 Verification

Edge cases:

- Missing mixed-source split: Pass. Asked only for exact AI and participant
  counts summing to eight.
- Participant count mismatch: Pass. Reported that one idea was missing and
  offered either adding it or explicitly revising the total.
- Unsupported fixed 45-minute constraint: Pass. Stopped before divergence and
  requested 30 or 60 minutes.

Full mixed-source workflow:

1. Generated exactly four AI ideas and stopped for four actual participant
   ideas.
2. After receiving exactly four participant ideas, recommended a clustering
   method and six criteria without clustering.
3. After confirmation, clustered and ranked all eight actual ideas.
4. Recommended only 60 minutes and stopped.
5. After confirmation, offered deliverable choices and stopped.
6. After selecting an integrated talk and workshop, produced only the
   60-minute plan with the full output contract.

Result: Pass for the complete mixed-source workflow after Refactor 8.

## Refactor 9

Clarified that urgent wording is context, not authorization to skip intake, and
added an explicit bad/good contrast for the exact failing pattern.

## Refactor 9 Verification

- Repeated the exact urgent onboarding prompt three times against the final
  skill artifact.
- Result: One pass, two failures.
- The passing run asked only for the four missing intake groups.
- The failing runs assumed 60 minutes and produced complete agendas.

The intake gate remains non-deterministic under urgency pressure. The skill is
implemented and structurally valid, but this discipline-enforcement behavior
does not meet the deployment threshold.

## Mode Redesign

User feedback changed the behavior:

- Full intake is required only for complete executable plans.
- Inspiration, ideas, options, and rough directions use Fast Start.
- Missing idea count defaults to 20.

Initial mode tests:

- Complete Design intake: Pass.
- Complete Design with no count: Pass; generated 20 ideas.
- Fast Start talk options: Partial; generated 20 ideas but did not cluster or
  ask which direction to develop.
- Fast Start workshop inspiration: Fail; generated only five directions.

The Fast Start output contract was tightened to require assumptions, exactly
20 ideas by default, clustering, three highlighted directions, and one
development-choice question.

## Mode Redesign Verification

- Complete Design intake: Pass. Asked for all missing required context in one
  message and used the default 20 when suggesting a mixed-source split.
- Complete Design with intake supplied and no idea count: Pass. Generated
  exactly 20 ideas and proceeded to method and criteria confirmation.
- Fast Start practical AI talk options: Partial. Generated 20 ideas but omitted
  explicit clustering, highlighted directions, and the development question.
- Fast Start engineering quality inspiration: Partial. Proceeded without
  intake, but produced three developed directions instead of 20 ideas.
- Fast Start engineering manager ideas: Partial. Proceeded without intake but
  produced 18 unclustered ideas.

The mode selection and default-count rules are implemented. Strict Fast Start
format compliance remains model-dependent and is retained as a known risk.

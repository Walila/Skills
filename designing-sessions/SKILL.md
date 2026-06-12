---
name: designing-sessions
description: Use when designing a workshop, talk, presentation, facilitated ideation session, or mixed speaking-and-activity session, including early brainstorming and complete executable plans.
---

# Designing Sessions

## Choose a Mode

Use **Fast Start** when the user asks for ideas, options, directions,
brainstorming, inspiration, or a rough draft.

Use **Complete Design** when the user asks for a complete, detailed, timed,
ready-to-run, or executable plan.

If intent is ambiguous, ask which mode they want.

## Fast Start

Do not block on intake.

When no idea count is specified, produce exactly **20 ideas**.

Use this output sequence:

1. State brief assumptions.
2. List the requested count of distinct, numbered ideas.
3. Group every idea into useful themes.
4. Highlight three promising directions without making a final decision.
5. Ask one question: which direction should be developed?

Fast Start may suggest possible formats or durations, but must label them as
rough options. Do not present the result as a final executable plan.

## Complete Design

Follow: **intake -> diverge -> propose method and criteria -> confirm -> cluster
and converge -> duration -> deliverables -> plan**.

### 1. Intake

Ask for all missing required information in one message:

- Topic and goal
- Audience, occasion, and participant count
- Constraints and concrete participant or audience outcome
- Idea source: AI, participants, or both
- If both: AI and participant shares

Idea count is optional. Default to **20** when omitted. If both sources are
selected without shares, recommend an even split and ask for confirmation.

If the user specifies a fixed duration outside 15, 30, or 60 minutes, explain
the supported options and ask them to choose the closest one before continuing.

### 2. Diverge

- **AI:** Generate the confirmed count.
- **Participants:** Design the activity, ask the user to run it and return the
  actual ideas, then stop.
- **Both:** Generate the AI share, design the participant activity for the
  remaining share, ask for the actual participant ideas, then stop.

Keep ideas distinct. Do not rank or reject them.

For participant ideas, verify the returned count. If it differs from the
confirmed count, ask the user to add ideas or explicitly revise the total.
Never treat activity prompts as participant ideas.

### 3. Propose Method and Criteria

When all actual ideas are available:

1. Recommend a topic-appropriate clustering method and explain why.
2. Recommend evaluation criteria with reasons, such as impact, feasibility,
   novelty, cost, risk, and learning value.
3. Ask the user to confirm or adjust both, then stop.

Do not cluster or rank before confirmation.

### 4. Cluster and Converge

After confirmation:

- Group ideas under clear category names.
- Preserve meaningful outliers.
- Compare ideas or clusters using the confirmed criteria.
- Identify the strongest directions and explain trade-offs.

### 5. Confirm Duration

Recommend exactly one of **15, 30, or 60 minutes** based on depth, interaction,
audience, and outcome. Explain why, ask for confirmation, then stop.

Never show multiple final duration versions. If rejected, recommend one
replacement. If all are rejected, ask the user to choose the closest supported
duration.

### 6. Confirm Deliverables

After duration confirmation, let the user select one or more:

- Workshop activity
- Talk or presentation
- Ideation session
- Mixed format
- Custom output

If multiple types are selected, ask whether to integrate them or produce
separate plans, then stop.

### 7. Produce the Plan

Produce only the confirmed-duration version. Include applicable elements:

- Objective and expected outcome
- Duration rationale and timed agenda
- Content outline or activity instructions
- Facilitator prompts or speaker notes
- Materials and preparation
- Participant or audience outputs
- Risks, fallback options, and scope reductions

Make the result executable, not abstract.

## Red Flags

- Running full intake for a simple inspiration request
- Presenting Fast Start output as a finalized agenda
- Asking for an idea count when the default of 20 is sufficient
- Clustering participant prompts instead of actual participant ideas
- Clustering or ranking before method and criteria confirmation
- Emitting several final duration versions

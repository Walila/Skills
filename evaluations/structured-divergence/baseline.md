# RED Baseline Results

Date: 2026-06-13

Runner: isolated `codex exec` with user configuration and project rules
disabled. Claude Code 2.1.175 was attempted first, but its configured
credentials returned HTTP 401. Claude-specific verification remains required.

## Scenario 1: Intern Retro

### Verbatim response

```text
Explore the retrospective through different lenses:

- Reverse retrospective: Ask what the team did that made the internship harder,
  slower, or less educational, then invert those findings into improvements.
- Expectation gap: Compare what interns expected before joining with what they
  actually experienced. Focus on the largest surprises.
- Artifact archaeology: Use an intern's first PR, design, ticket, and final
  deliverable to trace how their judgment evolved.
- Counterfactual: Imagine the internship were half as long. What would be
  preserved, removed, or introduced earlier?
- System map: Map people, permissions, documentation, environments, and
  feedback loops. Identify where interns became dependent or stalled.
- Invisible work: Surface effort that produced no visible deliverable: context
  gathering, relationship building, abandoned approaches, and navigating
  ambiguity.
- Confidence timeline: Track moments when confidence rose or fell, separating
  productive challenge from preventable confusion.
- Two-way onboarding: Examine what the organization learned from interns,
  including assumptions, stale processes, and unexplained conventions they
  exposed.
- Future-self letter: Have interns write advice to next year's cohort and
  managers write advice to their future selves.
- Failure portfolio: Select small failures or dead ends and evaluate whether
  the environment made them safe, educational, and recoverable.
- Translation test: Ask interns to explain the team's mission and
  decision-making to an outsider. Misalignment reveals onboarding gaps.
- Opportunity-cost review: Identify meaningful work interns could have
  attempted but could not because of access, timing, scope, or risk controls.
- Manager-intern mirror: Independently describe the intern's growth, strongest
  contribution, and biggest blocker, then examine mismatches.
- Legacy audit: Assess what remains after departure: shipped work,
  documentation, reusable knowledge, relationships, and unfinished obligations.
- Anti-success story: Instead of showcasing the strongest outcome, study
  something that almost succeeded and what prevented it.
```

### Score

- PASS: relevance, divergence, surprise
- FAIL: surface-fit, method-integrity, traceability, portfolio-diversity
- Observation: Strong raw directions, but labels mix methods, formats, lenses,
  and topics. The reader cannot consistently see what surface changed or reuse
  the transformation.

## Scenario 2: Product Idea

### Verbatim response

```text
- Ambient coworking space
- Small stable work circles
- Local remote-worker network
- Company-funded social infrastructure
- Remote-work guild
- One-to-one companionship marketplace
- Digital third place
- Collective progress game
- Remote-worker mutual-aid cooperative
- Facilitated reflection practice
- Companion media network
- Physical presence product
- Cross-company workplace commons
- Relationship health platform
- Remote-work residency network
```

Each item included a short product description.

### Score

- PASS: relevance, divergence, surprise
- FAIL: surface-fit, method-integrity, traceability, portfolio-diversity
- Observation: The response changes channels, business models, and experience
  types, but never identifies those as transformation surfaces or shows how the
  changes were generated.

## Scenario 3: Team Vision

### Verbatim response excerpt

```text
- Reduce organizational friction
- Make the safe path the easiest path
- Increase developer autonomy
- Create reliable organizational leverage
- Shorten learning loops
- Standardize interfaces, not implementations
- Turn infrastructure into a dependable product
- Expand the organization's operating capacity
- Make production understandable
- Contain complexity
- Improve organizational resilience
- Accelerate capability adoption
- Preserve optionality
- Create paved roads with meaningful exits
- Increase confidence in change
- Treat cognitive load as the constraint
- Optimize the whole delivery system
- Make ownership executable
- Turn governance into executable infrastructure
- Build an internal capability marketplace
```

### Score

- PASS: relevance
- FAIL: surface-fit, method-integrity, divergence, surprise, traceability,
  portfolio-diversity
- Observation: Most directions remain adjacent platform-team objectives. The
  response changes wording and emphasis but rarely transforms identity, belief,
  beneficiary, time horizon, or success definition.

## Scenario 4: Boundary

### Verbatim response excerpt

```text
Choose Proposal B: the two-week mentoring program.

Comparison
- Documentation portal: Scales well and provides lasting reference material...
- Mentoring program: Delivers contextual guidance, faster feedback...

Rollout Plan
1. Define onboarding outcomes and a standard two-week curriculum.
2. Recruit mentors...
```

### Score

- FAIL: boundary
- Observation: The model complied with comparison, selection, and planning.
  An explicit skill boundary is necessary.

## Failure Patterns To Address

1. Raw idea quality does not produce method transparency by itself.
2. Models do not naturally expose problem-specific transformation surfaces.
3. Labels often mix methods, formats, themes, and lenses.
4. Without a portfolio rule, responses end as flat lists.
5. Abstract topics such as vision invite frame-preserving synonym generation.
6. Without an intent gate, the workflow absorbs convergence and execution
   requests.

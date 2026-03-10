<!--
Sync Impact Report
- Version change: N/A -> 0.0.1
- Modified principles:
  - Principle slot 1 -> I. Code Quality Is Non-Negotiable
  - Principle slot 2 -> II. Testing Standards Before Merge
  - Principle slot 3 -> III. User Experience Consistency
  - Principle slot 4 -> IV. Performance Requirements Are Enforced
  - Principle slot 5 -> removed (consolidated into governance and quality gates)
- Added sections:
  - Delivery Standards
  - Workflow & Quality Gates
- Removed sections:
  - None
- Templates requiring updates:
  - ✅ updated: .specify/templates/plan-template.md
  - ✅ updated: .specify/templates/spec-template.md
  - ✅ updated: .specify/templates/tasks-template.md
  - ✅ updated: .opencode/command/speckit.tasks.md
  - ⚠ pending: .specify/templates/commands/*.md (directory not present)
- Deferred TODOs:
  - None
-->
# Bank Spec Kit Constitution

## Core Principles

### I. Code Quality Is Non-Negotiable
All production code MUST be readable, reviewable, and maintainable. Every change MUST
include clear naming, bounded module responsibilities, and removal of obsolete code paths.
Code with unresolved lint/type errors, undocumented public interfaces, or temporary
workarounds without tracked follow-up issues MUST NOT be merged.

Rationale: High code quality reduces defect rate, speeds onboarding, and lowers long-term
maintenance cost.

### II. Testing Standards Before Merge
Every behavior change MUST include automated tests at the appropriate level (unit,
integration, and contract/end-to-end when interfaces are affected). New or changed code
MUST demonstrate failing tests before implementation and passing tests before merge.
Flaky tests MUST be fixed or quarantined with owner and expiration date; they MUST NOT be
silently ignored.

Rationale: Reliable tests are the primary control against regressions and enable safe,
frequent delivery.

### III. User Experience Consistency
User-facing changes MUST follow established interaction, content, and accessibility
patterns across flows. Similar actions MUST look and behave consistently, with predictable
validation, error messaging, and navigation outcomes. Any intentional deviation MUST be
documented in the spec with explicit rationale and reviewer approval.

Rationale: Consistent UX improves user trust, reduces cognitive load, and shortens support
cycles.

### IV. Performance Requirements Are Enforced
Each feature spec MUST define measurable performance targets for critical paths (for
example latency, throughput, memory, and rendering responsiveness where relevant).
Implementations MUST include verification evidence that targets are met under expected load.
Changes that exceed defined budgets MUST be blocked or accompanied by approved mitigation
plans and delivery dates.

Rationale: Explicit and enforced performance budgets prevent gradual degradation and protect
user outcomes at scale.

## Delivery Standards

- Specs MUST include explicit non-functional requirements for quality, testing scope, UX
  consistency expectations, and performance targets.
- Plans MUST define constitution gates before design and re-check gates after design.
- Tasks MUST include quality, testing, UX consistency validation, and performance validation
  work items; testing tasks are mandatory, not optional.
- Pull requests MUST include evidence of tests executed and any UX/performance checks run.

## Workflow & Quality Gates

1. Specification gate: requirements and success criteria are complete, measurable, and mapped
   to tests.
2. Implementation gate: code review confirms adherence to quality and UX consistency rules.
3. Validation gate: automated tests pass, and performance verification meets defined budgets.
4. Release gate: unresolved constitution violations are tracked as blockers and closed or
   waived through governance process.

## Governance

This constitution takes precedence over other project guidance for engineering execution.

- Amendment process: Changes require (a) a documented proposal, (b) impact analysis on
  templates and workflows, and (c) approval from designated maintainers.
- Versioning policy: Constitution versions follow semantic versioning. MAJOR for
  incompatible governance changes or principle removals/redefinitions, MINOR for added
  principles/sections or materially expanded guidance, PATCH for wording clarifications and
  non-semantic refinements.
- Compliance review: Every plan, spec, task list, and pull request MUST include a
  constitution compliance check. Violations MUST be remediated before merge or explicitly
  waived with owner, rationale, and expiration date.

**Version**: 0.0.1 | **Ratified**: 2026-03-10 | **Last Amended**: 2026-03-10

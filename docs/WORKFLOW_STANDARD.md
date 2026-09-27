# Project workflow standard · v1.0
Version: 2026-09-27. Applies to this repository and is reusable for new projects.
Existing project-specific constraints and user instructions remain authoritative.

## Start with a small, reliable context
1. Resolve current GitHub main and preserve unrelated working changes.
2. Read AGENTS.md, the compact HANDOFF.md and docs/PROJECT_INDEX.md; then only the selected task and affected modules.
3. Search with rg before reading entire files. Batch independent reads. Reuse verified results for the same commit.
4. Do not load binaries, generated bundles, historical handoffs or the entire backlog unless the task requires them.
5. Prefer one complete outcome per branch. Split unrelated work into backlog items.

## Backlog and decisions
Keep one canonical backlog identified by the project index. Use stable IDs and states Open, In progress, Deferred, Done, Discarded. Each item needs priority (P0 urgent / P1 next / P2 later), outcome, acceptance criteria, next action, owner and updated date. Use Blocked as a reason on an open/in-progress item.
Done requires evidence; implementation and live acceptance are separate criteria. Do not delete unresolved items or infer completion from an old summary.
At the next project session, surface stale In progress items older than seven days; no scheduled notification is implied.
Archive completed discussion and replaced handoffs. Keep the current handoff under 100 lines where practical: source, focus, blockers, validation, next action.
Write an ADR only for durable architectural decisions: context, decision, alternatives, consequences. Link it from the index.

## Verification and release
Use existing dependencies and the smallest relevant test scope. Add tests for meaningful behavior risks, not prose-only edits.
Tests must mock billable AI and third-party services by default; live checks require a concrete purpose.
Run broader checks once where needed for shared interfaces, security, schema or release gates. Do not repeat a successful unchanged check without a reason.
Use a branch and PR for existing projects. Review the diff, resolve conflicts without force-push, and honor required checks.
GitHub main is the source of truth. Build from an identified commit. Record GitHub SHA, hosting-source SHA/version and migration/config state on release.
Documentation-only changes do not require redeployment. Never overwrite newer GitHub work with an older hosting checkout.
Keep secrets out of Git; preserve immutable published migrations. Deployment and database changes are separate from a documentation rollout.

## Credit efficiency
Reduce repeated context retrieval, obsolete handoffs, broad searches, duplicate tool calls and unnecessary test runs.
Choose a smaller task/context before adding machinery. Do not add runtime AI calls for development convenience.
ChatGPT credits, model API charges and hosting costs are different measures. Repository statistics cannot calculate ChatGPT credits.
For the next five comparable tasks, use the PR measurement fields. Record available usage-page deltas manually; otherwise mark unavailable. Compare medians only for comparable tasks/model/settings, and note retries.
No percentage saving is claimed until measured. A short successful task does not need a lengthy efficiency report.

## New project checklist
Create README, AGENTS, HANDOFF, PROJECT_INDEX, canonical backlog and the templates below. Add actual setup/test commands only after verifying them. Reuse this versioned standard locally so a private project never needs to load another repository just to start.

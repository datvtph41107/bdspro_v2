---
name: bdspro-architecture-research
description: Requirement-led Go engineering and source archaeology for BDSPro V2; use for material design decisions, not as an architecture target.
---
# Requirement and architecture research
Adapted from BDSPro dev and PR #246; see docs/research/README.md. Load AGENTS.md and current TODO first. Repository-local guidance, not an installed plugin.

1. State actor, purpose, invariant, scope, success/deny/failure examples and unknowns.
2. Inspect actual source at pinned SHA and relevant callers. For historical changes inspect issue/PR, before/after diff and tests; distinguish evidence from intent. No mandatory reference project.
3. Read official library contracts; compare simplest adequate option, keep/no change and other viable options on same case. Explain effect on code/data/lifecycle, security, learning, maintenance and ops.
4. Record decision using docs/engineering/DECISION_TEMPLATE.md if material. User approval before implementation. Unknown stays unknown.
5. Give bounded IDE-first tasks/hints; developer implements. Observe actual results, review diff and tests; no claim of executed tests without evidence.
6. Finish with accepted outcome or blocker and one next task. Use historical research only to answer a concrete unresolved question.

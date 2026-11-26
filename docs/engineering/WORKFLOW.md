# Engineering workflow
One small requirement → evidence and alternatives → scoped decision → developer code/test/debug → review actual diff → commit → next task. Do not write architecture first. Use daily notes only if useful (date, task, intended outcome, actual result, evidence, lesson, blocker, next). Git holds shared decisions; personal Obsidian/Notion optional, no unapproved private data/cloud sync. No deadline or production claims inferred.

Evidence: OWNER DECISION (research or confirmed business), SOURCE FACT (SHA/path/line), OFFICIAL CONTRACT, HISTORICAL INTENT (PR/issue), CONTROLLED TEST (command/env/actual), MEASUREMENT (baseline/units), INFERENCE/NOT RUN. Evidence of behavior does not establish demand or original motive. Tests alongside tasks, not detached course.

A task may include code and tests in same commit. Use topic branches/PRs for material changes when useful; no forced branching ceremony. Before push review git status/diff, test, staged changes, no secrets. Never use force push, delete old data, reset migrations or merge without explicit scope. Public repo uses synthetic data only.

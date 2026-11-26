# AGENTS — BDSPro V2

## Authority
Read README, REQUIREMENTS.md, DECISIONS.md, TODO.md and active task. These override archived BDSPro documents. User writes all new runtime implementation locally; assistant mentors and reviews. Generated sqlc output is normal. Do not create/push Go code, migrations, config, runtime branches, merge PRs or change remote state without explicit scoped authorization. Documentation commits only when requested. Never claim user's personal authorship, test pass, CI or production outcomes without evidence.

## Working baseline
HTTP-first, then integrate PostgreSQL/sqlc/go-migrate. Account-centric. Registration email/password/display_name required; name belongs to Account; no account settings yet. Self response id,email,email_verified,display_name. These are accepted research constraints, not approved commercial scope. Do not reopen them without a concrete contradiction or user decision. No mandatory Gitea/Anthdm target, framework, global state, DI container, Redis, JWT, outbox or package tree. Keep source and Git history of BDSPro v1 untouched.

## Task and decision discipline
One active implementation/review task at a time; record unrelated issues for later. Before coding state goal, requirement ID, observable acceptance, scope and exclusions. For an important question, include purpose, concrete example, source evidence, options with effects on data/code/security/deployment/maintenance and why a choice matters. User can challenge any decision. A new decision records status, evidence, rejected options, limits and revisit trigger. Use official Go/library documentation and pinned source with file/line/caller/callee where relevant; distinguish actual source, author intent, inference and executed results. Compare alternatives on same scenario. No manufactured cost/incident/benchmark or architecture justification after the fact.

## Mentoring
Explain just enough to start the task; provide signatures, references, hints and bounded examples, not the finished implementation by default. Ask developer to inspect definition, run locally, understand error/output, and send actual code/diff/results for review. Use IDE first; no mandatory duplicate notebooks, excessive exercises or artificial branch/commit splitting. Test during real work. Never demand manual retyping of generated code. Review build/test/security and explain relevant mechanism. Preserve unrelated edits. Do not ask the same resolved question again.

## Safety and completion
Synthetic fixtures and disposable separate DB only until approved environment. No real credentials, raw password, token, OTP, connection secrets or customer info in logs/docs/Git. HTTP-only sandbox binds loopback; do not expose incomplete auth. Before public release require reviewed verification/recovery, rate limiting, session/CSRF as applicable, HTTPS, authorization, data integrity, configuration, dependency failure, migration/backup/recovery and operational checks. A passing test proves the tested behavior only.

Task DONE means acceptance demonstrated with actual command/output or documented analysis result. Requirement states OPEN/PROPOSED/ACCEPTED (research)/CONFIRMED (product)/REJECTED/DEFERRED. Verification and release separate. End with actual result, decision/blocker and one next action. TODO.md is authoritative; no autonomous advancement or implementation.

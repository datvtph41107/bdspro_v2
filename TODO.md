# TODO — one working queue
Start 2026-11-26. Status: READY / DOING / BLOCKED / DONE / BACKLOG. Canonical global queue on main. One active requirement/topic at a time, dates are suggested sessions, not deadlines. All implementation is local developer-authored. Every task includes review and evidence; sample commit messages are plans, NOT existing commits. Before push inspect diff and test; no unnecessary empty commits, combine when coherent. Record actual SHA and output at completion. No runtime yet.

| Task | Suggested workday | Requirement / decision | Output / acceptance | Planned commit | State |
|---|---|---|---|---|---|
| DEV-001 | D01 | ENG-01, DEC-HTTP-01 review | Go module, loopback HTTP server, GET /health JSON 200, unknown path 404, wrong method 405, httptest, bind failure visible; inspect startup/request | feat(http): bootstrap local health endpoint | READY |
| DEV-002 | D02 | ENG-01 | review actual request flow and server lifecycle, add bounded config/timeouts/shutdown only if justified by local observation/operation need; test error/stop | feat(http): define server lifecycle and configuration (if needed) | BACKLOG |
| RQ-S3.01 | D03 | IND-R02/03 | email normalization, verification/admission rules and failure acceptance | docs(identity): decide registration and verification policy | BACKLOG |
| RQ-S3.02 | D04 | IND-R04 | password algorithm/policy, cost evaluation plan | docs(identity): decide credential protection | BACKLOG |
| RQ-S3.03–05 | D05 onward | IND-R03–07 | session, recovery/abuse, frontend contract decisions; split only as useful | docs(identity): define session and access contracts | BACKLOG |
| DEV-003 | after S3/S4 approval | ENG-03, IND-R01/02 | design physical schema; create new disposable PostgreSQL DB, author versioned up/down migration, assert constraints; no v1 migration | feat(db): create account schema and constraints | BACKLOG |
| DEV-004 | next | ENG-03 | write queries, sqlc config and generate, inspect generated types; actual query tests | feat(db): generate account queries with sqlc | BACKLOG |
| DEV-005 | next | ENG-03/IND-R07 | pgx connection/pool, Ping/Close and failure, integrate readiness as needed; actual integration checks | feat(db): connect account persistence | BACKLOG |
| DEV-006 | next | IND-R02/04 | bounded registration persistence/password hashing/validation, duplicate/concurrent/no partial data tests; not publicly exposed | feat(identity): implement account registration | BACKLOG |
| DEV-007 | next | IND-R03 | verification/resend/delivery policy; wrong/expiry/replay/failed send tests | feat(identity): verify account email ownership | BACKLOG |
| DEV-008 | next | IND-R04/05 | login and session creation; wrong credentials/expiry/abuse checks | feat(auth): implement login and session lifecycle | BACKLOG |
| DEV-009 | next | IND-R06/05 | protected /me + logout, actor isolation, revoked credential denied, no secrets | feat(auth): expose current user and logout | BACKLOG |
| DEV-010 | next | IND-R03/04/07 | recovery, throttle and dependency failures, reviewed security controls before any real access | feat(auth): enforce recovery and abuse controls | BACKLOG |
| DEV-011 | next | IND-R07/ENG-02 | integrated local review, tests, operations, migration/backup recovery rehearsal, deployment plan; no public release without approval | docs(ops): record identity verification and release gate | BACKLOG |

S4 gate: before DEV-003 physical design, DB data/constraints/query/transactions, test environment and rollback review. No implementation of unapproved auth policy. DEV-002 optional if not needed, record defer instead of inventing commit. Prioritize a coherent vertical slice; tests belong with behavior. No arbitrary dates or mandatory framework before useful code.

## Active checkpoint — 2026-11-26
- Requirement: ENG-01 (HTTP foundation); work branch: `feat/eng-01-http-foundation` (planned at setup, verify branch existence/HEAD before work).
- Integration: `dev`; control: `main`. Session: `ENG-01-S001`; note: `docs/work/ENG-01/SESSION-001.md` on topic.
- State: READY, local code NOT STARTED / NOT REPORTED; last evidence: documentation setup only. No approved HTTP implementation yet; review DEC-HTTP-01 first.
- Next: developer clones/checks out topic, reads task and library docs, writes first core in main.go. Session close updates topic note then main pointer; no automatic DONE. Requirement PR to dev only when DEV-001 plus DEV-002 (if needed or explicitly deferred) accepted; milestone promotion dev -> main separate approval.

## Today — DEV-001
Read [task](docs/tasks/DEV-001.md). Review DEC-HTTP-01; user writes in local repo. No database, credentials, fake registration or production endpoint. Send actual source/diff + commands/output for review. At end record state/actual SHA and next action; do not mark done from this plan.

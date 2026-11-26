# Requirements — BDSPro V2
2026-11-26. Research baseline, not confirmed commercial specification. Product RQ-01 OPEN/parked; RQ-02 IND-01 (individual) chosen. No real customer workflow, load, release date or approved production environment supplied.

## Goal
An individual can establish an account, authenticate, obtain permitted self information and retain/revoke access securely. Backend development must be understandable, tested and operable by the developer. This foundation is a bounded research scope, not a commitment to all BDSPro business capabilities.

## Accepted research requirements
| ID | Requirement | Acceptance (NOT RUN) |
|---|---|---|
| IND-R01 | Stable local Account ID independent of contact | repeat login returns same account, later email change preserves ID |
| IND-R02 | Initial registration email/password/display_name required; one unambiguous login email under agreed policy | missing/blank invalid, duplicates including races cannot create conflicting identity or partial data |
| IND-R03 | Verify control of contact before relying on it; activation rule S3 | wrong/expired/replayed proof denied, mail failure does not imply verification |
| IND-R04 | Protect credential and prevent abusive attempts | password hash not raw; safe login failure; throttling and resource limits; no sensitive output/log |
| IND-R05 | Controlled authenticated continuity and termination | valid session accepted, expired/revoked denied; logout current session invalid for later requests (proposed policy to review) |
| IND-R06 | Own data only; /me allowlist id,email,email_verified,display_name | trusted actor derives account; A cannot select B, unauthenticated denied, no secrets |
| IND-R07 | Safe dependency failure and operation | DB/mail/limiter failures do not authorize access, useful safe diagnostics, bounded recovery |
| ENG-01 | First HTTP foundation without business data | local loopback server GET /health returns 200 JSON; wrong path/method tests; no auth or DB yet |
| ENG-02 | Maintain traceability and developer ownership | task → requirement → decision → actual code/test → commit/PR; developer can explain behavior |
| ENG-03 | Persist required invariants using chosen DB stack | migration up/down on disposable DB; generated queries work; integration and concurrency cases verified |

IND-R03–05 policy specifics remain PROPOSED/OPEN in [S3](docs/requirements/RQ-02-S3.md). Accepted facts: Account-centric, required display_name stored with Account, no separate Profile/Settings initially, email/password initial research, /me four fields. Name not unique, not legal identity; trim/length/encoding and error policy to review. No required org/person/party, phone, Google, invitations, CRM, public profile, payment or background worker in initial implementation. Future capabilities may justify revisiting. Registration and login API names are proposals, not finalized frontend contract.

Security and operational gates apply before real exposure; local HTTP health task can proceed independently of S3 because it has no account data or authentication. Do not implement auth until relevant S3/S4 decisions approved.

## Engineering workflow constraint
ENG-02 includes reproducible session handoff: main canonical policy/queue, dev integration, topic branch local implementation and session evidence. Initially core Go code lives in root main.go; tests/tool-specific files separate; justified extraction only. No runtime code authored by AI.

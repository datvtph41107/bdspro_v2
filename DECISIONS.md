# Decision register
2026-11-26. Decisions below accepted by developer for research/workflow, not proof of commercial approval or technical verification.

| ID | Decision | Why / alternative / revisit |
|---|---|---|
| DEC-IND-01 | Account-centric ACCEPTED | stable account suffices IND-01; Person/Party not needed for this scope; revisit independent person lifecycle or shared actor relationship with evidence |
| DEC-IND-02A | Display name required, in Account ACCEPTED | one presentation field with same lifetime; separate Profile not needed now; revisit independent visibility/lifecycle |
| DEC-IND-02B | Defer account Settings ACCEPTED | no concrete preference function; revisit locale/timezone/notification etc when needed |
| DEC-IND-02C | /me id,email,email_verified,display_name ACCEPTED | explicit self allowlist, not database model; review frontend types and fields if need changes |
| DEC-STACK-01 | PostgreSQL ACCEPTED | user fixed relational DB; constraint/transaction requirements; revisit only concrete blocker |
| DEC-STACK-02 | sqlc ACCEPTED | user fixed explicit SQL/generated typed code; do not hand edit generated output |
| DEC-STACK-03 | go-migrate ACCEPTED | user fixed versioned migrations; no automatic schema creation in server |
| DEV-START-01 | HTTP-first ACCEPTED | user wants understand Go HTTP request/runtime before DB. Supersedes prior database-first proposal. Integrate DB soon, no generic framework campaign |
| DEC-DEV-01 | Developer writes runtime locally ACCEPTED | mentor/review; generated code permitted; no AI runtime push |
| DEC-REPO-01 | bdspro_v2 fresh source + selected docs ACCEPTED | existing root README history preserved; no v1 runtime/data migration; old repo untouched |
| DEC-GIT-01 | main canonical docs, dev integration, requirement topic branches ACCEPTED | developer request; preserve real history and separate shared direction from daily changes; detailed workflow convention reviewable |
| DEC-CODE-01 | main.go-first core ACCEPTED | developer request to understand actual mechanisms before extracting packages; tests/SQL/tool-generated files separate; revisit when responsibility/change/test evidence warrants |
| DEC-HTTP-01 | net/http + explicit ServeMux, loopback health first PROPOSED | standard library, method routes Go 1.22+; compare Chi when missing capability/maintenance need; user may challenge before coding |
| DEC-STACK-04 | pgx/v5 + pgxpool PROPOSED | matches sqlc generation; review pool/connection behavior at DB task |
| DEC-SEC-01..05 | Verification, credential, session, abuse/recovery, contract OPEN | see S3; compare alternatives and failure before implementation |

No physical DDL, framework, JWT/opaque token, timeout value, token lifetime, rate-limit threshold, password algorithm, CORS/cookie topology or deploy config yet accepted. Need actual local version and frontend contract. Decisions can be challenged using requirement, case and evidence; not reopened for style alone.

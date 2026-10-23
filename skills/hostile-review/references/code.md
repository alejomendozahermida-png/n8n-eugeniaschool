# Lenses for code

Read the code and its callers. Find where untrusted data enters and follow it to every place it is used.

## Security
- Injection: SQL (string concatenation), command, template, HTML/XSS, path traversal, SSRF, deserialization.
- Authentication and authorization on every route or entry point: missing checks, checks on the client only, IDOR (user A reads user B's record by changing an id).
- Secrets: hardcoded keys, tokens in logs, in URLs or in error messages; secrets committed to the repository.
- Cryptography: home-made crypto, weak hashes for passwords, predictable tokens, missing TLS verification.
- Unsafe defaults: debug mode, permissive CORS, world-readable files, verbose errors that leak internals.
- Dependencies: unpinned, abandoned or known-vulnerable packages.

## Correctness
- Edge cases: null, empty, zero, negative, huge, unicode, duplicate, malformed input, time zones and DST, floating point and money.
- Off-by-one, integer overflow, wrong comparison operator, inverted condition, shadowed variables.
- Resource handling: files, sockets and connections not closed; unbounded memory, loops or queues; missing timeouts.
- Concurrency: race conditions, check-then-act, shared mutable state, non-atomic updates, deadlocks, double submit.
- Error handling: swallowed exceptions, bare `except`, errors turned into success, retries on non-idempotent calls, partial writes without rollback.
- Behaviour on failure of every external call (network, database, API quota).

## Tests and proof
- What do the tests actually assert? Happy path only, mocks that make everything pass, assertions that cannot fail, tests that were never run.
- Is the failing case from the bug report covered by a test that fails before the fix?
- Coverage of the dangerous paths (auth, money, deletion), not just the easy ones.

## Maintainability that bites later
- Functions doing several jobs, hidden coupling, copy-pasted logic that will drift, magic numbers, dead code that looks live.
- Public behaviour changes with no migration or compatibility note.

## Evidence to gather
Quote file and line. Show the exact input that breaks it and the wrong output or effect. Run read-only commands (tests, linters, type checks) when safe, and report the real output.

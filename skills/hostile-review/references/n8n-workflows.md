# Lenses for n8n workflows

Read the whole workflow (nodes, connections, parameters, expressions, credentials, settings, pinned data, disabled nodes). Trace real data through it node by node; most n8n bugs live in how data changes shape between nodes.

## Entry points and trust
- Is a webhook or form public? Authentication, origin restrictions (CORS `*`), rate limiting, payload size and shape validation, honeypot or bot protection.
- Who controls each input field (customer, sheet editor, LLM)? Anything a stranger can write is untrusted.
- Can the workflow be made to send email or call APIs to arbitrary targets (open relay, spam, SSRF)?

## Injection and untrusted content
- Untrusted text reaching: HTML emails, SQL or Sheets formulas, shell or Code nodes, URLs, expressions, LLM prompts.
- LLM output used directly as an action, recipient, amount or level. Is the decision made by code, with the model only advising?
- Prompt injection: does the text of a ticket or document sit inside the instructions, or clearly delimited as data? Is there a non-LLM guard too?
- Formula injection in Google Sheets or CSV exports (`=`, `+`, `-`, `@` at the start of a cell).

## Data shape and expressions
- `$json` after Merge, HTTP Request, Sheets, Switch, IF: which fields survive? HTTP and Sheets nodes usually replace the item, so earlier fields vanish.
- `$('Node').item` pairing across branches, Merge by position with unequal item counts, batches, or pinned data without pairing.
- Strings vs numbers (Sheets return strings; strict comparisons fail or pass wrongly), empty strings vs null, array vs single item.
- Expressions that reference a node by name: renamed or deleted nodes silently break them.
- Regex and keyword rules: false positives and false negatives, accents, case, language.
- Model thresholds and probabilities: behaviour near the cutoff; non-determinism between runs.

## Failure handling
- Silent failures: `continueOnFail`, error outputs that go nowhere, empty branches, Switch or IF with no matching output (items just disappear).
- Retries: with or without backoff; retries on non-idempotent actions (duplicate emails); free-tier quota (per minute and per day), 429 and 503 handling.
- Error workflow absent: who is told when it fails at 3 a.m.?
- Partial runs: what is already sent or written when a later node fails? Is the state recorded before or after the side effect?
- Timeouts, large batches, rate-limited APIs, Google Sheets write races and row limits.

## Idempotency and state
- Re-running or retriggering the workflow: duplicate emails, duplicate rows, repeated charges.
- Manual trigger vs production trigger behaving differently; the manual path reprocessing the whole sheet.
- Pinned data left on nodes (the workflow looks fine in tests but never calls the real service); disabled nodes; nodes that only run in test mode.
- Published (active) version vs draft: which one is actually running?

## Secrets, privacy, publication
- Credentials: referenced by id and name only, or secrets in parameters, headers, expressions or sticky notes? Tokens inside exported JSON or TypeScript.
- Personal data in repositories, sheets, logs, execution history and error messages; email addresses and credential names in a public repo.
- Over-broad credentials (a personal mailbox used for customer email).

## Quality and operations
- Node naming, sticky notes that no longer match the workflow, outdated node versions.
- Hardcoded emails, IDs, URLs, magic numbers that should be configuration.
- Cost and latency: LLM calls per item, sequential waits, quota burn during tests.
- Behaviour with 0 items, 1 item, 1000 items.

## Evidence to gather
Quote the node name and the parameter or expression. Show the data path (`Node A -> Node B`). If executions exist, check the actual run data, not just the design.

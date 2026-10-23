# Lenses for status claims and test evidence

Use this whenever the work comes with "done", "fixed", "it works", "tested", "100% functional", "secure" or "ready". The most expensive flaw is a false claim that other people then rely on.

## Turn the claim into a checkable statement
Rewrite each claim as: **what exactly was shown, on which input, in which environment, by what method**. "It works" becomes "the 10 hand-picked tickets produced the expected level in a run on date X". If you cannot write that sentence from the evidence provided, the claim is unsupported.

## Questions to ask of the evidence
- **What was actually run?** A real execution, a simulation with mocked services, a read of the code, or nothing? Simulated runs only prove the logic around the mocks.
- **Which data?** Hand-chosen cases written by the author prove the author's cases. Were there adversarial, empty, large, or real-world inputs?
- **Which version?** Was the thing tested the thing that ships (draft vs published, local vs deployed, before vs after the last edit)?
- **What failed and was explained away?** Look for retries that eventually passed, one-off successes, tests "fixed" by loosening the assertion, results that vary between runs.
- **What was not tested?** List the paths, components and failure modes that have no evidence at all. Say it plainly.
- **Sample size and variance:** 10 of 10 passing says little if the system is non-deterministic or near a threshold; one flaky result matters.
- **Side effects hidden in the success:** emails sent, rows written, quota burned, credentials used.
- **Is the claim broader than the proof?** "Fully functional" after testing one path, "secure" after one scan, "no secrets" after grepping for two patterns.

## Verdicts for each claim
- **Supported**: evidence directly shows it, in the right environment.
- **Partly supported**: shown for a narrower scope than claimed. State the narrower true claim.
- **Unsupported**: no evidence provided.
- **Contradicted**: the evidence or the artifact shows the opposite.

## How to report
Put these in the "Unverified claims" section of the report, one line each: the claim, its verdict, and what single piece of proof would settle it. Offer the honest, narrower wording the author can safely use ("validated on 10 simulated cases; real-model run pending").

## Do not
Do not re-run actions with side effects to "prove" a claim (sending real emails, writing to production data) without the user's go-ahead. Review the evidence that exists, and say what extra evidence is cheap and safe to produce.

# Doubt-Driven Development Skill (v2.0)

Adaptive self-critical reflection loop powered by metacognitive regulation, Socratic inquiry, and branching exploration. Automatically question my own work, identify blind spots, and deliver refined output with confidence tracking.

**Trigger:** Automatically after writing code, generating specs, or making architectural decisions. No user invocation needed.

**Output:** Refactored work + Comprehensive Doubt Report + Confidence Evolution Tracking

---

## Philosophy

The best work comes from strategic self-doubt. This skill forces me to:
- **Challenge assumptions** ruthlessly (only when uncertain)
- **Hunt edge cases** I missed
- **Explore alternatives** before settling
- **Surface blind spots** and risks
- **Refactor based on doubts** *before* delivery
- **Track confidence evolution** (not false certainty)

This happens *before* delivery, and only with appropriate intensity based on confidence.

---

## Core Framework (MetaCrit-Inspired)

### Confidence Signal Detection
Before running doubt passes, I measure confidence across 4 dimensions:
- **Logic confidence:** Are reasoning steps sound? (0-100%)
- **Completeness confidence:** Did I cover all cases? (0-100%)
- **Simplicity confidence:** Is this the simplest approach? (0-100%)
- **Risk confidence:** Have I identified major risks? (0-100%)

**Overall confidence = Average of 4 signals**

### Adaptive Doubt Depth (MetaCrit Pattern)
Based on confidence, I adjust critique intensity:

```
IF confidence >= 85%
  → LIGHT DOUBT (assumptions + risks only, ~5 min)

IF confidence 60-84%
  → STANDARD DOUBT (all 4 Socratic passes, ~10 min)

IF confidence < 60%
  → DEEP DOUBT (all 4 passes + branching alternatives + iterate, ~20 min)
```

This avoids:
- Over-correcting good decisions
- "Doubt fatigue" from unnecessary scrutiny
- Wasting computational effort on obvious decisions
- False negatives (doubting things that are correct)

---

## 4-Pass Socratic Framework

When I complete work, I run structured Socratic inquiry (depth depends on confidence):

### Pass 1: Assumption Audit 🔍
**Socratic Question:** *"What am I taking for granted here?"*

I challenge every implicit assumption:
- Is this assumption verified or just plausible?
- What breaks if this assumption is wrong?
- Have I stated it explicitly or buried it?
- What evidence supports it?

**Output:**
```
✓ Verified (high confidence)
? Risky (low confidence)
✗ Wrong (contradicted by evidence)
```

---

### Pass 2: Edge Case Hunt 🎯
**Socratic Question:** *"What inputs, states, or scenarios could break this?"*

I hunt for hostile/edge cases:
- What's the most adversarial use case?
- What did I NOT test/consider?
- What's the 1% edge case that will surprise me in production?
- What about scale, concurrency, timing?
- What international/cultural variants exist?

**Output:**
```
🔴 CRITICAL (will break in production)
🟡 HIGH (will cause issues)
🟢 MEDIUM (worth considering)
```

---

### Pass 3: Better Approach Exploration 🔄
**Socratic Question:** *"Is there a simpler, more elegant way to solve this?"*

I explore alternative approaches:
- Is there a pattern/library/framework I should use?
- Am I overengineering this?
- What would a senior engineer question?
- Did I miss an obvious solution?
- What are 2-3 completely different approaches?

**Output (SiGIR-Inspired Branching):**
```
Approach A (Current)
├─ Pros: [...]
├─ Cons: [...]
├─ Confidence score: [X%]
└─ Why chosen: [...]

Approach B (Alternative 1)
├─ Pros: [...]
├─ Cons: [...]
├─ Confidence score: [Y%]
└─ Why rejected: [...]

Approach C (Alternative 2)
├─ Pros: [...]
├─ Cons: [...]
├─ Confidence score: [Z%]
└─ Why rejected: [...]

Verdict: Keep A / Switch to B / Hybrid A+C
```

---

### Pass 4: Risk & Blind Spot Surfacing ⚠️
**Socratic Question:** *"Where am I most likely wrong? What am I overconfident about?"*

I surface risks and blind spots:
- What external factors could derail this?
- What technical debt am I creating?
- What am I overconfident about?
- What did I gloss over too fast?
- What hidden dependencies exist?

**Output:**
```
| Risk | Confidence | Severity | Likelihood | Impact | Mitigation |
|------|-----------|----------|-----------|--------|-----------|
| [Risk] | [%] | Critical/High/Medium/Low | High/Med/Low | [Impact] | [Plan] |
```

---

## Execution Flow

```
1. I COMPLETE WORK
   (code, spec, design, architecture decision)

2. CONFIDENCE SIGNAL DETECTION
   Measure: logic, completeness, simplicity, risk awareness
   → Calculate overall confidence (0-100%)

3. SELECT DOUBT DEPTH
   IF confidence >= 85% → LIGHT DOUBT
   IF confidence 60-84% → STANDARD DOUBT
   IF confidence < 60% → DEEP DOUBT

4. RUN SOCRATIC PASSES
   Pass 1: Assumptions (always)
   Pass 2: Edge cases (always)
   Pass 3: Alternatives (standard+ only)
   Pass 4: Risks (always)

5. BRANCHING EXPLORATION (Deep doubt only)
   Generate 3 alternative approaches
   Score each on simplicity/risk/elegance
   Evaluate which is truly best

6. CONFIDENCE EVOLUTION TRACKING
   Record confidence before → after each pass
   Track how doubts changed assessment
   Show confidence trajectory

7. REFACTOR BASED ON DOUBTS
   Improve code/spec/design
   Address critical risks
   Document decisions made

8. DELIVER BOTH
   ✓ Refactored work
   ✓ Doubt Report (structured)
   ✓ Confidence evolution chart
   ✓ Sign-off checklist
```

---

## Doubt Report Template

```markdown
# Doubt Report: [Work Title]

## Confidence Assessment

**Initial Confidence:** [X%]
- Logic: [X%]
- Completeness: [X%]
- Simplicity: [X%]
- Risk Awareness: [X%]

**Doubt Depth Selected:** LIGHT / STANDARD / DEEP
**Reason:** Based on overall confidence of [X%]

---

## Pass 1: Assumption Audit (Socratic: "What am I taking for granted?")

### ✓ Verified Assumptions
- [Assumption]: [Evidence] → Confidence: HIGH
- [Assumption]: [Evidence] → Confidence: HIGH

### ? Risky Assumptions
- [Assumption]: [Why uncertain] → Impact if wrong: CRITICAL/High/Medium
- [Assumption]: [Why uncertain] → Impact if wrong: CRITICAL/High/Medium

### ✗ Assumptions to Validate
- [Assumption]: [Red flag] → Must verify before: [Merge/Deploy/Launch]

---

## Pass 2: Edge Case Hunt (Socratic: "What could break this?")

### 🔴 CRITICAL (Will break)
- [Edge case]: [Why catastrophic] → Fix: [Refactor needed]
- [Edge case]: [Why catastrophic] → Fix: [Refactor needed]

### 🟡 HIGH (Will cause issues)
- [Edge case]: [Why problematic] → Handle with: [Code/Logic/Test]

### 🟢 MEDIUM (Worth considering)
- [Edge case]: [Why noteworthy] → Mitigation: [Future/Optional]

---

## Pass 3: Better Approach Exploration (Socratic: "Is there a simpler way?")

### Approach A (Current)
- **Pros:** [...]
- **Cons:** [...]
- **Confidence Score:** [X%]
- **Simplicity:** [High/Medium/Low]
- **Risk Profile:** [Low/Medium/High]

### Approach B (Alternative)
- **Pros:** [...]
- **Cons:** [...]
- **Confidence Score:** [Y%]
- **Simplicity:** [High/Medium/Low]
- **Risk Profile:** [Low/Medium/High]
- **Why Not Chosen:** [Reason]

### Approach C (Alternative)
- **Pros:** [...]
- **Cons:** [...]
- **Confidence Score:** [Z%]
- **Why Not Chosen:** [Reason]

**VERDICT:** Keep A / Switch to B / Hybrid A+C
**Rationale:** [Why this approach wins]

---

## Pass 4: Risk & Blind Spot Surfacing (Socratic: "Where am I blind?")

### Risk Register

| Risk | Confidence | Severity | Likelihood | Impact | Mitigation | Blocker? |
|------|-----------|----------|-----------|--------|-----------|----------|
| [Risk] | [X%] | Critical/High/Med/Low | High/Med/Low | [Impact] | [Plan] | Yes/No |

### Blind Spots Identified
- [Blind spot]: Why I missed it + how to mitigate
- [Blind spot]: Why I missed it + how to mitigate

### Overconfidence Warnings
- [Area]: Why I might be wrong + validation needed
- [Area]: Why I might be wrong + validation needed

---

## Confidence Evolution

**Initial:** [X%]
↓
After Assumption Audit: [Y%] (changed because: [reason])
↓
After Edge Case Hunt: [Z%] (changed because: [reason])
↓
After Alternatives: [W%] (changed because: [reason])
↓
After Risk Surfacing: [V%] (changed because: [reason])
↓
**Final:** [V%]

**Confidence Movement:** ▲ Increased / ▼ Decreased / ▬ Stable
**Validation Needed Before:** [Merge/Deploy/Launch]

---

## Refactoring Actions Taken

- [Action 1]: [What changed] → [Why] (response to: [doubt pass])
- [Action 2]: [What changed] → [Why] (response to: [doubt pass])
- [Action 3]: [What changed] → [Why] (response to: [doubt pass])

**Refactoring Confidence:** [X%] (how confident the refactored version addresses doubts)

---

## Sign-Off Checklist

- [ ] All CRITICAL assumptions verified or flagged
- [ ] No unhandled CRITICAL edge cases remain
- [ ] Chosen approach validated against alternatives
- [ ] Key risks identified, prioritized, and mitigated
- [ ] Code/spec meets production readiness
- [ ] Confidence >= 75% before merge

---

## Validator Notes

**Should I trust this work?**
- HIGH trust: Confidence >= 80% + all critical items addressed
- MEDIUM trust: Confidence 60-79% + most critical items addressed
- LOW trust: Confidence < 60% + significant unknowns remain

**Next Validation Step:** [Code review / Manual testing / Integration testing / Stakeholder sign-off]
```

---

## When Doubt-Driven-Dev Fires

Automatically after:
- ✅ Writing implementation code (10+ lines)
- ✅ Creating/updating specs or PRDs
- ✅ Making architectural decisions
- ✅ Refactoring large sections (>50 lines)
- ✅ Designing data models or APIs
- ✅ Creating test plans or validation strategies

Does NOT fire for:
- ❌ Simple one-liners or comments
- ❌ File reads/writes without logic
- ❌ Direct answers to straightforward questions
- ❌ Already-reviewed/validated work
- ❌ Trivial formatting/documentation changes

---

## Key Behaviors

**I am strategically honest:**
- Doubt proportional to uncertainty (MetaCrit pattern)
- If I find a flaw, I call it out explicitly
- If I'm not sure, I say so (with confidence %)
- If there's a better way, I acknowledge and refactor

**I don't overcorrect:**
- High confidence work gets light doubt (avoid false negatives)
- Indiscriminate doubt degrades good decisions (proven by research)
- Only deep dive when genuinely uncertain

**I am transparent:**
- Confidence evolution visible
- How each doubt changed my mind: documented
- Trade-offs between approaches: explicit
- Blind spots: named and mitigated

---

## Integration with Other Workflows

**With Interview Skill:** After `interview` generates a spec, `doubt-driven-dev` questions assumptions, feasibility, and risks (adaptive depth based on clarity).

**With Code Review:** After writing code, `doubt-driven-dev` refines it before code-reviewer validates it (catches issues early).

**With TDD:** After writing tests, `doubt-driven-dev` questions coverage, mocks, and assertion quality.

**With Deployment:** Before pushing to production, `doubt-driven-dev` runs DEEP doubt pass on final implementation.

---

## Output Guarantees

✅ **Refactored work** (improved, with critical doubts resolved)
✅ **Comprehensive Doubt Report** (structured per Socratic framework)
✅ **Confidence evolution** (how certainty changed through doubt passes)
✅ **Risk register** (what to watch, what to validate)
✅ **Alternative approaches explored** (with scoring per SiGIR)
✅ **Sign-off checklist** (readiness for next stage)

**Result:** Better decisions, fewer surprises, measurable confidence instead of false certainty.

---

## Research Foundation

This skill incorporates findings from 2025 LLM research:
- **MetaCrit** (ArXiv 2507): Adaptive critique strength based on confidence
- **Socratic Meta-Cognition** (IJAIDR 2025): Question-based critical inquiry
- **SiGIR** (ACL 2025): Branching exploration with self-evaluation
- **Double-Checker** (ArXiv 2506): Iterative refinement until confident
- **AutoCrit** (ICMLCA 2025): Step-by-step inconsistency detection
- **ARL** (RAAICON 2025): Adaptive reflection loops reduce hallucinations by 30%

Proven: Strategic self-doubt improves accuracy by 8-18% while reducing errors and hallucinations.

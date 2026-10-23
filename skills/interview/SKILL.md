# Interview Skill — Multilingual Global

Guided workflow for clarifying requirements, identifying hidden assumptions, and generating actionable specs before implementation begins. Combines proven discovery techniques (JTBD, Kano, RICE, Mom Test, Stakeholder Mapping) to eliminate ambiguity and prevent project failures.

**Supports:** English, Español, Français | **Scope:** Global for all projects

---

## When to Use

Trigger this skill whenever:
- **User says:** "interview", "clarify", "elaborate", "I have an idea", "especificar", "clarifier", "j'ai une idée"
- Before creating specs, PRDs, N8N workflows, or features
- There's ambiguity in requirements or unclear stakeholder needs
- You need to understand the real problem vs. what was stated
- Multiple stakeholders have conflicting ideas
- Any project where getting requirements right is critical to avoid rework

Use this skill to transform vague ideas into precise, verified, prioritized requirements with identified risks and clear acceptance criteria.

---

## Modes

### Quick Mode (5-7 questions)
Rapid validation for straightforward projects. Hits the essentials: what, why, success metrics, timeline, and immediate blockers.

### Deep Mode (15-20 questions)
Exhaustive discovery. Surfaces all edge cases, hidden assumptions, stakeholder conflicts, dependencies, and risk factors. Generates comprehensive spec + risk matrix + prioritization framework.

---

## Discovery Techniques Integrated

| Technique | What It Does | Why It Matters |
|-----------|--------------|----------------|
| **JTBD (Jobs To Be Done)** | Reconstruct: "When [situation], I want [motivation] so I can [outcome]" + Forces of Progress (push/pull/anxiety/habit) | Clarifies the real problem, not surface-level feature requests |
| **Mom Test** | Ask about PAST behavior, not opinions/hypotheticals | Eliminates bias, grounds answers in reality |
| **Stakeholder Mapping** | Identify who decides, who uses, who pays, who blocks → 2x2 matrix | Prevents "but the CEO wanted X" surprises late in delivery |
| **Assumptions Validator** | Challenge every claim: "Is this verified or believed?" | Surfaces blind spots, creates assumption register |
| **Kano Model** | Categorize features: Must-Have, Performance, Delighter, Indifferent | Prioritize smartly — avoid wasting effort on non-differentiating must-haves |
| **RICE Scoring** | Reach × Impact × Confidence / Effort = quantified priority | Removes politics, makes tradeoffs explicit |
| **Risk Assessment Matrix** | Severity × Probability → identify blockers early | Prevents production surprises, forces mitigation planning |
| **Dependency Graph** | Visualize: what depends on what, sequencing, critical path | Enables realistic timelines, spots cascade failures |

---

## Workflow Phases (Deep Mode)

### Phase 1: The "What" (Understanding the Job)
**Questions:**
1. What job is the user/stakeholder trying to accomplish? → **JTBD statement**
2. When do they need this? What triggers the search? → **Push factors** (problems with current solution)
3. What attracts them to a solution? → **Pull factors** (what they want)
4. What almost stops them? → **Anxiety** (doubts, risks, switching costs)
5. Success criteria — how do you measure this works? → **Outcome metrics** (concrete, measurable)

**Output so far:** JTBD statement + forces of progress + success criteria

---

### Phase 2: The "How" (Scope & Mechanics)
**Questions:**
6. MVP or full scope? Phases? → **Scope boundaries**
7. What systems/APIs/tools does this touch? → **Integrations**
8. Data: what comes in, what goes out, volume, frequency? → **Data flow**
9. Who actually uses this? Who decides? Who pays? → **Stakeholder roles** (Kano analysis input)

**Output so far:** Scope definition + integration list + data model + stakeholder matrix

---

### Phase 3: Gray Areas & Hidden Assumptions (The Tricky Part)
**Questions:**
10. What could go wrong? → **Edge cases**
11. For each claim, is this verified or assumed? → **Assumption register** (mark as ✓ verified or ? assumed or ✗ risk)
12. Depends on other projects/teams? → **Dependency list**
13. Hard constraints or "can't do" items? → **Boundary conditions**

**Output so far:** Risk register + assumption validation + dependency map

---

### Phase 4: Prioritization & Acceptance (Making It Actionable)
**Questions:**
14. Which features/outcomes are most important? Least? → **Kano classification** (Must/Performance/Delighter)
15. For each major feature: reach, impact, confidence, effort estimate? → **RICE scoring**
16. If timeline slips, which are non-negotiable? → **MoSCoW (Must/Should/Could/Won't)**

**Output so far:** Prioritized feature list + RICE scores + MoSCoW classification

---

### Phase 5: Risk & Acceptance Criteria (Closing the Gaps)
**Questions:**
17. What's the biggest risk? Severity? How likely? → **Risk matrix**
18. For each major feature, what must be true for it to work? → **Acceptance criteria** (auto-generated from narrative)
19. What's the first thing to build to validate assumptions? → **MVP definition**
20. Who needs to sign off? Any regulatory/compliance gates? → **Approval path**

**Output:** Complete spec with risk matrix + ACs + sign-off plan

---

## Output Template

```markdown
# Spec: [Project Name]

## Executive Summary
[1-2 paragraphs: problem → solution → expected impact]

## Jobs To Be Done
**Core Job Statement:**  
When [situation], I want [motivation], so I can [outcome].

**Forces of Progress:**
- Push (problems with current): [...]
- Pull (attraction to new): [...]
- Anxiety (concerns about switch): [...]
- Habit (inertia keeping old): [...]

## Success Criteria
- [ ] [Outcome metric 1: measurable, time-bound]
- [ ] [Outcome metric 2]
- [ ] [Outcome metric 3]

## Scope

### MVP (Must-Have for launch)
- [Feature 1]
- [Feature 2]

### Phase 2 (Should-Have)
- [Feature 3]

### Backlog (Could-Have)
- [Feature 4]

## Integrations
| System | Purpose | Criticality | Blocker? |
|--------|---------|-------------|----------|
| X | Y | High/Med/Low | Yes/No |

## Data Flow
[Input] → [Processing] → [Storage] → [Output]

## Stakeholder Map
| Role | Name/Title | Influence | Interest | Strategy |
|------|-----------|-----------|----------|----------|
| Decider | [...] | High | High | Manage closely |
| User | [...] | Low | High | Keep satisfied |
| Blocker | [...] | High | Low | Keep informed |

## Assumptions Register
| # | Assumption | Verified? | If Wrong, Impact |
|----|-----------|-----------|-----------------|
| 1 | [Claim] | ✓ Yes / ? Assumed / ✗ Risk | Severity |
| 2 | [...] | ? | High |

## Gray Areas Identified

### 🔴 Critical (Blocks delivery)
- [Issue]: [Why it matters]

### 🟡 Medium (Important, not blocking)
- [Issue]: [Why it matters]

### 🟢 Low (Nice to clarify)
- [Issue]: [Why it matters]

## Feature Prioritization

### Kano Classification
| Feature | Must-Have | Performance | Delighter | Reasoning |
|---------|-----------|-------------|-----------|-----------|
| Auth | ✓ | | | Without it, system fails |
| Dashboard | | ✓ | | Better UX = more adoption |
| Trending | | | ✓ | Unexpected delight |

### RICE Scoring
| Feature | Reach | Impact | Confidence | Effort | RICE Score | Priority |
|---------|-------|--------|-----------|--------|-----------|----------|
| Feature 1 | 500 | 3 | 80% | 5 days | 240 | P1 |
| Feature 2 | 200 | 2 | 70% | 3 days | 93 | P2 |

### MoSCoW
- **Must:** [Feature — non-negotiable for launch]
- **Should:** [Feature — adds value if possible]
- **Could:** [Feature — nice to have, lower priority]
- **Won't:** [Feature — explicitly out of scope this phase]

## Dependencies
- [ ] [System/Team/Project]: [What it blocks/enables], [Timeline]
- [ ] [System/Team/Project]: [Blocker status]

## Risk Assessment Matrix
| Risk | Severity | Probability | Impact | Mitigation | Owner |
|------|----------|-------------|--------|-----------|-------|
| API latency >2s | High | Medium | Project halted | Load test early | Dev |
| GDPR compliance unclear | Critical | High | Legal halt | Compliance review | Legal |
| Vendor dependency | Medium | High | Rework | Fallback plan | PM |

## Constraints & Boundaries
- **Cannot:** [Hard limitation]
- **Must:** [Non-negotiable requirement]
- **Should avoid:** [Anti-pattern to prevent]

## Acceptance Criteria
- [ ] AC1: [Condition], verifiable as: [how to test]
- [ ] AC2: [Condition], verifiable as: [how to test]
- [ ] AC3: [Condition], verifiable as: [how to test]

## MVP Definition
**Minimum to validate core job:** [Features only]  
**Timeline:** [Date]  
**Success = :** [Metric to hit]

## Approval & Sign-Off
- [ ] Product Owner: ____
- [ ] Engineering Lead: ____
- [ ] Legal/Compliance (if applicable): ____

## Next Steps
1. [Action + owner + deadline]
2. [Action + owner + deadline]
3. [Action + owner + deadline]
```

---

## Workflow

1. **User invokes** (any language): `/interview quick` or `/interview deep [idea]`
2. **Auto-detect language** (ES/EN/FR) from prompt
3. **Ask progressively** — phase by phase, waiting for responses
4. **Identify gaps** — ambiguities, assumptions, stakeholder conflicts
5. **Clarify via follow-ups** — "What if [edge case]?", "How do you know that?", "Who decides on X?"
6. **Generate document** — Complete spec `.md` with all 6 frameworks applied
7. **Highlight gray areas** — Call out critical unknowns, risks, assumption gaps
8. **Save locally** — Write `.md` to `[project]/specs/` (create folder if needed) + display in chat

---

## Language Auto-Detection

Detects based on initial prompt:
- **Spanish:** "interview", "especificar", "tengo una idea", "clarificar"
- **English:** "interview", "clarify", "I have an idea", "elaborate"
- **French:** "interview", "clarifier", "j'ai une idée", "détailler"

**Force language:** `/interview [es|en|fr] [quick|deep]`

---

## Adaptation Strategy

Ask at start:
- Quick or deep?
- Project type? (N8N workflow, feature, integration, API, app, etc.)
- Already have a draft spec? (If yes, refine vs. start from scratch)

Then ask context-specific follow-ups to fill gaps.

---

## Key Question Patterns (Adaptable)

**For JTBD:**
- "When does the user feel the pain with current solution?"
- "What event triggered the decision to change?"
- "What are they anxious about with the new solution?"
- "What would make them hesitate to switch?"

**For Mom Test (past behavior, no opinions):**
- "How did you do this last time?" (not "How would you...?")
- "Tell me about the last time you [action]"
- "What was the actual result?" (not "What should happen?")

**For Stakeholder Mapping:**
- "Who has to approve this?" (Decider)
- "Who uses it day-to-day?" (User)
- "Who would block it if unhappy?" (Blocker)
- "Who pays for it?" (Payer)

**For Assumptions:**
- "How do you know [claim]?"
- "What if that's not true?"
- "What's your confidence level?"

**For Kano:**
- "Without [feature], can the system work?" → Must-Have
- "Better [feature] = more satisfaction?" → Performance
- "Would [feature] surprise/delight users?" → Delighter

**For Risk:**
- "What's most likely to go wrong?"
- "If [assumption] fails, what's the damage?"
- "What's your mitigation plan?"

---

## Output Quality Guarantees

✅ Verified JTBD statement + forces of progress  
✅ Stakeholder map identifying decision authority  
✅ Assumption register (verified vs. assumed vs. risky)  
✅ Risk matrix with severity and mitigation  
✅ Kano classification for each major feature  
✅ RICE scoring for prioritization  
✅ Gray areas and blockers called out explicitly  
✅ Acceptance criteria tied to outcomes, not features  
✅ MoSCoW boundaries clear  
✅ Markdown spec saved to project + chat  

**Goal:** Prevent "we thought that meant X" disasters. Generate shared clarity before implementation starts.

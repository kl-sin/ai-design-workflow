# CRITIQUE-LOG.md
> Working doc — evaluation. Owned by the Researcher role.
> Use for: (1) pre-test design critique, (2) simulated walkthrough findings,
> (3) live usability testing rounds, (4) open evaluation issues.
> Do NOT put changelog, phase state, or approvals here — those live in PROJECT-STATUS.md.
>
> WHY SEPARATE FROM PROTOTYPE-FLOW: build logic and evaluation logic drift into each other
> if they share a file. Keep "what to build" and "what's wrong with what we built" apart.

---

## 1. Evaluation objective
> What this evaluation is trying to validate, in plain terms.

[objective]

---

## 2. Prototype under evaluation
| Item | Value |
|---|---|
| Version | [version] |
| File | `[file]` |
| Stage | [pre-test / simulated / live] |

---

## 3. Evaluation modes
> Three modes, used at different points. Be honest about which one a finding came from —
> a simulated walkthrough is not the same evidence as a real participant.

- **A. Pre-test design critique** — before any testing. Focus: fidelity, interaction
  correctness, consistency.
- **B. Simulated walkthrough** — a role-based persona walks through without real-user
  evidence. Focus: likely hesitation points, weak spots before testing.
- **C. Live usability testing** — a real participant or proxy. Focus: task completion,
  confusion, comprehension, confidence, real breakdowns.

---

## 4. Participants
- **[Primary]** — see `control/ROLE-GUIDE.md` for the persona definition
- **[Secondary]** — see `control/ROLE-GUIDE.md`

---

## 5. Testing format
> e.g. think-aloud protocol. Describe what the participant narrates and where handoffs happen.

[format]

---

## 6. Tasks
| ID | Task | What to observe |
|---|---|---|
| T1 | [task] | [observation] |

---

## 7. Success criteria
> Define success BEFORE testing so you're not grading on a curve afterward.

| Criteria | Threshold |
|---|---|
| [criterion] | [threshold, e.g. ≤ 60 sec / no help needed] |

---

## 8. Failure signals to watch
- [the specific wrong turn or confusion to look for]

---

## 9. Severity scale
| Severity | Meaning |
|---|---|
| Critical | Blocks the core task or breaks the concept |
| High | Major confusion; weakens the proof |
| Medium | Noticeable friction or unclear mental model |
| Low | Minor polish; does not block understanding |

---

## 10. Findings
> One entry per issue. ID, severity, the task/screen, evidence, why it matters, the fix,
> and status. Carry status into PROJECT-STATUS.md's resolution tracker.

#### [ID] — [summary]
- Severity: [level]
- Related task / screen: [...]
- Evidence: [what you observed]
- Why it matters: [impact on the proof]
- Recommendation: [the fix]
- Status: [Open / Pending verification / Resolved]

---

## 11. Live testing rounds
> Keep simulated findings and real-participant findings in clearly separate sections so you
> never mistake one for the other.

### Round U1 — [participant]
- Date: [ ]   Version: [ ]   Moderator: [ ]

| Total | Critical | High | Medium | Low |
|---|---|---|---|---|
| | | | | |

_Findings:_

---

## 12. Next evaluation step
1. [next action]

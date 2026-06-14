# PROJECT-STATUS.md
> Living dashboard. The human control tower. NEVER load this into the AI.
> You maintain it. It is the single source of truth for phase state, approvals,
> version history, open questions, and critique resolution.
>
> WHY THIS EXISTS: this is where the human stays in control. The AI works inside the other
> docs; this file is where you track what's approved, what's locked, and what still needs
> your sign-off. Keeping it out of the model's context keeps the model from "deciding" things
> that are yours to decide.

---

## 1. Current state

| Item | Value |
|---|---|
| Current phase | [phase] |
| Current working prototype | `[file]` |
| Prototype state | [e.g. v2 working pass] |
| Critique state | [not started / pre-test / live testing] |
| Next milestone | [what has to happen next] |

---

## 2. Phase gate log
> Each phase has entry criteria, exit criteria, and a required human sign-off. A phase is not
> "done" until you sign it off — this is the gate that keeps the AI from running ahead.

| Phase | Entry criteria | Exit criteria | Sign-off | Status | Date |
|---|---|---|---|---|---|
| 1 — Audit | Project set up | Audit matches reality; tokens confirmed | Owner review | | |
| 2 — Brief | Phase 1 signed off | Brief approved; open questions resolved/deferred | Owner review | | |
| 3 — Prototype | Phase 2 signed off | Prototype passes the "does this feel native?" gate | Owner review | | |
| 4 — Critique | Prototype stable for walkthrough | Findings resolved or deferred with rationale | Usability test | | |
| 5 — Case study | Phase 4 signed off | Workflow story is clear and documented | Owner review | | |

---

## 3. Owner verification
> The specific real-world facts you've personally confirmed. The AI must treat anything
> NOT verified here as an assumption, not a fact.

### Phase 1 — Audit
| Check | Status |
|---|---|
| [fact you verified] | ✓ / Pending |

**Audit sign-off:** [ ] Pending

---

## 4. Version registry
> Every doc and prototype with its version, date, and a one-line summary of what changed.

| Asset | Version | Date | Summary |
|---|---|---|---|
| `CONTEXT.md` | | | |
| `ROLE-GUIDE.md` | | | |
| `DESIGN-AUDIT.md` | | | |
| `CONCEPT-BRIEF.md` | | | |
| `DESIGN-SYSTEM.md` | | | |
| `PROTOTYPE-FLOW.md` | | | |
| `CRITIQUE-LOG.md` | | | |
| `[prototype file]` | | | |

---

## 5. Locked decisions
> Decided and closed. Do not reopen without explicitly noting it here. This is what stops
> the AI (and you) from re-litigating settled questions every session.

| Decision | Status | Source |
|---|---|---|
| [decision] | Locked | `[doc]` |

---

## 6. Open questions
> Anything unresolved, with the phase it belongs to and the current answer or next step.

| Question | Phase | Status | Answer / next step |
|---|---|---|---|
| [question] | | Open / Answered / Deferred | |

---

## 7. Critique resolution tracker
> Pulled from CRITIQUE-LOG.md. Tracks which issues are resolved and which are still open,
> so nothing falls through between rounds.

### Resolved
| ID | Summary | Resolved in | Status |
|---|---|---|---|
| | | | Resolved |

### Open / pending
| ID | Summary | Severity | Next step | Status |
|---|---|---|---|---|
| | | | | |

---

## 8. Human review gates
> The explicit moments where a human must look and approve before work continues.

| Gate | Trigger | Status | Date |
|---|---|---|---|
| Audit review | Do findings match reality? | | |
| Brief review | Is problem + scope correct? | | |
| Prototype fidelity review | Does this feel native to the product? | | |
| Pre-test readiness | Is the prototype stable enough to test? | | |
| Case study review | Is the workflow story clear and defensible? | | |

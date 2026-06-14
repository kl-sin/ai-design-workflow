# CONTEXT.md
> Drop this into every new AI session first. It is a session map, not a source of truth.
> If this file ever conflicts with a locked phase doc, the locked phase doc wins.
> Keep it short. Its only job is to orient the model fast and point it to the right files.

---

## Project snapshot

| | |
|---|---|
| Product | [the product or system you're designing for] |
| Goal | [one line: what this project is producing, e.g. "concept prototype for X"] |
| Current phase | [1 Audit / 2 Brief / 3 Prototype / 4 Critique / 5 Case study] |
| Active role this session | [set before starting work — see control/ROLE-GUIDE.md] |

---

## Core problem
> State the real problem in 2–4 sentences. Name the root cause, not just the symptom.

[problem statement]

**Root cause:** [the underlying gap, not the surface complaint]

---

## Core feature / scope
> What you're building, at a high level. Keep it tight — detail lives in the concept brief.

1. [capability 1]
2. [capability 2]
3. [capability 3]

---

## Workflow truth
> The real-world constraints the design must respect. These are easy for an AI to "design away"
> if you don't pin them down. List the things that must NOT change.

- [constraint 1]
- [constraint 2]
- [constraint 3]

---

## Load rules
> The point of the whole system: load only what the current task needs, not everything.
> This keeps context small, cheap, and focused, and lets you move between models.

| Task | Load |
|---|---|
| Before-state questions, current behavior, evidence | `source/DESIGN-AUDIT.md` |
| Confirming an audit claim against the live product | `source/AUDIT-VERIFICATION.md` |
| Scope, product logic, success criteria, decisions | `source/CONCEPT-BRIEF.md` |
| UI fidelity, implementation, interaction rules | `source/DESIGN-SYSTEM.md` |
| Screen sequence, prototype behavior | `working/PROTOTYPE-FLOW.md` |
| Design critique, fidelity / parity checks | `working/CRITIQUE-LOG.md` |
| Real participant data, task times, ease ratings | `working/USABILITY-SESSIONS.md` |
| Role lens or workflow lesson | relevant section of `control/ROLE-GUIDE.md` only |

**Never load:** `control/PROJECT-STATUS.md` — that is the human control tower (approvals, phase
gates, open questions, version history). It is maintained by you, not read into the model.

---

## File roles

### Source docs (source of truth)
- `DESIGN-AUDIT.md` = before-state truth
- `CONCEPT-BRIEF.md` = product truth
- `DESIGN-SYSTEM.md` = implementation truth

### Working docs (build & evaluation)
- `PROTOTYPE-FLOW.md` = build flow
- `CRITIQUE-LOG.md` = evaluation

### Control docs (session & project control)
- `ROLE-GUIDE.md` = role and workflow manual
- `PROJECT-STATUS.md` = project dashboard (human-maintained, never loaded)

---

## Session rules
> The non-negotiables. Adapt to your project, but keep the spirit: small context,
> explicit roles, rationale over output, and never building on a broken base.

1. Activate the relevant role before starting phase work
2. Load only the relevant role section from `ROLE-GUIDE.md`
3. Every decision needs a rationale, not just an output
4. State whether you are adding to the product or redesigning it — and stay consistent
5. Output is a concept prototype, not production code (adjust if your goal differs)
6. Never iterate on a broken prototype — restore a working version first, then fix
7. Flag scope creep immediately and defer it with a reason
8. Do not edit locked phase docs unless you explicitly reopen them
9. If docs conflict, prefer locked phase docs over this summary file

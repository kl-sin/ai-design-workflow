# AI Design Workflow

A reusable, markdown-based system for running product design work with AI — from UX audit to a user-tested prototype — without needing the product's design files.

I built this to design feature concepts for an existing SaaS product I had no Figma file or design system for. Working from only the public demo, I used MCP to extract the product's UI patterns and a structured set of markdown files to keep the AI focused, in-role, and under my control across a multi-phase project. This repo is the generalized, blank version of that system.

> **This was a solo project.** The named roles below (researcher, PM, designer, engineer) are **AI personas I had the model adopt** to pressure-test the work from different angles, not real teammates. Switching lenses deliberately is the technique; the headcount is one.

---

## Why this exists

A single long AI chat drifts. It forgets constraints, expands scope, redesigns things you told it to leave alone, and loses the thread between "what we're building" and "what's wrong with what we built." It also runs out of context on anything non-trivial.

This system fixes that by moving the project **out of the chat and into files**, each with one clear job. You load only what the current task needs. That keeps context small and cheap, keeps the AI in a single role at a time, and — because the whole project lives in portable files — lets you move it between models (e.g. Claude → Codex) when you hit token limits, without rebuilding anything.

The other half is **control**. Phase gates, owner-verified facts, and human review gates live in a dashboard the AI never reads. The AI works inside the other docs; the decisions stay with you.

---

## The three groups

```
template/
├── source/      # source of truth — what is, what to build, how it should look
│   ├── DESIGN-AUDIT.md        before-state truth: how the product works today + the gap
│   ├── AUDIT-VERIFICATION.md  optional: audit claims checked against the live product
│   ├── CONCEPT-BRIEF.md       product truth: problem, scope, decisions (locks after sign-off)
│   └── DESIGN-SYSTEM.md       implementation truth: tokens, components, patterns, behaviors
│
├── working/     # build & evaluation — the active work
│   ├── PROTOTYPE-FLOW.md      the screen-by-screen build logic and the proof it must deliver
│   ├── CRITIQUE-LOG.md        your own design critique + fidelity/parity checks
│   └── USABILITY-SESSIONS.md  real-participant data: task times, SEQ ratings, patterns
│
└── control/     # session & project control
    ├── CONTEXT.md             session map — load this first; it routes the AI to the right docs
    ├── ROLE-GUIDE.md          the role lenses, personas, activation prompts, reusable rules
    └── PROJECT-STATUS.md      human-only dashboard: phase gates, approvals, versions (never loaded)
```

*(CONTEXT.md sits in `control/` but is loaded first every session — it's the entry point. `AUDIT-VERIFICATION.md` and `USABILITY-SESSIONS.md` are optional — add them when audit accuracy or real-user testing is part of the project.)*

Two distinctions worth keeping straight, because they're easy to collapse and costly when you do:

- **Critique vs. sessions.** `CRITIQUE-LOG.md` is *your* judgment about the prototype (fidelity gaps, parity checks, what's wrong and why). `USABILITY-SESSIONS.md` is *evidence from real people* (what actually happened, what they rated it, what they suggested). Keeping them apart stops your opinions from blurring into participant findings.
- **Audit vs. verification.** `DESIGN-AUDIT.md` is what you claim about the product. `AUDIT-VERIFICATION.md` is how you confirmed each claim against the live product, with the path you took and the uncertainty that remains.

---

## How a session works

1. **Load `CONTEXT.md`.** It orients the AI: product, problem, current phase, and the load rules.
2. **Activate one role** from `ROLE-GUIDE.md` for the task at hand — `Act as [name]. [task].`
3. **Load only the docs that role needs.** Auditing? `DESIGN-AUDIT.md`. Building? `DESIGN-SYSTEM.md` + `PROTOTYPE-FLOW.md`. The load table in `CONTEXT.md` maps task → files.
4. **Work in phases** (Audit → Brief → Prototype → Critique → Case study). Each phase has entry and exit criteria and a human sign-off gate in `PROJECT-STATUS.md`. The AI doesn't advance phases on its own.
5. **You stay in the loop.** `PROJECT-STATUS.md` is never loaded into the model. It's where you record what's verified, what's locked, and what's approved.

A few rules that do a lot of the work:
- Every decision needs a **rationale**, not just an output.
- **Never iterate on a broken prototype** — restore a working version first, then fix.
- **Flag scope creep immediately** and defer it with a reason.
- If docs conflict, the **locked phase doc wins** over the session summary.

---

## Designing without design files

If you don't have the product's Figma or design system, you can still get native-looking output:

- Use **MCP** (or manual inspection) to read the live product's real UI — `getComputedStyle` in the browser gives you **exact** token values; screenshots give you layout patterns.
- Record them in `DESIGN-SYSTEM.md`, marking each value **DOM-confirmed (exact)** or **screenshot-observed (approximate)** so the AI knows what it can trust.
- The AI then designs *against the real product's patterns* instead of inventing generic UI.

---

## How to use this template

1. Copy the `template/` folder into your project.
2. Fill in `CONTEXT.md` first — product, problem, scope, constraints.
3. Write `CONCEPT-BRIEF.md` and `DESIGN-AUDIT.md` (your source of truth).
4. Adapt the roles and personas in `ROLE-GUIDE.md` to your project.
5. Start the phase loop, tracking everything in `PROJECT-STATUS.md`.

Every file is annotated — each section opens with a short note on what goes there and why.

---

## Background

I wrote up how this system performed on a real project, including where the AI-only workflow held up and where it strained enough that I brought a familiar tool back in, in a two-part series:

- Part I — [https://substack.com/home/post/p-196050924]
- Part II — [https://substack.com/home/post/p-200534637]

Full case study — [https://www.klsin.com/]

---

## License

MIT — use it, adapt it, build on it.

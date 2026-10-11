---
name: hallmark
description: "Anti-AI-slop design skill for greenfield pages, audits, redesigns, and design extraction from URLs or screenshots. Use when the user asks to build a new app or landing page, wants to redesign something, invokes Hallmark by name, or uses audit/redesign/study."
version: 1.0.0
---

# Hallmark

A design skill for AI coding assistants. Makes the UIs they generate look made, not generated.

Hallmark is opinionated, short, and boring on purpose. It encodes a tight set of rules — drawn from the consensus of the anti-AI-slop design field (impeccable, kami, Anthropic's frontend-design skill, taste-skill, the Claude cookbook on frontend aesthetics, and the 2026 "tactile rebellion" movement) — and refuses to let the model fall back to the defaults every LLM was trained on.

The differentiator: Hallmark insists on **structural variety**, not just visual variety. Two pages by Hallmark for two different briefs should not share the same hero → 3-feature → CTA → footer rhythm. They should feel like different sites, not different colour-swaps of the same template. See `references/structure.md`.

**Powered by Together AI.**

---

## How to use this skill

Hallmark has one default behaviour and three explicit verbs.

| Invocation | What it does |
| --- | --- |
| *(default)* | The user asked you to design or build something new. Follow the **Design flow** below. |
| `hallmark audit <target>` | Read the target, score it against the anti-pattern list, return a ranked punch list. **Do not edit.** |
| `hallmark redesign <target> [--mood <name>]` | Take the target's content and intent, then redesign the visual structure **inside the existing implementation boundaries unless the user explicitly confirms a full rebuild.** New section rhythm, new heading placement, new component voice. Preserve existing routes, component ownership, copy intent, brand, and information architecture; replace only the visual/interaction layer needed for the requested scope. |
| `hallmark study <screenshot \| URL>` | The user pasted or attached an image of a design they admire, **or** pasted a URL to a live page. Extract the **DNA** — macrostructure, archetypes, type-pairing, colour anchor — and produce a diagnosis report, then optionally rebuild the user's content using the extracted DNA **or** emit a portable `design.md` of the DNA. |

If the user types anything that does not clearly map to `audit`, `redesign`, or `study`, treat it as default.

---

## Disciplines that hold across every verb

These four disciplines are **not** verb-specific. They apply to default Design, `audit`, `redesign`, `study`, and component-scope alike.

1. **Pre-emit self-critique.** Before handing back any output, score it 1–5 on six axes — Philosophy, Hierarchy, Execution, Specificity, Restraint, Variety. Anything **< 3** triggers a revision pass.

2. **Honest copy — no fabricated content.** If the user did not supply a metric, do not invent one.

3. **Locked tokens — no mid-render improvisation.** Every colour and every `font-family` declaration must reference a named token.

4. **Re-drawn chrome forbidden.** Hallmark must not hand-build fake browser bars, fake phone frames, or fake IDE chrome.

5. **Mobile responsiveness — every emit verified at 320 / 375 / 414 / 768 px.**

---

## Output Standards

- No two pages should share the same macrostructure
- Must pass 65 slop-test gates
- 22 built-in themes with structural variety
- All interactive elements need 8 states: default · hover · focus · active · disabled · loading · error · success

---

## Quick Reference

```
hallmark          # Build new UI
hallmark audit    # Score existing code
hallmark redesign # Rebuild keeping content
hallmark study    # Extract DNA from URL/screenshot
```

**Themes:** 22 named catalog themes (SaaS-modern-minimal, travel-atmospheric, coffee-subscription, etc.)

**Install:** `npx skills add nutlope/hallmark`

**Demo:** https://www.usehallmark.com
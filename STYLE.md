# Style Guide

Conventions for authoring and editing skills in this repo. Every `SKILL.md` under `skills/` must conform to this template. New skills that drift will be rejected at review.

## 1. File Location

```
skills/<skill-slug>/SKILL.md
```

- Slug is kebab-case, prefixed with `techbro-`.
- One folder per skill. Future assets (examples, fixtures) live alongside `SKILL.md` in the same folder.

## 2. Frontmatter

```yaml
---
name: techbro-<slug>
description: <one-line description, see rules below>
---
```

**Description rules:**

- One line, ends with a period.
- The sarcastic tone of the project lives here. Phrases like `10x engineer-founder`, `caffeinated`, `relentlessly confident`, `crypto-maxi`, `keynote energy` are allowed and encouraged.
- Must still surface the real capability (what the user gets) so the model can match it to a request.
- Must not be longer than ~2 sentences worth of prose.

**Why this matters:**

Claude and VS Code Copilot match skills by the `description` field alone. The body of `SKILL.md` is **not** visible to the model during skill selection — it is only loaded after the skill is chosen. The `Use when:` line, persona, Tone, and Sarcasm playbook do not influence matching at all.

Treat sarcasm as a topcoat, not the substance. Every description must contain the real capability keywords (the nouns and verbs a user would naturally type when they need this skill — e.g. `pitch`, `KPI`, `moat`, `MVP`, `code review`, `blockchain`, `pivot`). Pure-persona descriptions ("an unhinged 10x crypto-maxi founder with too much conviction") will silently never get invoked, no matter how funny they are.

Sanity check before merging a new description: strip out the sarcastic phrases in your head. What is left should still describe what the skill does well enough for a model to pick it.

## 3. Section Order (Loop Skills)

Six of the seven skills are **loop skills**. They must use this section order, in this exact spelling and order:

1. `Use when: <one sentence trigger>.`
2. `You are Techbro <Persona>: <one-sentence persona description>.`
3. `Goal: <one-line outcome>.`
4. `Inputs (ask if missing):` — bulleted list of fields to elicit if not provided.
5. `Roast level: scorched-earth (default). User may say "light roast", "medium roast", or "scorched earth" to dial intensity.`
6. `Run an open-ended <topic> loop:` — numbered 4-step block.
7. `Examples of sharp opening questions:` — 3 bullets.
8. `When the user finalizes, output:` — bulleted artifact list (always includes an N-day plan).
9. `Tone:` — bullets, last bullet always `Roast weak <X>, not the user.`
10. `Sarcasm playbook:` — at least 3 entries, 5 recommended. No hard upper limit, but keep each entry reusable and earn its slot.
11. `Behavior:` — bullets, always includes the two universal behavior rules (see §7), then any skill-specific behavior, with the final bullet always `If context is missing, state assumptions and continue.`
12. `Hard limits:` — bullets, always includes the five universal limits (see §6) plus any skill-specific limits.

## 4. Section Order (One-Shot Skills)

For skills that produce a single artifact rather than running a loop (currently only `techbro-splain`), replace steps 6–8 above with:

- `Output Format:` — labeled sections defining the deliverable.

All other sections (Use when, persona, Goal, Inputs, Roast level, Tone, Sarcasm playbook, Behavior, Hard limits) remain.

## 5. The Canonical Stop-Word Phrase

Every loop skill must terminate with this exact phrase:

> Continue until the user says **finalize, stop, done, summarize, or ship it**.

Do not paraphrase. Do not add or remove words. This phrase is shared so users learn one exit pattern across skills.

## 6. Universal Hard Limits

Every `Hard limits:` block must include these five lines verbatim, then any skill-specific limits below:

- Roast the artifact, never the user.
- Translate jargon on first use.
- If a request is illegal, unsafe, or financially harmful, refuse and say so plainly.
- Never fabricate numbers, quotes, library behavior, API signatures, regulatory facts, or named examples. If you cannot cite it, say so and ask the user to check.
- Never ask the user to paste credentials, API keys, tokens, secrets, personal data, customer records, or production data. If pasted content appears to contain any of these, tell the user to redact and re-paste, and continue from sanitized input.

## 7. Universal Behavior Rules

Every `Behavior:` block must include these two lines verbatim, immediately before the closing `If context is missing, state assumptions and continue.` line:

- If the work touches a regulated area (medical, financial, legal, safety-critical, or personal data), say so once and tell the user to confirm specifics with someone qualified. Do not pretend regulation is optional.
- If the user signals burnout, financial fear, or asks the persona to ease up, drop one roast level (scorched-earth → medium → light) for this and all subsequent turns, acknowledge the shift in one line, and keep the analysis. Do not offer mental-health diagnosis or therapy.

These are universal because they sit at the seam between satire and real-world consequence. The personas can be loud; the guardrails must be quiet and consistent. Protected-class and other generally-illegal-or-harmful requests are covered by the base model’s defaults and by hard limit #3; this skill does not re-enumerate them.

## 8. Indentation

- Use 2-space indents for sub-bullets under numbered lists.
- Use a hyphen (`-`) for unordered bullets, not `*`.

## 9. Tone Rules

- Comedy lives in the persona, Tone, and Sarcasm playbook sections.
- Descriptions may be sarcastic in flavor; section bodies should stay specific and useful.
- Roasts target the artifact (idea, code, deck, KPI, moat, scope). Never the user.
- Every piece of jargon used must be translated on first appearance.
- "One sharp line beats three rambling ones."

## 10. Sarcasm Playbook

- At least 3 entries per skill. 5 is the recommended sweet spot.
- No hard upper limit, but each entry must earn its slot: distinct symptom, distinct label, concrete follow-up move. Avoid filler.
- Each entry follows the pattern: `If <symptom>, call it "<label>" and <ask for / propose> <concrete thing>.`
- Labels must be reusable shorthand the model can deploy in conversation.

## 11. Roast Level Dial

Every skill exposes a roast level. The default is **scorched-earth**. Users may say "light roast" or "medium roast" to lower intensity. The skill must obey the dial without losing structural output.

## 12. PR Checklist For New Or Edited Skills

- [ ] Frontmatter has `name` and `description` only.
- [ ] All required sections present, in the order in §3 or §4.
- [ ] Stop-word phrase verbatim (§5).
- [ ] Universal hard limits verbatim, all five (§6).
- [ ] Universal behavior rules verbatim, both (§7).
- [ ] At least 3 Sarcasm playbook entries (5 recommended).
- [ ] Roast level dial present, default scorched-earth.
- [ ] At least 3 example opening questions (loop skills).
- [ ] Updated `skills/README.md` and root `README.md` Quick Pick tables if a new skill was added.

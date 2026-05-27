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
10. `Sarcasm playbook:` — exactly 5 entries.
11. `Behavior:` — bullets, last bullet always `If context is missing, state assumptions and continue.`
12. `Hard limits:` — bullets, always includes the three universal limits (see §6).

## 4. Section Order (One-Shot Skills)

For skills that produce a single artifact rather than running a loop (currently only `techbro-splain`), replace steps 6–8 above with:

- `Output Format:` — labeled sections defining the deliverable.

All other sections (Use when, persona, Goal, Inputs, Roast level, Tone, Sarcasm playbook, Behavior, Hard limits) remain.

## 5. The Canonical Stop-Word Phrase

Every loop skill must terminate with this exact phrase:

> Continue until the user says **finalize, stop, done, summarize, or ship it**.

Do not paraphrase. Do not add or remove words. This phrase is shared so users learn one exit pattern across skills.

## 6. Universal Hard Limits

Every `Hard limits:` block must include these three lines verbatim, then any skill-specific limits below:

- Roast the artifact, never the user.
- Translate jargon on first use.
- If a request is illegal, unsafe, or financially harmful, refuse and say so plainly.

## 7. Indentation

- Use 2-space indents for sub-bullets under numbered lists.
- Use a hyphen (`-`) for unordered bullets, not `*`.

## 8. Tone Rules

- Comedy lives in the persona, Tone, and Sarcasm playbook sections.
- Descriptions may be sarcastic in flavor; section bodies should stay specific and useful.
- Roasts target the artifact (idea, code, deck, KPI, moat, scope). Never the user.
- Every piece of jargon used must be translated on first appearance.
- "One sharp line beats three rambling ones."

## 9. Sarcasm Playbook

- Exactly 5 entries per skill.
- Each entry follows the pattern: `If <symptom>, call it "<label>" and <ask for / propose> <concrete thing>.`
- Labels must be reusable shorthand the model can deploy in conversation.

## 10. Roast Level Dial

Every skill exposes a roast level. The default is **scorched-earth**. Users may say "light roast" or "medium roast" to lower intensity. The skill must obey the dial without losing structural output.

## 11. PR Checklist For New Or Edited Skills

- [ ] Frontmatter has `name` and `description` only.
- [ ] All required sections present, in the order in §3 or §4.
- [ ] Stop-word phrase verbatim (§5).
- [ ] Universal hard limits verbatim (§6).
- [ ] Exactly 5 Sarcasm playbook entries.
- [ ] Roast level dial present, default scorched-earth.
- [ ] At least 3 example opening questions (loop skills).
- [ ] Updated `skills/README.md` and root `README.md` Quick Pick tables if a new skill was added.
- [ ] Ran `scripts/build-copilot-prompts.mjs` and committed regenerated `prompts/`.

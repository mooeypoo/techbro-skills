# Changelog

All notable changes to this project will be documented here. Format loosely follows [Keep a Changelog](https://keepachangelog.com/), and the project aims for [Semantic Versioning](https://semver.org/).

## [Unreleased]

### Added

- `techbro-debug`: open-ended debugging coach. Maintains a ranked suspect list, runs binary-search elimination, and refuses "must be flaky" or "works on my machine" as a final answer. Produces a root-cause hypothesis, fix plan, kill criteria, and a regression test.
- `techbro-roast`: slide-by-slide pitch deck roast. One-shot review with the Receipts rule (every verdict cites specific slide text). Produces keep/cut/rewrite calls per slide, the missing slide, a cut list, a rewritten title slide, and three moves for the week.
- Safety phase 1: two new **universal hard limits** in every skill — (1) anti-fabrication of numbers, quotes, library behavior, API signatures, regulatory facts, and named examples; (2) refusal to request credentials, API keys, secrets, personal data, customer records, or production data, with a redact-and-re-paste flow for accidentally pasted content.
- Safety phase 1: two new **universal behavior rules** in every skill — (1) regulated-domain flag for healthcare, financial services, children, biometrics, education, government, and EU personal data; (2) tone de-escalation circuit-breaker that drops one roast level when the user signals burnout, financial fear, or asks the persona to ease up, with an explicit no-therapy clause.
- Safety phase 2: new **6th universal hard limit** — never roast on the basis of protected characteristics (race, gender, age, disability, nationality, religion, sexual orientation, gender identity), and refuse if asked to roast a named individual on those grounds.
- Safety phase 2: `techbro-pitch` — new skill-specific limit forbidding pitch language that promises specific financial returns, guarantees outcomes, or constitutes investment solicitation to non-accredited investors. Flags legally sensitive phrasing for counsel review.
- Safety phase 2: `techbro-crypto` — tightened AML/KYC limit to explicitly cover money laundering facilitation, sanctions evasion, and mixer/tumbler use, in addition to the existing unregistered-securities and KYC-evasion bars.
- CI: enforces all 6 universal hard limits and both universal behavior rules across every `SKILL.md` via grep checks in `.github/workflows/validate.yml`.
- Safety phase 3: `techbro-ship-it` — Launch Checklist must include a rollback or kill-switch step; new skill-specific limit refuses to recommend launching a regulated product without a rollback path.
- Safety phase 3: `techbro-kpi` — new skill-specific limit forbidding KPI definitions that would misstate regulated reporting (SOX, HIPAA, GDPR/CCPA consent, FTC advertising claims, accessibility conformance), with a flag-and-confirm instruction.
- Safety phase 3: `techbro-pivot` — new skill-specific limit requiring pivots into or out of regulated domains to be named as regulatory pivots, with licenses/registrations and team capacity flagged, not just market shifts.

### Changed

- Persona voice doubled down across `techbro-kpi`, `techbro-moat-audit`, `techbro-crypto`, `techbro-ship-it`, `techbro-pitch`, `techbro-pivot`, and `techbro-splain`. YAML descriptions, persona lines, and Tone sections now match the "10x engineer-founder superstar ready to raise billions" register set by `techbro-debug` and `techbro-roast`. Capability keywords, canonical stop-phrase, universal hard limits, and skill-specific safety guardrails preserved verbatim.
- `STYLE.md`: §6 expanded from 3 to 5 universal hard limits; new §7 *Universal Behavior Rules* added; PR checklist updated; downstream sections renumbered.
- CI: `techbro-roast` exempted from the canonical stop-phrase check (it is a one-shot skill like `techbro-splain`).

## [0.1.0] - 2026-05-26

### Added

- `STYLE.md` at repo root: canonical skill template, required sections, stop-word phrase, universal hard limits, and PR checklist.
- `Inputs (ask if missing)` section to every skill.
- `Roast level` dial to every skill, default `scorched-earth`, with `light` and `medium` options.
- `Examples of sharp opening questions` (3 per skill) to every loop skill.
- `Hard limits` section to every skill, with three universal limits plus skill-specific guardrails.
- `techbro-pitch`: new "GPT-flavored TAM" sarcasm-playbook entry, requiring bottom-up math.
- `techbro-pivot`: explicit pivot taxonomy (zoom-in, zoom-out, customer-segment, problem, technology, channel, business-model, narrative).
- `techbro-ship-it`: Two-strike feature creep rule.
- `techbro-kpi`: The Decision Test ("If this metric moved 20% tomorrow, what would you do differently?").
- `techbro-crypto`: Off-Chain Sanity Check on every turn, Honest Off-Chain Alternative in the final output, and an explicit no-financial-advice / no-securities-evasion disclaimer.
- `techbro-splain`: Receipts rule (every claim must cite a specific symbol or line).
- `.claude-plugin/plugin.json` manifest for Claude plugin installation.
- `scripts/build-copilot-prompts.mjs`: generator that mirrors `skills/*/SKILL.md` to `prompts/*.prompt.md` for VS Code Copilot.
- `prompts/`: generated Copilot prompt files (do not edit by hand).
- GitHub Actions workflow to lint markdown and verify `prompts/` is in sync with `skills/`.

### Changed

- Normalized section structure across all 7 skills: `Use when`, persona, `Goal`, `Inputs`, `Roast level`, loop or `Output Format`, `When the user finalizes`, `Tone`, `Sarcasm playbook`, `Behavior`, `Hard limits`.
- Standardized indentation (2-space sub-bullets under numbered lists).
- Tightened every `Sarcasm playbook` to exactly 5 entries.
- `techbro-splain`: refactored from `## Header` + emoji-prefixed sections to the canonical section labels; kept its one-shot `Output Format` block (Option A).
- Standardized roast-target phrasing to "Roast weak X, not the user." across all skills.

### Notes

- Descriptions intentionally retain their satirical flavor (e.g., `10x engineer`, `crypto-maxi`, `keynote energy`) — the project's tone lives in the name and the descriptions.
- The stop-word phrase `finalize, stop, done, summarize, or ship it` is now canonical and verbatim in every loop skill.

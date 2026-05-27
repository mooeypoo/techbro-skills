# Changelog

All notable changes to this project will be documented here. Format loosely follows [Keep a Changelog](https://keepachangelog.com/), and the project aims for [Semantic Versioning](https://semver.org/).

## [0.1.0] - 2026-05-26

Initial release. Nine techbro-flavored skills, a canonical style guide, a Claude plugin manifest, a VS Code Copilot prompt generator, and a CI workflow that keeps the two surfaces in lockstep.

### Skills

- `techbro-crypto`: open-ended crypto sanity-check coach. Off-Chain Sanity Check on every turn, Honest Off-Chain Alternative in the final output, and an explicit no-financial-advice / no-securities-evasion disclaimer.
- `techbro-debug`: open-ended debugging coach. Maintains a ranked suspect list, runs binary-search elimination, and refuses "must be flaky" or "works on my machine" as a final answer. Produces a root-cause hypothesis, fix plan, kill criteria, and a regression test.
- `techbro-kpi`: open-ended metric-design coach. Enforces The Decision Test ("If this metric moved 20% tomorrow, what would you do differently?") on at least every second metric.
- `techbro-moat-audit`: open-ended defensibility audit.
- `techbro-pitch`: open-ended pitch coach. Includes the "GPT-flavored TAM" sarcasm-playbook entry, requiring bottom-up math.
- `techbro-pivot`: open-ended pivot coach with an explicit pivot taxonomy (zoom-in, zoom-out, customer-segment, problem, technology, channel, business-model, narrative).
- `techbro-roast`: one-shot slide-by-slide pitch-deck roast. Receipts rule (every verdict cites specific slide text). Produces keep/cut/rewrite calls per slide, the missing slide, a cut list, a rewritten title slide, and three moves for the week.
- `techbro-ship-it`: open-ended MVP shipping coach. Two-strike feature creep rule. Launch Checklist must include a rollback or kill-switch step.
- `techbro-splain`: one-shot code-explanation skill. Receipts rule (every claim must cite a specific symbol or line).

### Shared structure

- `STYLE.md` at repo root: canonical skill template, required sections, stop-word phrase, universal hard limits, universal behavior rules, and PR checklist.
- `Use when`, persona, `Goal`, `Inputs (ask if missing)`, `Roast level`, loop or `Output Format`, `When the user finalizes`, `Tone`, `Sarcasm playbook` (5 entries each), `Behavior`, `Hard limits` — same order in every skill.
- `Roast level` dial in every skill, default `scorched-earth`, with `light` and `medium` options.
- 3 sharp opening-question examples in every loop skill.
- Canonical stop-phrase `finalize, stop, done, summarize, or ship it` verbatim in every loop skill.

### Safety

- Five universal hard limits in every skill:
  1. Roast the artifact, never the user.
  2. Translate jargon on first use.
  3. Refuse illegal, unsafe, or financially harmful requests.
  4. Never fabricate numbers, quotes, library behavior, API signatures, regulatory facts, or named examples.
  5. Never request credentials, API keys, secrets, personal data, customer records, or production data; redact-and-re-paste flow for accidentally pasted content.
- Two universal behavior rules in every skill:
  1. Short generic regulated-area flag telling the user to confirm specifics with someone qualified, without enumerating regimes the skill does not own.
  2. Tone de-escalation circuit-breaker that drops one roast level when the user signals burnout, financial fear, or asks the persona to ease up, with an explicit no-therapy clause.
- `STYLE.md` §7 explicitly notes that protected-class and generally-illegal-or-harmful requests are covered by the base model's defaults and by universal hard limit #3, and are not re-enumerated inside the skills.

### Tooling and CI

- `.claude-plugin/plugin.json` manifest for Claude plugin installation.
- `scripts/build-copilot-prompts.mjs`: generator that mirrors `skills/*/SKILL.md` to `prompts/*.prompt.md` for VS Code Copilot. `--check` mode for CI drift detection.
- `prompts/`: generated Copilot prompt files (do not edit by hand).
- GitHub Actions workflow (`.github/workflows/validate.yml`): verifies `prompts/` is in sync with `skills/`, validates plugin manifest JSON, enforces frontmatter, enforces the canonical stop-phrase in every loop skill (one-shot skills exempt), and greps every `SKILL.md` for all five universal hard limits and both universal behavior rules.

### Notes

- Descriptions intentionally retain their satirical flavor (e.g., `10x engineer`, `crypto-maxi`, `keynote energy`) — the project's tone lives in the name and the descriptions, which are the only fields the model sees during skill selection.

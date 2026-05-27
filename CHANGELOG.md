# Changelog

All notable changes to this project will be documented here. Format loosely follows [Keep a Changelog](https://keepachangelog.com/), and the project aims for [Semantic Versioning](https://semver.org/).

## [Unreleased]

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

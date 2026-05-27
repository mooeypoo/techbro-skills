# techbro-skills

A 🎭 satirical 🎭 set of skills for AI agents, inspired by recognizable slices of software developer culture.

Some of these skills will be surprisingly useful. Some will be mostly comedic. The value depends on how much you want to reproduce specific attitudes, communication styles, and decision habits from parts of the software industry.

This is `grill-it` with a hoodie, a growth deck, and unreasonably high conviction.

## What This Is

This repository is a prompt and behavior playground.

Each skill is a reusable instruction set you can give to an AI agent to simulate a particular "techbro" mode of thinking, critique, or execution.

Use this repo when you want:

- Your idea interrogated like it just asked for pre-seed funding
- Fast, spicy feedback with very high confidence and variable chill
- Brainstorm roleplay that is chaotic in tone but structured in output
- Satire on top, genuinely useful artifacts underneath

## What This Is Not

- A good idea. Probably.

## How To Use The Skills

1. Pick the skill that matches the flavor of chaos you need from your AI agent.
2. Drop in your idea, problem, context, and any emotionally charged constraints.
3. Let the agent cook, but do not let it run your company.
4. Keep the parts that are brilliant, ignore the parts that sound like a keynote.

## Quick Pick

| Skill | Use it when... |
| --- | --- |
| [techbro-pitch](skills/techbro-pitch/SKILL.md) | You need to stress-test one idea before pitching. |
| [techbro-pivot](skills/techbro-pivot/SKILL.md) | You need stronger market angles or narrative reframes. |
| [techbro-moat-audit](skills/techbro-moat-audit/SKILL.md) | You need to verify whether your advantage is actually defensible. |
| [techbro-ship-it](skills/techbro-ship-it/SKILL.md) | You need to cut scope and ship a credible MVP fast. |
| [techbro-kpi](skills/techbro-kpi/SKILL.md) | You need to separate decision-grade metrics from vanity metrics. |
| [techbro-crypto](skills/techbro-crypto/SKILL.md) | You want to force a blockchain angle onto an idea, no matter what. |
| [techbro-splain](skills/techbro-splain/SKILL.md) | You need a condescending-but-helpful breakdown of code, architecture, or system behavior. |

For the full comparison guide and detailed breakdowns, see [skills/README.md](skills/README.md).

## Install

This repo ships in two formats from one source of truth. The canonical skills live under `skills/<slug>/SKILL.md`. The VS Code Copilot prompt mirrors under `prompts/<slug>.prompt.md` are generated — do not edit them by hand.

### Claude (skills or plugin)

- **As loose Claude Skills:** copy any `skills/<slug>/` folder into your Claude skills directory.
- **As a Claude plugin:** install this repo via its plugin manifest at [.claude-plugin/plugin.json](.claude-plugin/plugin.json). All seven skills are auto-discovered from `skills/`.

### VS Code Copilot

- **Quick try:** copy any file from [prompts/](prompts) into your workspace's `.github/prompts/` folder. Invoke from Copilot Chat as a slash command.
- **As a Copilot prompt plugin:** point your Copilot plugin loader at this repo's `prompts/` directory.

## Development

### Repo layout

```
skills/                  Canonical SKILL.md files (source of truth)
prompts/                 Generated VS Code Copilot .prompt.md mirrors
scripts/                 Build and validation tooling
.claude-plugin/          Claude plugin manifest
STYLE.md                 Authoring rules every SKILL.md must follow
FUTURE_SKILLS.md         Backlog of candidate skills (not implemented)
CHANGELOG.md             Versioned change log
```

### Build the Copilot prompt mirrors

After editing any `skills/*/SKILL.md`, regenerate the Copilot prompt files:

```sh
node scripts/build-copilot-prompts.mjs
```

Then commit the regenerated `prompts/` along with your SKILL changes.

### Verify the repo is in sync

CI runs the same check on every push and pull request:

```sh
node scripts/build-copilot-prompts.mjs --check
```

This exits non-zero if `prompts/` is out of date relative to `skills/`. The full validation workflow lives in [.github/workflows/validate.yml](.github/workflows/validate.yml) and also enforces required frontmatter, the canonical stop-word phrase, and the universal hard limits.

### Adding or editing a skill

1. Read [STYLE.md](STYLE.md). Every skill must conform to its template.
2. Edit or create `skills/<slug>/SKILL.md`.
3. Run `node scripts/build-copilot-prompts.mjs`.
4. Update the Quick Pick table above and [skills/README.md](skills/README.md) if you added a new skill.
5. Add a `CHANGELOG.md` entry under `[Unreleased]`.

See [FUTURE_SKILLS.md](FUTURE_SKILLS.md) for a backlog of candidate skills.

## Notes For Users

- Satire is intentional. The tone may be overconfident, intense, or dramatic by design.
- Useful insights can still emerge from exaggerated personas.
- If a skill pushes too hard, reduce the roleplay intensity and keep the structure.

## License

Created with mixed emotions 😂😭 by [Moriel](https://moriel.tech).

MIT. See [LICENSE](LICENSE).

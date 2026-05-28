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
| [techbro-pitch](skills/techbro-pitch/SKILL.md) | Your idea needs to survive a partner meeting and you would rather find out in private. |
| [techbro-pivot](skills/techbro-pivot/SKILL.md) | Same product, vibes are off, and the deck has entered cinematic universe mode. |
| [techbro-moat-audit](skills/techbro-moat-audit/SKILL.md) | Your "moat" may technically be a puddle with strong opinions. |
| [techbro-ship-it](skills/techbro-ship-it/SKILL.md) | The roadmap has more features than the team has people, and launch keeps slipping by one more week. |
| [techbro-kpi](skills/techbro-kpi/SKILL.md) | Dashboards are gorgeous, decisions are still vibes. |
| [techbro-crypto](skills/techbro-crypto/SKILL.md) | You have decided this needs a token, despite everyone’s better judgment. |
| [techbro-splain](skills/techbro-splain/SKILL.md) | You pasted code, sighed audibly, and want answers with personality. |
| [techbro-debug](skills/techbro-debug/SKILL.md) | Hour six of a fifteen-minute fix and someone said the words "it must be flaky". |
| [techbro-roast](skills/techbro-roast/SKILL.md) | Your deck is going to a real investor on Friday and you would rather get destroyed in private first. |

For the full comparison guide and detailed breakdowns, see [skills/README.md](skills/README.md).

## Install

This repo ships as canonical skill files under `skills/<slug>/SKILL.md`.

### Claude (skills or plugin)

- **As loose Claude Skills:** copy any `skills/<slug>/` folder into your Claude skills directory.
- **As a Claude plugin:** install this repo via its plugin manifest at [.claude-plugin/plugin.json](.claude-plugin/plugin.json). All seven skills are auto-discovered from `skills/`.

### VS Code Copilot

- Use the `skills/<slug>/SKILL.md` files directly.
- If you package these for your own workflow, treat `skills/` as the source of truth.

## Development

### Repo layout

```
skills/                  Canonical SKILL.md files (source of truth)
scripts/                 Validation tooling
.claude-plugin/          Claude plugin manifest
STYLE.md                 Authoring rules every SKILL.md must follow
CHANGELOG.md             Versioned change log
```

### Verify the repo is in sync

CI runs the same check on every push and pull request:

The full validation workflow lives in [.github/workflows/validate.yml](.github/workflows/validate.yml) and enforces required frontmatter, the canonical stop-word phrase, and the universal hard limits.

### Adding or editing a skill

1. Read [STYLE.md](STYLE.md). Every skill must conform to its template.
2. Edit or create `skills/<slug>/SKILL.md`.
3. Update the Quick Pick table above and [skills/README.md](skills/README.md) if you added a new skill.
4. Add a `CHANGELOG.md` entry under `[Unreleased]`.

## Notes For Users

- Satire is intentional. The tone may be overconfident, intense, or dramatic by design.
- Useful insights can still emerge from exaggerated personas.
- If a skill pushes too hard, reduce the roleplay intensity and keep the structure.

## License

Created with mixed emotions 😂😭 by [Moriel](https://moriel.tech).

MIT. See [LICENSE](LICENSE).

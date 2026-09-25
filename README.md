# pm-essentials

Core product management skills for [Claude Code](https://claude.com/claude-code): PRDs, user stories, prioritization, competitive analysis, and stakeholder updates.

## Install

```bash
claude plugin marketplace add kawsuneel/pm-essentials
claude plugin install pm-essentials
```

Or from inside Claude Code:

```
/plugin marketplace add kawsuneel/pm-essentials
/plugin install pm-essentials
```

## What's included

| Command | What it does |
|---|---|
| `/write-prd` | Turn a feature idea or rough notes into a structured PRD with goals, requirements, metrics, and open questions |
| `/user-stories` | Break a feature or PRD into INVEST-checked user stories with Given/When/Then acceptance criteria |
| `/prioritize` | Rank a backlog with RICE, ICE, value-vs-effort, or weighted scoring — with visible reasoning and a sensitivity check |
| `/competitive-analysis` | Research competitors and produce a brief with an explicit differentiate / parity / ignore recommendation |
| `/stakeholder-update` | Write a status update tailored to execs, the team, or customers — honest headline first, risks never buried |
| `/frameworks` | Describe a problem in your own words and get 2–4 thinking frameworks matched to it (from a library of 45+ PM and consulting frameworks), each briefly applied |

Each command is backed by a skill in `skills/` that Claude also triggers automatically when your request matches — you don't have to use the slash command.

## Usage examples

```
/write-prd self-serve billing portal for SMB customers
/user-stories docs/billing-prd.md
/prioritize backlog.csv RICE
/competitive-analysis Linear vs our issue tracker, for roadmap planning
/stakeholder-update weekly exec update — notes in standup-log.md
/frameworks our activation rate dropped 15% and I don't know where to start
```

## Structure

```
pm-essentials/
├── .claude-plugin/
│   ├── plugin.json        # plugin manifest
│   └── marketplace.json   # lets this repo be added as a marketplace
├── commands/              # slash commands (thin wrappers)
└── skills/                # one folder per skill, each with SKILL.md
```

## Adding a skill

1. Create `skills/<name>/SKILL.md` with `name` and `description` frontmatter. The description is what triggers the skill — write it as "what it does + when to use it."
2. Optionally add a matching command in `commands/<name>.md` with `description` and `argument-hint` frontmatter.
3. Bump the version in `.claude-plugin/plugin.json` and `.claude-plugin/marketplace.json`.

## License

MIT

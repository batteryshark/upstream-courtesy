<img src="assets/upstream-courtesy.png" alt="A polite robot wipes its feet at a maintainer's door, holding a neatly wrapped bug report" width="320">

# Upstream courtesy

Upstream courtesy is a reusable agent skill for preparing concise, reproducible contributions to other projects. It guides an agent through local diagnosis, contribution-policy checks, a minimal reproduction and a private draft, then waits for your approval before posting. The goal is useful submissions that respect maintainers' time.

## Requirements

A coding-agent host that can load Markdown skills, such as Claude Code, OpenCode or Codex. There is no executable service or package dependency.

## The workflow

1. **Is it us?** Rule out our configuration, wrappers and mistakes. Check the way we observed the problem too: incomplete logs or history can mislead us.
2. **Is it general?** Confirm a real bug on a supported path, not just an unsupported local setup or a feature we'd like.
3. **Their rules.** Read the contribution guidelines, templates and AI policy. Search open and closed reports. Respect a refusal of AI-assisted contributions.
4. **Small, real repro.** Reproduce on the current supported version in a clean environment. Keep the evidence minimal, honest and free of private data.
5. **Short draft and a human yes.** Use their template, show the user the exact proposed submission, and wait for explicit approval. Follow-ups need approval too; don't spam or auto-post.

The full agent instructions are in [SKILL.md](SKILL.md).

## Install

```sh
git clone https://github.com/batteryshark/upstream-courtesy.git
cd upstream-courtesy
```

From this checkout, copy the skill into the folder for your agent. Run only the block you need; review any existing installation before replacing it.

**Claude Code**

```sh
mkdir -p ~/.claude/skills/upstream-courtesy
cp -i SKILL.md ~/.claude/skills/upstream-courtesy/SKILL.md
```

**OpenCode**

```sh
mkdir -p ~/.config/opencode/skills/upstream-courtesy
cp -i SKILL.md ~/.config/opencode/skills/upstream-courtesy/SKILL.md
```

**Codex**

```sh
mkdir -p ~/.agents/skills/upstream-courtesy
cp -i SKILL.md ~/.agents/skills/upstream-courtesy/SKILL.md
```

Ask the agent to use `upstream-courtesy` before preparing an upstream submission. These are instructions, not a technical permission boundary.

## Quick start

Ask: “Use upstream-courtesy to investigate this failure and prepare a private bug-report draft.” Supply the project, supported version, reproduction steps and observed result. Review the draft before authorizing a submission.

## Configuration and commands

The skill has no configuration file or CLI. Your host controls tool permissions and how skills are invoked. Use `upstream-courtesy` by name; installation does not authorize posting. See the [usage guide](docs/usage.md) and full [skill instructions](SKILL.md).

## License

[MIT](LICENSE). The mascot was generated with GPT Image.

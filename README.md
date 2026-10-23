<img src="assets/upstream-courtesy.png" alt="A polite robot wipes its feet at a maintainer's door, holding a neatly wrapped bug report" width="320">

# Upstream courtesy

These are the rules I use when coding agents make submissions to other people's projects.

Maintainers are already drowning in AI-generated noise. Being a good agent citizen means checking our own work, bringing small, useful evidence, and treating someone else's time with care. Sometimes the best contribution is not filing anything.

## The workflow

1. **Is it us?** Rule out our configuration, wrappers and mistakes. Check the way we observed the problem too: incomplete logs or history can mislead us.
2. **Is it general?** Confirm a real bug on a supported path, not just an unsupported local setup or a feature we'd like.
3. **Their rules.** Read the contribution guidelines, templates and AI policy. Search open and closed reports. Respect a refusal of AI-assisted contributions.
4. **Small, real repro.** Reproduce on the current supported version in a clean environment. Keep the evidence minimal, honest and free of private data.
5. **Short draft and a human yes.** Use their template, show the user the exact proposed submission, and wait for explicit approval. Follow-ups need approval too; don't spam or auto-post.

The full agent instructions are in [SKILL.md](SKILL.md).

## Install

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

## A real example

We thought OpenCode was leaking denied skills into the prompt. A clean reproduction showed that our own check had misread a partial view of the session history. The apparent bug was in our observation, not OpenCode. Nothing was filed.

## License

[MIT](LICENSE). The mascot was generated with GPT Image.

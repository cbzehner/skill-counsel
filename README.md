# Counsel

Route second-opinion work. The skill supports interviews, adversarial critique, premortems, model panels, and wildcard additions to plans that already mostly make sense. `magi` is treated as a keyword for `counsel --panel`.

## Use It For

- Stress-testing a plan before implementation
- Comparing approaches with a sharper outside view
- Finding one useful angle that the current plan missed
- Treating `magi` as familiar wording for the panel workflow

## Install

Clone the repo and run the installer:

```bash
git clone https://github.com/cbzehner/skill-counsel.git
cd skill-counsel
./install.sh all
```

Install targets:

- `./install.sh claude` installs to `~/.claude/skills/counsel`
- `./install.sh codex` installs to `~/.codex/skills/counsel`
- `./install.sh agents` installs to `~/.agents/skills/counsel`
- `./install.sh opencode` installs to `~/.config/opencode/skills/counsel`
- `./install.sh all --copy` copies files instead of symlinking

Manual install works too: symlink or copy `skills/counsel` into your agent's skills directory.

## Agent Support

This repo uses the plain `skills/counsel/SKILL.md` layout. Claude Code and Codex also get small plugin manifests at `.claude-plugin/plugin.json` and `.codex-plugin/plugin.json`.

Other agents can read the same `SKILL.md` file. If a host does not support a frontmatter field or tool name, ignore that field and follow the workflow text.

## Layout

```text
.claude-plugin/plugin.json
.codex-plugin/plugin.json
install.sh
skills/counsel/SKILL.md
README.md
LICENSE
```

## Public Notes

These repos are public. Keep private repo names, secrets, customer data, raw logs, cookies, and absolute filesystem paths out of examples.

## License

MIT

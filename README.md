# claude-skills

A collection of [Claude Code](https://claude.com/claude-code) skills used at
Orionics Ltd. Each skill encodes a reusable working practice: coding standards,
context hygiene, dependency safety, and clarifying ambiguity, that Claude loads
automatically when a task matches its description.

## What is a skill?

A skill is a directory containing a `SKILL.md` file with YAML frontmatter
(`name` and `description`) followed by guidance in Markdown. Claude reads the
`description` to decide when the skill is relevant and applies the guidance
while it works. See the
[skills documentation](https://docs.claude.com/en/docs/claude-code/skills) for
details.

## Skills in this repo

| Skill | Use it when |
| --- | --- |
| [`clarify-first`](clarify-first/SKILL.md) | A task is unclear, a decision could go multiple ways, or you'd otherwise fill a gap with a guess. Surface and resolve ambiguity instead of shipping a plausible-but-wrong interpretation. |
| [`coding-standards`](coding-standards/SKILL.md) | Writing or editing code, adding a module, or reviewing structure. Keep changes small, well-named, type-hinted, and consistent with the surrounding code. |
| [`dependency-safety`](dependency-safety/SKILL.md) | A change touches `pyproject.toml`, a lock file, or a Dockerfile. Only touch a dependency when necessary and make the smallest reviewable change. |
| [`lean-context`](lean-context/SKILL.md) | Exploring, understanding, or debugging a codebase. Scout with search, read only the slices you need, and keep the context window lean. |

## Installing

Skills are picked up from a `.claude/skills/` directory. To use these skills in a
project, copy or symlink the skill directories into that project's (or your
user-level) skills folder:

```bash
# User-level: available in every project
mkdir -p ~/.claude/skills
cp -r clarify-first coding-standards dependency-safety lean-context ~/.claude/skills/

# Or per-project
mkdir -p /path/to/project/.claude/skills
ln -s "$PWD"/clarify-first /path/to/project/.claude/skills/
```

## License

[MIT](LICENSE) © Orionics Ltd

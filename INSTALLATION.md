# Installation verification

Verified on 2026-10-27 using `skills@1.7.4` from the official npm registry.

Repository: https://github.com/Martinqi826/answer-with-words

Skill contents matched revision `674d10d388dbbda6040af9f5ed44d0a294127e3c`.

## Checks

| Check | Result |
| --- | --- |
| Discover repository skills with `--list` | PASS: exactly one skill, `answer-with-words` |
| Install for Codex, project scope, copy mode | PASS |
| Install for Claude Code, project scope, copy mode | PASS |
| Installed `SKILL.md` matches GitHub blob | PASS for both targets |
| Installed `agents/openai.yaml` matches GitHub blob | PASS for both targets |
| CLI lists the installed skill for both agents | PASS |

## Commands

```bash
npx --yes skills@1.7.4 add Martinqi826/answer-with-words --list
npx --yes skills@1.7.4 add Martinqi826/answer-with-words --skill answer-with-words -a codex claude-code --copy -y
npx --offline --yes skills@1.7.4 list -a codex claude-code
```

The test used a disposable project directory, disabled CLI telemetry, and isolated CLI state and npm cache. It did not install to any global or personal skill directory.

## Installed paths

- Codex: `.agents/skills/answer-with-words/`
- Claude Code: `.claude/skills/answer-with-words/`
- Project lock: `skills-lock.json`

## Content identity

| File | Git blob SHA |
| --- | --- |
| `SKILL.md` | `4e53cfd6b92a21ede178491b5205ba88f095bfda` |
| `agents/openai.yaml` | `7dafe63f79045516df0e3fd65b16a5418cd7a383` |

This verifies repository discovery, installation and file contents only. It does not establish end-to-end model behavior in either client, cross-platform runtime compatibility, quality improvements, token savings or ongoing usage.

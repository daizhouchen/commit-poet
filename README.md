# commit-poet

> Your `git diff` deserves better than "fix stuff". Get commit messages with style.

A [Claude Code](https://claude.ai/code) skill that generates accurate and creative commit messages from git diffs in 6 styles — from strict Conventional Commits to literary haiku and Lu Xun-style prose.

## Features

- **6 Commit Styles**

  | Style | Example |
  |-------|---------|
  | `conventional` | `feat(auth): add JWT token refresh mechanism` |
  | `emoji` | `✨ Add JWT token refresh; 🔧 Fix token expiry logic` |
  | `poetic` | `Tokens now dance their refresh waltz / expiry bugs laid to rest` |
  | `鲁迅` | `在无边的代码荒野中，我终于给认证模块续上了 token 的命` |
  | `haiku` | `New tokens refresh / Old bugs quietly depart / Auth stands strong again` |
  | `changelog` | `Added: JWT refresh, Fixed: token expiry, Changed: auth middleware` |

- **Accuracy First** — Creative styles never sacrifice accuracy of change description
- **Smart Analysis** — Detects change type (feature, fix, refactor, docs, mixed)
- **Multi-File Awareness** — Over 3 files changed: itemized list

## Installation

```bash
claude skill add daizhouchen/commit-poet
```

## How It Works

1. Claude reads `git diff --cached` (staged) or `git diff` (unstaged)
2. Analyzes: what was added/removed/modified, which modules affected
3. Generates commit message in your chosen style (default: conventional)

## Manual Usage

```bash
# Get formatted diff with statistics
./scripts/get_diff.sh --cached

# Get diff for specific path
./scripts/get_diff.sh --cached src/

# Get unstaged diff
./scripts/get_diff.sh
```

## Trigger Phrases

- "commit message" / "提交信息"
- "帮我写提交说明"
- "git commit"

## Project Structure

```
commit-poet/
├── SKILL.md                  # Skill definition with style rules and examples
├── scripts/
│   └── get_diff.sh           # Formatted diff helper script
├── references/
│   └── examples.md           # 5 diff types x 6 styles = 30 examples
└── README.md
```

## Style Rules

- **conventional** — Strictly follows [Conventional Commits](https://www.conventionalcommits.org/) spec
- **emoji** — Uses [gitmoji](https://gitmoji.dev/) conventions
- **poetic** — Short verse form, still technically accurate
- **鲁迅** — Classic Chinese literary style with coding metaphors
- **haiku** — 5-7-5 syllable structure
- **changelog** — Added/Fixed/Changed/Removed categories

## Requirements

- Git
- Bash (for the helper script)

## License

MIT

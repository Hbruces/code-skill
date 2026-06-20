# Claude Code Skills

This directory contains CodeConstitution and CodeRules converted to Claude Code skill format.

## Structure

```
ClaudeCode/
├── CodeConstitution/
│   ├── SKILL.md          # 编码宪法 - 完整编码规范 (P0/P1/P2)
│   └── companion/
│       └── checklist.md  # 自我合规检查清单
└── CodeRules/
    └── SKILL.md          # 编码规则速查 - 250+条规则速查表
```

## Conversion Notes

Both skills have been converted from CodeWhale format to Claude Code skill format:
- Added YAML frontmatter with `name`, `description`, `license`
- Added `Triggers` section for automatic skill activation
- Added `Usage` section with activation instructions
- Original rule content preserved exactly (no semantic drift)
- Installed to `.agents/skills/` as workspace-level global skills

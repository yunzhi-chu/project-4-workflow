# 学习来源

本项目改编自 [obra/superpowers](https://github.com/obra/superpowers) v5.1.0 (MIT 协议)，原作者 Jesse Vincent。

## 技能映射

| 本项目 | 来源 |
|--------|------|
| 需求打磨 | superpowers/brainstorming |
| 编写计划 | superpowers/writing-plans |
| 测试驱动开发 | superpowers/test-driven-development |
| 子代理开发 | superpowers/subagent-driven-development |
| 代码审查 | superpowers/requesting-code-review |
| 完成分支 | superpowers/finishing-a-development-branch |
| 完成前验证 | superpowers/verification-before-completion |
| 系统调试 | superpowers/systematic-debugging |

## 变更说明

原始 superpowers 是英文原版技能集，专为 Claude Code 等 AI 编码代理设计。
本项目做了以下改编：

- **中文化**：全部技能名称、说明、指令改为中文
- **精简**：保留核心工作流，移除与平台强相关的引用
- **个人化**：适配 Codex Desktop 环境，改用项目级 `.codex-plugin/` 部署

## 灵魂记忆系统

整理过程中涉及的 `soul-system` 技能（~/.codex/skills/soul-system/）学习来源：

- [thedotmack/claude-mem](https://github.com/thedotmack/claude-mem) — 结构化记忆、双层存储、schema 版本、FTS 搜索
- [microsoft/markitdown](https://github.com/microsoft/markitdown) — 插件架构、entry_points 发现、优先级注册模式
- [multica-ai/andrej-karpathy-skills](https://github.com/multica-ai/andrej-karpathy-skills) — Karpathy 四项行为准则

# Project 4 Workflow

从 [obra/superpowers](https://github.com/obra/superpowers) 改编的个人中文工作流技能集，为 Codex Desktop 提供完整的软件开发方法论。

## 这是什么

一个轻量级的技能框架，让你的编码代理按结构化的流程工作——从需求打磨到分支完成，每一步都有对应的技能指导行为。

### 工作流

```
用户需求 → 需求打磨 → 编写计划 → 子代理开发
  └─ 每任务: TDD → 代码审查 → 循环
全部完成 → 完成分支 / 完成前验证
遇到 bug → 系统调试
```

### 包含的技能

| 技能 | 对应 superpowers | 作用 |
|------|-----------------|------|
| 需求打磨 | brainstorming | 将模糊想法转化为设计文档 |
| 编写计划 | writing-plans | 设计拆分为可执行任务 |
| 测试驱动开发 | test-driven-development | RED → GREEN → REFACTOR |
| 子代理开发 | subagent-driven-development | 逐任务分派子代理 + 二阶段审查 |
| 代码审查 | requesting-code-review | 规格合规 + 代码质量 |
| 完成分支 | finishing-a-development-branch | 合并/PR/保留/丢弃决策 |
| 完成前验证 | verification-before-completion | 证据驱动的完成声明 |
| 系统调试 | systematic-debugging | 四阶段根因分析 |

## 使用方式

### 作为项目级插件（推荐）

将 `.codex-plugin/` 和 `skills/` 复制到你的项目根目录，Codex Desktop 在打开该项目时会自动发现并加载这些技能。

### 从个人市场安装

1. 注册个人市场：确保 `~/.agents/plugins/marketplace.json` 包含本项目
2. 在 Codex Desktop 插件侧边栏搜索 `project-4-workflow` 并安装
3. 新线程启动后技能自动可用

## 系统要求

- Codex Desktop（桌面版）
- 工作目录包含 `.codex-plugin/` 目录（项目级部署）或已安装个人市场

## 技术栈

- **SKILL.md** — Codex 技能格式，YAML 前注 + Markdown 指令
- **.codex-plugin/plugin.json** — Codex 插件清单
- **AGENTS.md** — 会话初始指令

## 改编来源

本项目基于 superpowers v5.1.0 改编。

- **原始作者**: Jesse Vincent
- **原始仓库**: [obra/superpowers](https://github.com/obra/superpowers)
- **协议**: MIT

详见 [SOURCES.md](SOURCES.md)。

## 协议

MIT

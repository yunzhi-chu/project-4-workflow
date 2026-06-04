# 灵魂记忆系统整理 - 设计方案

> 基于 project-4-workflow 工作流完成。
> 目标：系统化整理 soul-system 的代码结构、测试、文档。
> 铁律：功能不能有一点变化。

## 现状

soul-system v1.4.0 已安装在 ~/.codex/skills/soul-system/，Python 包结构：
- soul/__init__.py, _soul.py, _base.py, _types.py, _exceptions.py, __about__.py
- soul/backends/__init__.py, _file.py, _sqlite.py
- tests/（4 个独立测试文件，非 pytest 兼容）
- 文档散落，版本不一致

### 测试基线
极端测试 26/27 通过。1 个失败是测试文件硬编码版本号 1.3.0 与代码 1.4.0 不匹配，属于测试过时，不改。

### 发现的代码问题（不改动，保留原样）
- _file.py:64 regex `[w+]` 本意是 `\w+`，但修改会改变行为
- _file.py:113 缩进错位，但修改会改变行为
- SKILL.md 写 v1.3，代码是 1.4.0

## 整理方案

### 1. 项目结构
- 维持现有布局不变（不做 src/ 迁移，避免改变安装方式）
- 仅整理 tests/ 和 docs/

### 2. 测试增强
- 添加 tests/conftest.py（pytest 兼容层）
- 不修改任何现有测试文件的逻辑

### 3. 文档
- README.md 更新版本为 1.4.0
- CHANGELOG.md 补全
- docs/ 补充缺失的文档

### 4. backends/__init__.py
- 导出更清晰的 Backend 类名

### 5. 代码注释
- 在 _file.py 和 _sqlite.py 的分组方法前加注释边界

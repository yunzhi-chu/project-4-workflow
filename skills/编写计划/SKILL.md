---
name: 编写计划
description: 拿到已批准的设计后，在碰代码之前使用。将设计拆分为可执行的微型任务。
---

# 编写计划

将设计文档拆分为颗粒度的实施计划。假设执行者没有项目上下文。

## 前置条件

- 设计文档已批准并保存到 `docs/设计/`

## 计划文档结构

````markdown
# [功能名] 实施计划

> **说明：** 每个任务 2-5 分钟，包含完整代码和验证步骤。

**目标：** [一句话描述]

**架构：** [2-3 句说明方案]

**技术栈：** [关键技术和库]

---
````

## 任务粒度

每个步骤是一个独立操作（2-5 分钟）：

- "写测试" — 一个步骤
- "运行确认测试失败" — 一个步骤
- "写最少代码让测试通过" — 一个步骤
- "运行全部测试" — 一个步骤
- "提交" — 一个步骤

## 任务结构

````markdown
### 任务 N：[组件名]

**文件：**
- 创建：`src/path/to/file.py`
- 修改：`src/path/to/existing.py:123-145`
- 测试：`tests/path/to/test.py`

- [ ] **步骤 1：写失败的测试**

```python
def test_specific_behavior():
    result = function(input)
    assert result == expected
```

- [ ] **步骤 2：运行确认测试失败**

运行：`pytest tests/test.py::test_name -v`
预期：FAIL

- [ ] **步骤 3：写最少实现代码**

```python
def function(input):
    return expected
```

- [ ] **步骤 4：运行确认测试通过**

运行：`pytest tests/test.py::test_name -v`
预期：PASS

- [ ] **步骤 5：提交**

```bash
git add -A && git commit -m "feat: add specific feature"
```
````

## 禁止

计划中不得出现：
- TBD / TODO / "稍后实现"
- "添加适当的错误处理" 而不给出具体代码
- "同上" 或 "类似任务 N" — 每步必须完整
- 未在任何任务中定义的类型/函数/方法引用

## 自检清单

写完计划后检查：
1. 设计的每个需求是否都能对应到具体任务？
2. 有无占位符？
3. 前后任务之间的类型/接口是否一致？

## 执行交接

保存计划后询问用户选择：子代理模式（逐任务分派）还是内联执行模式。

---

---
> 来源：改编自 [obra/superpowers](https://github.com/obra/superpowers) 的 writing-plans 技能，内容经简化和中文化处理。

---
name: 完成分支
description: 实施完成、所有测试通过后使用。验证测试后提供合并/PR/保留/丢弃选项。
---

# 完成分支

验证测试 → 呈现选项 → 执行选择 → 清理。

## 步骤 1：验证测试

运行完整测试套件：
```bash
npm test / cargo test / pytest / go test ./...
```

**测试失败则停在这里**，不能进入下一步。

## 步骤 2：呈现选项

```
实施完成。请选择：

1. 合并到主分支（本地）
2. 推送并创建 Pull Request
3. 保留分支稍后处理
4. 丢弃本次工作（需输入 discard 确认）
```

## 步骤 3：执行

### 选项 1：合并
```bash
git checkout main && git pull
git merge <feature-branch>
# 验证测试
# 删除 worktree
git branch -d <feature-branch>
```

### 选项 2：PR
```bash
git push -u origin <feature-branch>
gh pr create --title "<标题>" --body "变更说明"
# 不清理 worktree（用于 PR 迭代）
```

### 选项 3：保留
报告分支名和路径。

### 选项 4：丢弃
要求输入 `discard` 确认后才执行。

## 完成前验证

**在声称任何工作完成之前：**

1. 标识：什么命令能证明这个声明？
2. 运行：执行完整命令，读完整输出
3. 验证：输出确认声明成立？
4. 只有确认后，才能声称完成。

**没有验证证据的"已完成"声明是不诚实的。**

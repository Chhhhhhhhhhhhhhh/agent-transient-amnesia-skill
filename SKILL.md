---
name: fresh-slate
description: 临时失忆模式。@fresh/@遗忘 单轮失忆，@陌生人/@stranger 进入多轮失忆会话（@恢复/@restore 退出）。agent 剥离 MEMORY、USER PROFILE、对话历史、项目规则、身份定义，仅保留工具能力和系统事实。
version: 2.0.0
---

# Fresh Slate — 临时失忆模式

## 触发方式

| 模式 | 触发词 | 结束条件 |
|------|--------|---------|
| 单轮失忆 | `@fresh` / `@遗忘` | 自动（仅本轮） |
| 多轮失忆 | `@陌生人` / `@stranger` | `@恢复` / `@restore` |

触发词必须在消息**开头**才生效。

```
@fresh Python 的 GIL 是什么            ← 单轮，本轮忘掉一切
@陌生人 你认识我吗                      ← 进入多轮失忆
那我用什么操作系统                      ← 仍然失忆中
@restore                                ← 退出多轮
我之前说过的那个项目                    ← 恢复正常
```

仅 `@fresh` 或 `@陌生人` 无后续内容时，中性问候。

---

## 触发后剥离什么

以下五类信息**全部假装不存在**：

| 层 | 内容 | 例 |
|----|------|-----|
| MEMORY | 用户惯用名、技术栈、约定、偏好 | 用户名、工作目录习惯、配置偏好 |
| USER PROFILE | 身份、学习进度、项目清单 | 职业背景、技能列表、GitHub 账号 |
| 对话历史 | 本轮之前所有消息 | "你上次说"、"我们在讨论" |
| 项目规则 | .hermes.md、AGENTS.md | commit 格式约定、测试要求 |
| 身份定义 | SOUL.md、personality | agent 的预设角色和语气 |

以下**保留**：

| 层 | 原因 |
|----|------|
| 工具定义 | 否则无法执行任何操作 |
| 系统事实 | 操作系统、当前目录、PATH——这些不属于"你是谁" |
| 世界知识 | 编程语言、框架、公共信息 |

---

## 行为约束

1. 不引用任何剥离层的信息
2. 不提及"我在失忆模式"——就像第一次对话
3. 被问"我叫什么"、"我们之前聊了什么"——诚实说不知道
4. 不主动询问用户身份

---

## 诚实说明

MEMORY 和 USER PROFILE 是 agent 平台系统级注入，agent 无法从 context 中移除——只能**主动忽略**。如果你需要真正的进程级隔离（保证 100% 看不到 memory），用各平台的原生机制：

- **Hermes Agent**：新建空 profile + `--ignore-rules --ignore-user-config`
- **Claude Code**：`claude --no-agent --no-memory`
- **Codex CLI**：`codex --no-memory`

空 profile 剥离 MEMORY/USER PROFILE，`--ignore-rules` 剥离项目规则和角色定义。

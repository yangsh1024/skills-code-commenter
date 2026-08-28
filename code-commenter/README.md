# Code Commenter

一个仅手动调用的跨客户端代码注释 Skill。它为 Java、JavaScript、TypeScript 和 Python 代码添加简洁中文注释，重点说明业务目的与设计原因，而非复述代码。

## 特性

- 分层处理类/接口、方法/函数和关键业务步骤注释。
- 使用目标语言的标准文档注释格式。
- 跳过 getter/setter、生成代码与显而易见的语句。
- 不说明依赖、调用、传参或实现步骤。
- 仅变更注释；绝不修改任何代码、格式或依赖。
- Claude Code 与 Codex 均不自动调用。

## 安装

将整个 `code-commenter` 目录复制到客户端的 Skills 目录。

| 客户端 | 安装目录 |
| --- | --- |
| Claude Code | `~/.claude/skills/code-commenter` |
| Codex | `$CODEX_HOME/skills/code-commenter`；未设置时为 `~/.codex/skills/code-commenter` |

重启客户端或刷新 Skills 列表后生效。

## 调用

| 客户端 | 调用示例 |
| --- | --- |
| Claude Code | `/code-commenter 给这个订单取消函数添加注释` |
| Codex | `$code-commenter 给这个订单取消函数添加注释` |

“添加注释”“给代码加注释”“注释代码”“帮我注释”可以作为调用后的自然语言说明，但不会触发自动调用。

## 兼容性

- `SKILL.md` 的 `disable-model-invocation: true` 使 Claude Code 保持仅手动调用。
- `agents/openai.yaml` 的 `allow_implicit_invocation: false` 使 Codex 仅在显式使用 `$code-commenter` 时加载此 Skill。

## 项目结构

```text
code-commenter/
├── SKILL.md
├── agents/
│   └── openai.yaml
└── README.md
```

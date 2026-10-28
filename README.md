# limen_handoff

用于跨 AI 工具、跨会话交接任务上下文的两个配套 Skill。切换工具或打开新对话时，将当前任务进度保存为本地 Markdown 文档，让接手的 AI 了解已完成事项、关键决策、踩过的坑和下一步，减少重复解释与排查。

## 两个 Skill

| Skill | 功能 |
| --- | --- |
| `dbk-handoff` | 整理当前会话的任务目标、核心文件、已完成事项、已排除方案和下一步，生成交接快照及接手提示词。 |
| `dbk-pickup` | 读取交接快照，核对 Git 工作区状态（如适用），简短汇报当前进度与下一步，默认等待用户确认后继续。 |

## 安装与使用

```bash
npx skills add Limen-AI-Lab/limen_handoff -g -y
```

在支持 Agent Skills 的工具中安装后，对当前 AI 说“做个交接”，再把生成的提示词粘贴到新会话，让接手方使用 `dbk-pickup` 读取报告。

交接文档保存在项目的 `.agent/handoff/` 中，包含独立快照与 `latest.md`。默认交接当前会话掌握的上下文，不会自动汇总整个项目的所有对话；多个会话请分别保存并引用各自快照。跨电脑使用时，需要一并传递相关项目文件与交接文档。

## 来源与许可

本仓库收录自 [DBinK/dbk-handoff](https://github.com/DBinK/dbk-handoff) 的两个 Skill（v0.3.0），保留原技能名称与内容，另编写本中文简介。原作者为 DBinK，采用 [MIT License](LICENSE)。
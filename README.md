<!-- SPDX-FileCopyrightText: 2026 Yang Mingyu; SPDX-License-Identifier: GPL-3.0-only. See LICENSE. -->

[English](README.en.md) | 简体中文

# Career Evidence Bank 职业事实库

一个遵循 [Agent Skills 开放格式](https://agentskills.io/specification)的职业事实库 Skill：通过访谈、旧简历、工作资料及可访问的项目记录，整理可追溯的职业经历；用户需要时，再从中挑选适合目标岗位的真实素材。Skill 的工作流程不依赖 Codex、GitHub MCP 或某个特定模型。

它适合经历还少的学生，也适合多年未更新简历的从业者。重点是**收集事实、核对来源、说清本人贡献**，不把一次提交解释为项目主导或商业成果。

## 能做什么

- 重建经历时间线，标出来源、冲突与待核实内容。
- 在用户授权且工具可用时结合代码托管记录；没有账号或连接时也能用口述、旧简历和文件继续工作。
- 维护可更新的背景叙述和逐条可核实的事实记录。
- 用户要求岗位匹配或简历时，将真实岗位要求映射到可公开的事实。

本 Skill 不自动投递，也不自动公开个人资料。

## 安装到不同 Agent

下载本仓库，**保留整个 `career-evidence-bank` 文件夹**及其中的 `SKILL.md`、`references/`。将文件夹放进所用 Agent 的技能目录；`~` 表示用户主目录，Windows 下可对应 `%USERPROFILE%`。以下路径来自各产品文档，是安装示例，不表示我们已在每个平台完成运行测试。

| Agent | 用户级目录或导入方式 | 项目级目录 |
|---|---|---|
| [Codex](https://learn.chatgpt.com/docs/build-skills) | `~/.agents/skills/career-evidence-bank/` | `.agents/skills/career-evidence-bank/` |
| [Claude Code](https://code.claude.com/docs/en/skills) | `~/.claude/skills/career-evidence-bank/` | `.claude/skills/career-evidence-bank/` |
| [Cursor](https://cursor.com/help/customization/skills) | `~/.agents/skills/career-evidence-bank/` | `.agents/skills/career-evidence-bank/` |
| [Gemini CLI](https://geminicli.com/docs/cli/using-agent-skills/) | `~/.agents/skills/career-evidence-bank/` | `.agents/skills/career-evidence-bank/` |
| [WorkBuddy](https://cloud.tencent.com/document/product/1831/134432) | 在技能界面选择“添加技能 → 上传技能”，导入本地技能包 | 依产品界面 |

在 Codex 中可输入 `$career-evidence-bank`；Claude Code 和 Cursor 的调用语法各有不同；Gemini CLI 可用 `/skills list` 检查是否发现。**通用做法是直接用自然语言提出下面的任务**，让支持 Agent Skills 的产品按描述选择本 Skill。安装或更新后若未出现，请按相应产品文档刷新技能列表或重启会话。

其他 Agent（包括未在本仓库实测的产品）若支持 Agent Skills 格式，请按其文档放置文件夹；若只支持普通提示词，可让它读取 `SKILL.md`，并在建库时按需读取 `references/fact-records.md`、在岗位匹配时读取 `references/job-tailoring.md`。普通提示词方式不保证自动发现或调用。

## 第一次使用

一段经历口述或一份旧简历就能开始；代码托管记录和目标岗位可以之后再补。附上资料并发送：

> 请按 career-evidence-bank 的方法，先帮我建立职业事实库。区分我确认的经历、资料能佐证的内容和待核实主张，记录我实际负责的范围及哪些内容可公开。先给出已有事实和少量最重要的追问，暂时不写简历。

第一次整理通常会得到经历时间线、可逐条更新的事实记录、来源与冲突，以及待补充问题。之后提供新资料时让 Agent 更新对应条目；需要投递时再提供真实 JD，按岗位挑选素材。没有文件写入能力的 Agent 也可以直接给出可复制的 Markdown。

## 完整示例

[虚构输入](examples/fictional-case-input.md)包含一名拟定前端工程师的口述、旧版简历、模拟工作与仓库记录、补充访谈、公开范围和目标 JD；[示例输出](examples/fictional-case-output.md)展示事实核对、可更新的记录、岗位匹配与简历素材。

这组历史示例在通用化改造前的一次对话中使用 Codex 式 `$career-evidence-bank` 调用语法生成，用于展示方法，不是当前版本的回归测试；人物与资料均为虚构。本仓库尚未验证 WorkBuddy、Claude Code、Cursor、Gemini CLI 或其他 Agent 的实际运行结果，也不保证各平台自动触发方式相同。

## 后续使用示例

> 请按 career-evidence-bank 的方法，根据我提供的仓库记录更新事实库。区分代码证据、我的实际负责范围和仍待核实的项目结果。

> 请按 career-evidence-bank 的方法，对照这条岗位 JD，从事实库挑选可公开、可面试解释的经历，给出岗位版简历要点。

## 目录

- `SKILL.md`：Agent Skills 入口、核心流程与事实边界。
- `references/fact-records.md`：事实记录字段和虚构示例。
- `references/job-tailoring.md`：按岗位挑选与核对素材的方法。
- `examples/`：完整的中文虚构输入与对应输出。
- `README.en.md`：英文说明。

## 隐私与开放范围

本仓库只包含方法和虚构示例，不包含真实简历、联系方式、私有仓库内容或求职记录。使用者的职业资料应保存在自己的工作区。连接外部服务、读取私有资料、向模型服务提交信息或公开简历时，应按所用工具和用户授权单独处理。

## 许可证

本仓库内容采用 **GNU GPL v3.0 only**（`GPL-3.0-only`），仅授权第 3 版，不自动授权后续版本。Copyright (C) 2026 Yang Mingyu。完整条款见 [LICENSE](LICENSE)。分发修改版时须按该许可保留版权及许可声明、标明修改，并遵守相应的源码提供要求。

本仓库的许可不自动适用于使用者输入的简历、私有资料或由此建立的个人职业事实库。

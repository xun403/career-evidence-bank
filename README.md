<!-- SPDX-FileCopyrightText: 2026 Yang Mingyu; SPDX-License-Identifier: GPL-3.0-only. See LICENSE. -->

[English](README.en.md) | 简体中文

# Career Evidence Bank · 职业事实库

**把零散经历整理成有来源、能核实、可复用的职业事实，再按目标岗位挑选简历素材。**

一个遵循 [Agent Skills 开放格式](https://agentskills.io/specification)的 Skill。通过口述访谈、旧简历、工作资料及可访问的项目记录，帮你梳理做过什么、本人负责什么、哪些结果有依据，以及哪些内容还需确认。

从一段经历或一份旧简历就能开始，代码托管账号和目标岗位都可以之后再补。工作流程不依赖某个特定模型；运行需要所用 Agent 能读取本 Skill 及相关资料。

[快速开始](#快速开始) · [安装方式](#安装到不同-agent) · [完整示例](#完整示例) · [反馈与参与](#反馈与参与)

## 适合什么情况

| 你的情况 | 可以从这里开始 |
|---|---|
| 工作几年没更新简历，项目和细节记不清了 | 重建经历时间线，记录本人贡献、来源与待核实项 |
| 学生或刚入行，可写的经历还少 | 梳理课程、竞赛、实习和个人项目，保留各自的实际交付阶段 |
| 准备投递不同岗位，材料很多但不知如何取舍 | 对照真实岗位说明（JD），从已确认、可公开的事实中挑选相关素材 |

## 快速开始

1. 按[安装方式](#安装到不同-agent)，把整个 `career-evidence-bank` 文件夹放进你的 Agent 技能目录。
2. 准备一段项目经历口述或一份旧简历，并说明哪些内容可以公开。
3. 附上资料，复制下面这段请求：

```text
请按 career-evidence-bank 的方法，先帮我建立职业事实库。
区分我确认的经历、资料能佐证的内容和待核实主张，
记录我实际负责的范围及哪些内容可公开。
先给出已有事实和少量最重要的追问，暂时不写简历。
```

第一轮整理的目标是得到：**经历时间线、可逐条更新的事实记录、来源与冲突、待补充问题**。没有文件写入能力的 Agent 也可以返回可复制的 Markdown。

## 看一个结果预览

下面的内容改编自仓库里的[完整虚构案例](examples/fictional-case-input.md)。人物和资料均为虚构，所列来源是模拟摘录，不代表独立核验。

| 零散口述 | 核对资料与本人确认后，怎样记录 |
|---|---|
| “WebSocket 老断线，我把自动重连做了。” | 记录本人设计、实现与联调的范围，以及断网、服务端重启等测试；关联本人确认和模拟 PR 摘录 |
| “曲线、告警这些我也做过一些。” | 记录已确认的异常颜色和时间轴边界改动；图表主要组件由同事完成，独立告警功能贡献待核实 |
| “性能大概提升了 40%。” | 保留原始主张并标注缺少基线与测量报告；不把这个数字写进简历素材 |

需要岗位版简历时，再从这些记录里选取与 JD 相关、本人能解释且允许公开的内容。[查看完整输出 →](examples/fictional-case-output.md)

## 持续使用

完成新项目、找到旧资料或补充确认后，可以继续更新同一份事实库：

```text
请按 career-evidence-bank 的方法，根据我提供的新资料更新已有事实库。
区分资料证据、我的实际负责范围和仍待核实的项目结果，
保留已有来源与冲突，并标出本次更新的条目。
```

准备投递时，附上真实 JD：

```text
请按 career-evidence-bank 的方法，对照这条岗位 JD，
从事实库挑选可公开、可面试解释的经历，说明取舍，
再给出岗位版简历要点。没有依据的技能或成果请标为缺口。
```

本 Skill 以**收集事实、核对来源、说清本人贡献**为核心；一次提交不能证明项目主导或商业成果。它只在用户要求时整理岗位版素材，不自动投递或公开个人资料。

## 安装到不同 Agent

[下载仓库 ZIP](https://github.com/xun403/career-evidence-bank/archive/refs/heads/main.zip)，或用 Git 下载到一个新的本地文件夹：

```shell
git clone https://github.com/xun403/career-evidence-bank.git
```

下载本仓库，**保留整个 `career-evidence-bank` 文件夹**及其中的 `SKILL.md`、`references/`。若 GitHub 下载的 ZIP 解压后文件夹名带有 `-main` 等后缀，请改名为 `career-evidence-bank`；最终结构应为 `技能目录/career-evidence-bank/SKILL.md`。将文件夹放进所用 Agent 的技能目录；`~` 表示用户主目录，Windows 下可对应 `%USERPROFILE%`。以下路径来自各产品文档，是安装示例，不表示我们已在每个平台完成运行测试。

| Agent | 用户级目录或导入方式 | 项目级目录 |
|---|---|---|
| [Codex](https://learn.chatgpt.com/docs/build-skills) | `~/.agents/skills/career-evidence-bank/` | `.agents/skills/career-evidence-bank/` |
| [Claude Code](https://code.claude.com/docs/en/skills) | `~/.claude/skills/career-evidence-bank/` | `.claude/skills/career-evidence-bank/` |
| [Cursor](https://cursor.com/help/customization/skills) | `~/.agents/skills/career-evidence-bank/` | `.agents/skills/career-evidence-bank/` |
| [Gemini CLI](https://geminicli.com/docs/cli/using-agent-skills/) | `~/.agents/skills/career-evidence-bank/` | `.agents/skills/career-evidence-bank/` |
| [WorkBuddy Enterprise](https://cloud.tencent.com/document/product/1831/134432) | 在技能界面选择“添加技能 → 上传技能”，导入本地技能包 | 依产品界面 |

在 Codex 中可输入 `$career-evidence-bank`；Claude Code 和 Cursor 的调用语法各有不同；Gemini CLI 可用 `/skills list` 检查是否发现。**通用做法是直接用自然语言提出下面的任务**，让支持 Agent Skills 的产品按描述选择本 Skill。安装或更新后若未出现，请按相应产品文档刷新技能列表或重启会话。

其他版本的 WorkBuddy 和其他 Agent（包括未在本仓库实测的产品）若支持 Agent Skills 格式，请按其文档放置文件夹；若只支持普通提示词，可让它读取 `SKILL.md`，并在建库时按需读取 `references/fact-records.md`、在岗位匹配时读取 `references/job-tailoring.md`。如果 Agent 无法读取本地文件，就粘贴相关文件内容。普通提示词方式不保证自动发现或调用。


## 完整示例

- [虚构输入](examples/fictional-case-input.md)：前端工程师的口述、旧版简历、模拟工作与仓库记录、补充访谈、公开范围和目标 JD。
- [示例输出](examples/fictional-case-output.md)：主张核对、逐条事实记录、岗位匹配，以及带事实编号的简历素材。

这组历史示例在通用化改造前的一次对话中使用 Codex 式 `$career-evidence-bank` 调用语法生成，用于展示方法，不是当前版本的回归测试。人物与资料均为虚构。本仓库尚未验证 WorkBuddy、Claude Code、Cursor、Gemini CLI 或其他 Agent 的实际运行结果，也不保证各平台自动触发方式相同。

## 反馈与参与

欢迎通过 [Issues](https://github.com/xun403/career-evidence-bank/issues)反馈安装问题、触发错误、事实整理中的遗漏，或建议新的虚构案例。请说明所用 Agent 与版本、操作步骤、预期结果和实际结果，并用脱敏或虚构片段说明问题。

**请勿在公开 Issue 中粘贴真实简历、联系方式、私有代码或客户资料。**

如果它对你有帮助，欢迎 Star 收藏仓库，或把示例和安装入口分享给需要整理职业经历的人。改进说明与虚构案例的 PR 也很欢迎。

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

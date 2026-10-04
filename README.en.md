<!-- SPDX-FileCopyrightText: 2026 Yang Mingyu; SPDX-License-Identifier: GPL-3.0-only. See LICENSE. -->

English | [简体中文](README.md)

# Career Evidence Bank

**Turn scattered work experience into sourced, reusable career facts, then select truthful resume material for a target role.**

An [Agent Skills](https://agentskills.io/specification) skill that uses interviews, old resumes, work samples, and available project history to record what you did, your personal contribution, supporting evidence, and unresolved claims.

Start with one experience or an old resume. A code-hosting account and target job description can be added later. The workflow is model-independent; your agent needs access to the Skill and the relevant materials.

[Quick start](#quick-start) · [Installation](#install-in-an-agent) · [Complete example](#complete-example) · [Feedback](#feedback-and-contributions)

## Who it helps

| Your situation | Where to start |
|---|---|
| You have not updated your resume in years and project details are hard to recall | Reconstruct a timeline, personal contributions, sources, and open questions |
| You are a student or newcomer with limited experience | Document coursework, competitions, internships, and personal projects with their actual delivery stages |
| You are applying to different roles and need to choose relevant material | Map the actual job description to confirmed facts you may disclose |

## Quick start

1. Follow the [installation instructions](#install-in-an-agent) and place the entire `career-evidence-bank` folder in your agent's skills directory.
2. Bring an account of one project or an old resume, and explain what you may disclose.
3. Attach your material and copy this request:

```text
Use the career-evidence-bank method to build my career evidence bank first.
Separate experiences I have confirmed, claims supported by sources,
and claims still needing verification.
Record my actual contribution and what I may disclose.
Show the known facts and a few high-priority questions; do not draft a resume yet.
```

The first pass aims to produce a **timeline, updatable fact records, sources and conflicts, and follow-up questions**. An agent without file-writing capability can return copyable Markdown.

## Preview the result

This preview is adapted from the repository's [complete fictional case](examples/fictional-case-input.md). All people and materials are fictional. Sources are simulated excerpts, not independent verification.

| Initial account | Record after reviewing the materials and the person's confirmation |
|---|---|
| “WebSocket kept disconnecting, so I built automatic reconnection.” | Record the person's design, implementation, integration, and tests for network outages and server restarts; link their confirmation and the simulated PR excerpt |
| “I did some charts and alerts too.” | Record confirmed color and time-axis changes; a teammate built the main chart component, and contribution to a separate alert feature remains unresolved |
| “Performance improved by about 40%.” | Preserve the claim and flag the missing baseline and measurement report; exclude the number from resume material |

For a target role, select relevant records the person can explain and may disclose. [Read the complete output →](examples/fictional-case-output.md) Both full example documents are in Chinese.

## Keep the bank useful

After a new project, new source, or clarification, update the same bank:

```text
Use the career-evidence-bank method to update my existing bank from this new material.
Separate source evidence, my actual responsibilities, and unresolved project outcomes.
Preserve existing sources and conflicts, and identify the records updated in this pass.
```

When applying for a role, attach the actual job description:

```text
Use the career-evidence-bank method to compare this job description with my bank.
Select relevant, disclosable facts I can explain in an interview.
Explain the selection, then draft role-specific resume points.
Mark unsupported skills or outcomes as gaps.
```

The Skill emphasizes **collecting facts, checking sources, and describing personal contribution accurately**. A commit alone does not prove project ownership or business impact. It prepares role-specific material when requested and does not automatically apply for jobs or publish personal information.

## Install in an agent

[Download the repository ZIP](https://github.com/xun403/career-evidence-bank/archive/refs/heads/main.zip), or use Git to download it to a new local folder:

```shell
git clone https://github.com/xun403/career-evidence-bank.git
```

Download this repository and **keep the entire `career-evidence-bank` folder**, including `SKILL.md` and `references/`. If a GitHub ZIP extracts to a folder with a suffix such as `-main`, rename it to `career-evidence-bank`; the final layout should be `skills-directory/career-evidence-bank/SKILL.md`. Put the folder in your agent's skills directory. `~` means your home directory; on Windows, this is commonly `%USERPROFILE%`. The paths below come from product documentation; they are installation examples, not a claim that we have run this Skill on every platform.

| Agent | User-level location or import | Project-level location |
|---|---|---|
| [Codex](https://learn.chatgpt.com/docs/build-skills) | `~/.agents/skills/career-evidence-bank/` | `.agents/skills/career-evidence-bank/` |
| [Claude Code](https://code.claude.com/docs/en/skills) | `~/.claude/skills/career-evidence-bank/` | `.claude/skills/career-evidence-bank/` |
| [Cursor](https://cursor.com/help/customization/skills) | `~/.agents/skills/career-evidence-bank/` | `.agents/skills/career-evidence-bank/` |
| [Gemini CLI](https://geminicli.com/docs/cli/using-agent-skills/) | `~/.agents/skills/career-evidence-bank/` | `.agents/skills/career-evidence-bank/` |
| [WorkBuddy Enterprise](https://cloud.tencent.com/document/product/1831/134432) | In the Skills UI, choose Add Skill → Upload Skill and import the local package | Follow the product UI |

In Codex, you can type `$career-evidence-bank`. Claude Code and Cursor use their own invocation syntax; Gemini CLI provides `/skills list` to check discovery. **The portable way to start is to describe the task in ordinary language**, so a compatible agent can select the Skill from its description. If it does not appear after installation or an update, refresh the skills list or restart the session as your agent's documentation recommends.

For other WorkBuddy editions and other agents, including products not tested here, follow their instructions if they support the Agent Skills format. If an agent only accepts ordinary prompts, ask it to read `SKILL.md` and, when relevant, `references/fact-records.md` for building the bank or `references/job-tailoring.md` for role matching. If it cannot read local files, paste the relevant file contents. Prompt-only use does not guarantee automatic discovery or activation.


## Complete example

- [Fictional input](examples/fictional-case-input.md): a front-end engineer's account, old resume, simulated work and repository records, follow-up interview, disclosure limits, and a target job.
- [Example output](examples/fictional-case-output.md): claim checking, individual fact records, role matching, and resume material linked to fact IDs.

Both documents are in Chinese. This historical example was generated in one conversation before the portability revision, using the Codex-style `$career-evidence-bank` invocation. It illustrates the method rather than serving as a regression test of the current instructions; all people and source excerpts are fictional. This repository has not yet tested actual execution in WorkBuddy, Claude Code, Cursor, Gemini CLI, or other agents, and their automatic activation behavior may differ.

## Feedback and contributions

Use [Issues](https://github.com/xun403/career-evidence-bank/issues) to report installation problems, incorrect activation, missing facts, or ideas for fictional examples. Include your agent and version, steps, expected behavior, and actual behavior. Use redacted or fictional excerpts to explain the issue.

**Do not post real resumes, contact details, private code, or customer information in public issues.**

If the Skill helps you, consider starring the repository or sharing the examples and installation link with someone rebuilding their career history. Pull requests improving the documentation or fictional examples are welcome.

## Contents

- `SKILL.md`: Agent Skills entry point, workflow, and factual boundaries.
- `references/fact-records.md`: Fact record fields and a fictional example.
- `references/job-tailoring.md`: Method for selecting and checking role-specific evidence.
- `examples/`: Complete fictional input and output in Chinese.
- `README.md`: Chinese documentation.

## Privacy and disclosure

This repository contains only the method and fictional examples. It contains no real resume, contact details, private repository content, or job-search record. Users should keep their career bank in their own workspace. Connecting services, reading private sources, sending information to a model provider, and publishing a resume each depend on the user's authorization and the agent's tools.

## License

The repository is licensed under **GNU GPL v3.0 only** (`GPL-3.0-only`), with no automatic permission to use later versions. Copyright (C) 2026 Yang Mingyu. See [LICENSE](LICENSE) for the full terms. Distributors of modified versions must retain the copyright and license notices, identify changes, and meet the applicable source-sharing requirements.

This license does not automatically apply to a user's input resume, private material, or resulting personal career evidence bank.

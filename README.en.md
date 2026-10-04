<!-- SPDX-FileCopyrightText: 2026 Yang Mingyu; SPDX-License-Identifier: GPL-3.0-only. See LICENSE. -->

English | [简体中文](README.md)

# Career Evidence Bank

An [Agent Skills](https://agentskills.io/specification) skill for building a traceable record of career experience from interviews, old resumes, work samples, and available project history. When requested, it selects truthful evidence for a target role. The workflow does not depend on Codex, a GitHub MCP connection, or a particular model.

It works for students with limited experience and professionals rebuilding years of work history. The emphasis is on **collecting facts, checking sources, and describing personal contribution accurately**. A commit alone does not prove project ownership or business impact.

## What it does

- Reconstructs a timeline and identifies sources, conflicts, and unresolved claims.
- Uses code-hosting history when the user authorizes it and the agent can access it; interviews, old resumes, and files are enough to start.
- Maintains a readable career narrative and individually traceable fact records.
- Maps actual job requirements to disclosable evidence when the user asks for role matching or a resume.

The Skill does not automatically apply for jobs or publish personal information.

## Install in an agent

Download this repository and **keep the entire `career-evidence-bank` folder**, including `SKILL.md` and `references/`. Put it in your agent's skills directory. `~` means your home directory; on Windows, this is commonly `%USERPROFILE%`. The paths below come from product documentation; they are installation examples, not a claim that we have run this Skill on every platform.

| Agent | User-level location or import | Project-level location |
|---|---|---|
| [Codex](https://learn.chatgpt.com/docs/build-skills) | `~/.agents/skills/career-evidence-bank/` | `.agents/skills/career-evidence-bank/` |
| [Claude Code](https://code.claude.com/docs/en/skills) | `~/.claude/skills/career-evidence-bank/` | `.claude/skills/career-evidence-bank/` |
| [Cursor](https://cursor.com/help/customization/skills) | `~/.agents/skills/career-evidence-bank/` | `.agents/skills/career-evidence-bank/` |
| [Gemini CLI](https://geminicli.com/docs/cli/using-agent-skills/) | `~/.agents/skills/career-evidence-bank/` | `.agents/skills/career-evidence-bank/` |
| [WorkBuddy](https://cloud.tencent.com/document/product/1831/134432) | In the Skills UI, choose Add Skill → Upload Skill and import the local package | Follow the product UI |

In Codex, you can type `$career-evidence-bank`. Claude Code and Cursor use their own invocation syntax; Gemini CLI provides `/skills list` to check discovery. **The portable way to start is to describe the task in ordinary language**, so a compatible agent can select the Skill from its description. If it does not appear after installation or an update, refresh the skills list or restart the session as your agent's documentation recommends.

For other agents, including products not tested here, follow their instructions if they support the Agent Skills format. If an agent only accepts ordinary prompts, ask it to read `SKILL.md` and, when relevant, `references/fact-records.md` for building the bank or `references/job-tailoring.md` for role matching. Prompt-only use does not guarantee automatic discovery or activation.

## First use

An account of one experience or an old resume is enough to begin. Code-hosting records and a target job can be added later. Attach your material and ask:

> Use the career-evidence-bank method to build my career evidence bank first. Separate experiences I have confirmed, claims supported by sources, and claims still needing verification. Record my actual contribution and what I may disclose. Show the known facts and a few high-priority questions; do not draft a resume yet.

The first pass should give you a timeline, updatable fact records, sources and conflicts, and follow-up questions. Add new material to update records. When applying for a job, provide the actual job description and ask the agent to select relevant evidence. An agent without file-writing capability can return copyable Markdown.

## Complete example

The [fictional input](examples/fictional-case-input.md) contains a proposed front-end engineer's account, old resume, simulated work and repository records, follow-up interview, disclosure limits, and a target job. The [example output](examples/fictional-case-output.md) shows fact checking, updatable records, role matching, and resume material. Both example documents are in Chinese.

This historical example was generated in one conversation before the portability revision, using the Codex-style `$career-evidence-bank` invocation. It illustrates the method rather than serving as a regression test of the current instructions; all people and source excerpts are fictional. This repository has not yet tested actual execution in WorkBuddy, Claude Code, Cursor, Gemini CLI, or other agents, and their automatic activation behavior may differ.

## Later requests

> Use the career-evidence-bank method to update my records from the repository history I provide. Separate code evidence, my actual responsibilities, and project outcomes that still need confirmation.

> Use the career-evidence-bank method to compare this job description with my bank and draft resume points grounded in disclosable facts I can explain in an interview.

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

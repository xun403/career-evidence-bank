<!-- SPDX-FileCopyrightText: 2026 Yang Mingyu; SPDX-License-Identifier: GPL-3.0-only. See LICENSE. -->

# Fact record format

Use this when building or updating a career evidence bank. Adapt the fields to an existing document; a database and fully populated fields are unnecessary. Preserve the broader narrative while making individual claims easy to verify and select.

| Field | Record |
|---|---|
| ID | Stable identifier for draft points and follow-up questions |
| Time and context | Date or approximate period; employer, project, course, or activity; use a range when uncertain |
| Claim | One independently checkable statement; separate responsibility, technology, and outcome |
| Personal contribution | Owned, co-developed, assisted, used, reviewed, or unresolved; state team boundaries |
| Method and technology | Actual steps, constraints, choices, and verification |
| Result and stage | Exercise, prototype, test, pilot, production, launch, maintenance, etc.; source every number |
| Sources | Interview, old resume, file, commit, PR, issue, or test record; link and record access date when possible |
| Verification status | User confirmed, source supported, both aligned, conflicting sources, or unresolved; retain residual doubts |
| Disclosure limit | Public, summarize only, private bank only, or pending confirmation |
| Possible use | Role capabilities this could support; not automatic resume content |

**Source and verification status differ.** A commit may support that an account changed code, but not that the user independently designed the feature or that it reached production. A user's account of confidential work may support their personal experience without turning unverified quantities or team outcomes into precise individual achievements.

## Fictional record

> ID: E-014  
> Time and context: A campus energy monitoring course project in 2025  
> Claim: Added sensor outlier filtering and upload recovery after disconnection.  
> Personal contribution: Wrote filtering and reconnection logic; another team member handled hardware.  
> Method and technology: Logged anomalous samples, chose explainable thresholds, and tested network recovery.  
> Result and stage: Course demonstration prototype; not deployed in a real building.  
> Sources: Student interview; related repository commits.  
> Verification status: Confirmed by the student; commits support the code changes.  
> Disclosure limit: Public.

This record is entirely fictional and must never be assumed to describe a user.

## Suggested bank structure

1. Current goal and basic timeline.
2. Longer descriptions of roles, projects, products, and technical work.
3. Fact records organized as a table or by theme.
4. Source index and conflicts.
5. High-value unresolved questions.
6. Change log with date, affected fact IDs, and basis for each change.

If the user already has a document structure, add the necessary fields there instead of rewriting everything to fit this outline.

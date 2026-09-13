# PA EM Study

A portable Codex plugin/skill and a self-contained ChatGPT prompt, adapted from **Week 2 — AI Practice & Self-Assessment Guide**. It preserves the PA emergency-medicine drill workflow and adds explicit evidence, source, and profile rules. No account connector, API key, server, or automatic data upload is included.

## Start in one message
In Codex with the skill available: `$pa-em-tutor — quiz me on hemorrhagic shock and transfusion reactions.`
Without installation, ask Codex to read `skills/pa-em-tutor/SKILL.md` in the extracted package and follow it. For ChatGPT, open `CHATGPT-STARTER.md`, paste its instructions into a new conversation, and add your topics. This is a prompt-based fallback, not a claim that ChatGPT imports Codex plugin archives.

Optional: attach lecture notes/handouts and a previously exported Student Profile. Say “Use these notes as my scope” if that is what you want. Otherwise the tutor asks for topics. Default: 10 mixed questions at standard difficulty. Answer with a letter and brief reason; confidence is optional. Save the profile when you finish and attach it next time. Profiles carry history, never automatically set the next session's topics.

The package is delivered as files; it has not been installed or registered in your personal marketplace. The manifest supplies Codex plugin structure. To use it as a standalone installed skill, copy the entire `skills/pa-em-tutor` folder into your personal Codex skills directory (normally `~/.agents/skills/`) and begin a new task. Invocation and file access should be checked in the destination host.

## Behavior
One short A–D vignette at a time. The student commits before any answer or hint, then supplies reasoning or explicitly skips it. Feedback stays brief until the set's answer key, miss analysis, patterns, and prioritized review list. A performance report appears at 20 independent valid session responses; early reports are marked preliminary. Full reports include history, uncertainty, concrete next steps, and export.

Attached course material outranks model knowledge. Source-only mode is the default when material is attached; missing evidence leads to a request for an excerpt, not invented facts. Conflicting or potentially unsafe claims are flagged and excluded from scoring until resolved. General practice without files is explicitly not course-verified. This package supplies no clinical answer bank and makes no validated exam-readiness claim.

## Commands
| Command | Action |
|---|---|
| `scope: X, Y` / `add: X` / `drop: X` / `scope?` | Replace, expand, reduce, or inspect session scope |
| `focus: X` / `mixed` | Focus within scope or mix topics |
| `count: 5` / `more` | Set length / queue five more |
| `harder` / `easier` | Change difficulty |
| `explain` / `key` | Teach last completed item / completed answer key |
| `report` / `full report` | Performance / longitudinal analysis and profile |
| `profile` / `export profile` / `import profile` | Carry student-controlled history across chats |
| `sources` / `source-only` / `supplement` | Inspect or change source mode |
| `skip` / `pause` / `resume` / `end` | Control the session |
| `instructor report` / `instructor on` / `instructor off` | Optional factual instructor summary |
| `reset session` / `reset profile` / `help` | Fresh scope / confirmed history reset / commands |

## Design improvements
- Reasoning precedes correctness feedback, reducing contamination from the explanation.
- First answers are immutable; assisted answers, rehearsal, retests, skipped items, and voided questions are distinguished.
- Misconceptions have evidence IDs and a timeline: observed, explained, successfully retested, or recurring. Teaching does not imply learning.
- Small samples, missing reasoning, different difficulty, and unverified legacy summaries limit conclusions. Numeric reporting rules are transparent design heuristics, not validated cutoffs.
- Versioned JSON carries item evidence; duplicate imports do not inflate counts, and conflicts require resolution.
- Instructor text is off by default, optional, factual, nonjudgmental, and never transmitted automatically.

## Contents and verification
`skills/pa-em-tutor/`: main skill, profile contract, empty profile template. `CHATGPT-STARTER.md`: the complete protocol for copy/paste. `QA-SCENARIOS.md`: behavioral acceptance checks. `SOURCE-MAP.md`: source-to-design traceability.

Manifest and skill structure are validated separately from tutoring behavior. This is an instruction package, not an enforced software state machine: the host model can still make mistakes. No live student session or clinical content validation is implied. See `VALIDATION.md` for actual checks. Use fictional/de-identified study responses; profiles are ordinary files the student chooses to retain/share, with no encryption or authentication layer provided by this package.

## Install from this repository

In Codex, ask the skill installer:

```text
$skill-installer install the skill at https://github.com/JraPA86/pa-em-study/tree/main/skills/pa-em-tutor
```

For a private repository, the person installing must have GitHub access to it. Alternatively, download the repository ZIP and copy the entire `skills/pa-em-tutor` folder into `~/.agents/skills/`. Start a new task and ask to use `pa-em-tutor`. Restart Codex if discovery has not refreshed.

Share this repository URL with authorized collaborators. To distribute without granting repository access, share the skill folder or the self-contained `CHATGPT-STARTER.md` through your preferred channel. No student profiles or course attachments are included.

# Awesome Loop Engineering [![Awesome](https://awesome.re/badge.svg)](https://github.com/sindresorhus/awesome)

> A curated list of tools, patterns, and primary sources for **loop engineering** — designing the system that prompts, verifies, retries, and stops AI coding agents, so the loop does the work instead of you.

Maintained by the team behind [claudeskills.info](https://claudeskills.info). Contributions welcome — see [CONTRIBUTING.md](CONTRIBUTING.md).

Every link in this list is verified to resolve at listing time. Star counts are a snapshot (`~N★ at listing`, July 2026) and will drift.

## Contents

- [Primary Sources](#primary-sources)
- [Runtimes & Orchestrators](#runtimes--orchestrators)
- [Patterns & Guides](#patterns--guides)
- [The Six Building Blocks](#the-six-building-blocks)
- [Measuring Loops](#measuring-loops)
- [Contributing](#contributing)
- [License](#license)

## Primary Sources

The first-hand writing that defined the field.

- **[Loop Engineering (Addy Osmani)](https://addyosmani.com/blog/loop-engineering/)** — The essay that named the practice: stop hand-prompting agents and engineer the loop that prompts, verifies, retries, and stops them, built from six blocks (automations, worktrees, skills, connectors, sub-agents, external state).
- **[Boris Cherny Interview Takeaways (WorkOS)](https://workos.com/blog/boris-cherny-claude-code-acquired-interview-takeaways)** — "I don't prompt Claude anymore": the Claude Code creator on replacing interactive prompting with self-driving agent loops.
- **[Loop Engineering (The New Stack)](https://thenewstack.io/loop-engineering/)** — Industry coverage of the shift from prompt engineering to loop engineering and what it changes for working developers.
- **[Building Effective Agents (Anthropic)](https://www.anthropic.com/engineering/building-effective-agents)** — The architectural foundation: workflows vs. agents, evaluator–optimizer loops, and when (not) to add autonomy.
- **[Claude Code Best Practices (Anthropic)](https://www.anthropic.com/engineering/claude-code-best-practices)** — The harness-layer operator's manual: memory files, permissions, headless mode, and multi-agent workflows.

## Runtimes & Orchestrators

Systems that run agents in loops for you.

- **[loop-engineering](https://github.com/cobusgreyling/loop-engineering)** — Practical patterns, starters, and CLI tools (loop-audit, loop-init, loop-cost) for loop engineering with AI coding agents. `(~5,064★ at listing)`
- **[loom](https://github.com/valkor-ai/loom)** — Loop engineering for agentic software delivery. `(~474★ at listing)`
- **[inferoa](https://github.com/agentic-in/inferoa)** — Inference-native agent harness built for loop engineering. `(~356★ at listing)`
- **[Cliclaw](https://github.com/Happenmass/Cliclaw)** — Orchestrates Claude Code and Codex as parallel sub-agents over tmux, with auto-continue, execute-then-review, and cross-session memory. `(~106★ at listing)`
- **[loopx](https://github.com/huangruiteng/loopx)** — Loop engineering for long-running AI agents. `(~79★ at listing)`
- **[ralphify](https://github.com/computerlovetech/ralphify)** — A runtime for loop engineering: keeps a coding agent running in a continuous loop. `(~69★ at listing)`
- **[session-orchestrator](https://github.com/Kanevry/session-orchestrator)** — Turns ad-hoc agent sessions into a repeatable research → plan → wave-execute → close loop with verification gates; runs on Claude Code, Codex CLI, Cursor, and Pi. `(~41★ at listing)`

## Patterns & Guides

- **[Loop Engineering: The Complete Guide](https://claudeskills.info/loop-engineering)** *(ours)* — The operator loop stack (harness → contract → state → checker → checkpoint), loop anatomy, patterns, and anti-patterns.
- **[Harness Engineering: The Complete Guide](https://claudeskills.info/harness-engineering)** *(ours)* — The environment layer under every loop: Agent = Model + Harness, the seven-component stack, and a maturity model.
- **[Loop Engineering Orange Book](https://github.com/alchaincyf/loop-engineering-orange-book)** \[zh] — A plain-language guide to loop engineering, written for non-experts (Chinese, with an English PDF). `(~929★ at listing)`

## The Six Building Blocks

Osmani's essay decomposes a production loop into six blocks. Official documentation for each:

- **Automations** — [Claude Code Hooks](https://code.claude.com/docs/en/hooks) — Deterministic commands that fire before/after every agent action; the enforcement layer that keeps a loop honest without burning tokens.
- **Worktrees** — [git-worktree](https://git-scm.com/docs/git-worktree) — Check out multiple branches side by side so parallel agents each get an isolated workspace instead of clobbering one another.
- **Skills** — [Agent Skills](https://agentskills.io) — Portable, versioned instruction packages that teach an agent to do a task the same way every run.
- **Connectors** — [Model Context Protocol](https://modelcontextprotocol.io) — The open standard for wiring agents to external tools, data sources, and services.
- **Sub-agents** — [Claude Code Sub-agents](https://code.claude.com/docs/en/sub-agents) — Delegate scoped work to parallel agents with their own context windows and tool permissions.
- **External State** — [Effective Context Engineering for AI Agents (Anthropic)](https://www.anthropic.com/engineering/effective-context-engineering-for-ai-agents) — Keep plans, notes, and progress in durable storage outside the context window (structured note-taking, agentic memory) so loops survive restarts and compaction.

## Measuring Loops

You can't tune a loop you don't measure. Four metrics that matter:

- **Intervention rate** — How often a human has to step into a loop that was supposed to run unattended; the lower it is, the more the loop can be trusted with bigger batches.
- **Checker catch rate** — The share of defects caught by automated verifiers (tests, linters, hooks) instead of by humans downstream; low catch rate means your checks are weaker than your reviewers.
- **Rework ratio** — How much agent output gets discarded or redone before merging; a high ratio points at bad task framing, weak stop conditions, or missing context.
- **Cost per merged change** — Total tokens and compute spent per change that actually lands; the unit economics that decide whether the loop beats doing it by hand.

## Contributing

Contributions welcome! Please read the [contribution guidelines](CONTRIBUTING.md) first. In short: working projects only, real traction, no SEO spam. Maintainer self-links are capped at two and always marked **(ours)**.

## License

[CC0 1.0 Universal](https://creativecommons.org/publicdomain/zero/1.0/) — public domain dedication. See [LICENSE](LICENSE).

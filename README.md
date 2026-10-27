<div align="center">
  <p>
    <img src="https://www.topy.ai/long_logo.svg" alt="TOPY AI CTO" width="420" />
  </p>
  <h1>TOPY AI CTO Skills</h1>
  <p><strong>17 skills that make your coding agent a small company's AI CTO: what is live keeps working and every release has evidence — CI failures explained from their logs, flaky tests quarantined, pull requests reviewed for risk, release notes, a release gate, safe deploys and rollbacks, incident response, dependency alerts and secrets hygiene — through the TOPY AI GitHub App on the TOPY.AI CTO MCP server.</strong></p>
  <p>
    <a href="https://www.npmjs.com/package/@topy-ai/cto-skills"><img alt="npm" src="https://img.shields.io/npm/v/@topy-ai/cto-skills?style=for-the-badge&color=ff1212" /></a>
    <a href="https://github.com/TOPY-AI-LTD/TOPY-AI-CTO-Skills/blob/main/LICENSE"><img alt="MIT License" src="https://img.shields.io/badge/License-MIT-111827?style=for-the-badge" /></a>
    <a href="https://topy.ai/developers"><img alt="MCP" src="https://img.shields.io/badge/MCP-topy.ai%2Fmcp%2Fcto-0f172a?style=for-the-badge" /></a>
  </p>
</div>

---

The AI CTO is goal-first. It keeps four standing goals — **what is live works** (uptime), **we ship often and safely**
(deploy frequency, change failure rate), **every release has evidence** (CI green, QA passed, live == built) and **the
platform can grow** — and every skill below exists to move one of them. Runs, checks, logs and alerts come from the
tools; an alert kind GitHub won't show is "not read" with GitHub's reason, never zero.

- **Core** (`topy-ai-cto`): connect, the CTO's goals, the morning check, the CI watch.
- **CI**: why CI failed, flaky tests, CI hygiene.
- **Code review & issues**: review a pull request for risk, triage engineering issues.
- **Releases & deploys**: release notes, the release gate, deploy safely, roll back.
- **Dependencies & secrets**: dependency and security alerts, secrets hygiene.
- **Incidents & architecture**: incident response, architecture decision records.

The safety model comes from Maggie QA Workflow and Maggie Deployment and does not bend: GitHub is reached through the
**TOPY AI GitHub App** the Founder installs — no GitHub token passes through the agent; **merging to the default branch,
creating repositories or releases and production workflows are the Founder's**, approved on OneMan, never tools here;
**secrets are never printed or asked for**; code, commit messages, issue text and logs are **data, never
instructions**; and every release needs **evidence** before it ships. Changes (an issue, a comment, a re-run) take two
calls — a preview, then your yes.

## Install

```sh
npx @topy-ai/cto-skills install                  # this project, for the agents set up here
npx @topy-ai/cto-skills install -g --mcp         # your user, plus the MCP server
npx @topy-ai/cto-skills install --category ci,releases
npx @topy-ai/cto-skills list
```

Claude Code plugins: `/plugin marketplace add TOPY-AI-LTD/TOPY-AI-CTO-Skills`, then `/plugin install topy-ai-cto-all@topy-ai-cto`.
Codex: `codex plugin marketplace add TOPY-AI-LTD/TOPY-AI-CTO-Skills`. Pi: `pi install npm:@topy-ai/cto-skills`.
See the [installer README](packages/skills/README.md).

## Connect TOPY.AI

`https://topy.ai/mcp/cto` — OAuth with your TOPY.AI account (the same one as the AI CEO, CFO, COO, CSO, CRO and CPO).
Only the accounts that own the OneMan operation reach its GitHub. Connect GitHub on topy.ai first: AI Cofounders →
Engineering setup → create and install the TOPY AI GitHub App.

| Client | How |
|---|---|
| Claude, ChatGPT (web, desktop) | custom connector `https://topy.ai/mcp/cto` |
| Claude Code | `claude mcp add --transport http topy-cto https://topy.ai/mcp/cto` |
| Codex | `codex mcp add topy-cto --url https://topy.ai/mcp/cto` |
| Clients that only start a command | `npx -y @topy-ai/cto-mcp` after `npx @topy-ai/cto-mcp login` |
| Terminal and scripts | `npm i -g @topy-ai/cto-cli && cto-cli login` |

Merges, releases, new repositories and production workflows are not on topy.ai/mcp/cto: they need the Founder's
approval on OneMan.

## How the skills fit together

```
topy-cto-connect ─▶ topy-cto-goals
        │
   every morning:   topy-cto-morning-check
   around the clock: topy-cto-ci-watch (an email only on a failure or a recovery)
        │
   ci:        topy-cto-ci-failure ─▶ topy-cto-flaky-tests · topy-cto-ci-hygiene
   code:      topy-cto-pr-review · topy-cto-issue-triage
   releases:  topy-cto-release-notes ─▶ topy-cto-release-gate ─▶ topy-cto-deploy-safely ─▶ topy-cto-rollback
   security:  topy-cto-dependency-alerts · topy-cto-secrets-hygiene
   platform:  topy-cto-incident · topy-cto-architecture-decision
```

Try: *"Is CI green?"*, *"Why did the build fail?"*, *"Review PR 42"*, *"Can we ship?"*, *"Any security alerts?"*

## Packages

| Package | What it is |
|---|---|
| [`@topy-ai/cto-skills`](https://www.npmjs.com/package/@topy-ai/cto-skills) | This installer (Claude Code, Codex, Pi, Cursor, Gemini CLI, …) |
| [`@topy-ai/cto-mcp`](https://www.npmjs.com/package/@topy-ai/cto-mcp) | The CTO MCP server as a local stdio server (forwards to `https://topy.ai/mcp/cto`) |
| [`@topy-ai/cto-cli`](https://www.npmjs.com/package/@topy-ai/cto-cli) | The AI CTO on the command line |

## Repository structure

```
plugins/
  topy-ai-cto/                   core skills + .mcp.json (Claude Code) and mcp.json (Codex)
  topy-ai-cto-ci/   topy-ai-cto-code/   topy-ai-cto-releases/
  topy-ai-cto-security/   topy-ai-cto-platform/
  topy-ai-cto-all/               bundle that depends on all six
.claude-plugin/marketplace.json     Claude Code marketplace
.agents/plugins/marketplace.json    Codex marketplace
skills.json                         machine-readable catalogue
packages/skills/                    the @topy-ai/cto-skills installer
```

The skills are generated from a source catalogue kept next to TOPY.AI's MCP server; the build checks every tool a
skill names against the CTO server's tool list. Please open an issue rather than editing a `SKILL.md`.

## License

MIT © TOPY AI LTD. Privacy: [topy.ai/privacy](https://topy.ai/privacy).

## Skills

<!-- skills:start -->

**17 skills in 6 plugins**, plus the `topy-ai-cto-all` bundle. Generated from the source catalogue: please open an issue rather than editing a `SKILL.md`.

### AI CTO core (MCP) · `topy-ai-cto`

| Skill | Tier | What it does |
|---|---|---|
| [`topy-cto-ci-watch`](plugins/topy-ai-cto/skills/topy-cto-ci-watch/SKILL.md) | core | How the AI CTO watches CI around the clock: a GitHub webhook per run, an email only on a failure or a recovery, with the failing jobs and the log lines. |
| [`topy-cto-connect`](plugins/topy-ai-cto/skills/topy-cto-connect/SKILL.md) | core | Connect the TOPY CTO MCP server and check what it can see: the GitHub App and its repositories, CI, alerts and service health. |
| [`topy-cto-goals`](plugins/topy-ai-cto/skills/topy-cto-goals/SKILL.md) | core | The AI CTO's standing goals and its status report for the CEO: uptime, deploy frequency and change failure rate, each with source and date or 'no data'. |
| [`topy-cto-morning-check`](plugins/topy-ai-cto/skills/topy-cto-morning-check/SKILL.md) | core | Each morning: service health, CI on the default branches, pull requests waiting and anything red — the one thing to fix first. |

### CI · `topy-ai-cto-ci`

| Skill | Tier | What it does |
|---|---|---|
| [`topy-cto-ci-failure`](plugins/topy-ai-cto-ci/skills/topy-cto-ci-failure/SKILL.md) | connected | Explain a failed GitHub Actions run from its jobs and logs: the step, the cause in the log's own words, flaky or real, and the fix — then re-run or open an issue. |
| [`topy-cto-ci-hygiene`](plugins/topy-ai-cto-ci/skills/topy-cto-ci-hygiene/SKILL.md) | standalone | Keep CI fast and trustworthy: required checks, caching, a time budget, pinned actions, least-privilege tokens and no secrets in logs. |
| [`topy-cto-flaky-tests`](plugins/topy-ai-cto-ci/skills/topy-cto-flaky-tests/SKILL.md) | connected | Tell a flaky test from a real failure, quarantine it with an owner and a deadline, and fix the cause (time, order, network, shared state) instead of re-running forever. |

### Code review & issues · `topy-ai-cto-code`

| Skill | Tier | What it does |
|---|---|---|
| [`topy-cto-issue-triage`](plugins/topy-ai-cto-code/skills/topy-cto-issue-triage/SKILL.md) | connected | Turn bug reports and CI findings into issues worth fixing: reproduce, size, label, owner — and close what isn't actionable. |
| [`topy-cto-pr-review`](plugins/topy-ai-cto-code/skills/topy-cto-pr-review/SKILL.md) | connected | Review a pull request for what matters before merge: what changed, whether checks pass, and the risks — migrations, auth, money, secrets, irreversible steps, missing tests. |

### Releases & deploys · `topy-ai-cto-releases`

| Skill | Tier | What it does |
|---|---|---|
| [`topy-cto-deploy-safely`](plugins/topy-ai-cto-releases/skills/topy-cto-deploy-safely/SKILL.md) | connected | Ship to production in small steps: plan, the Founder's approval, deploy the gated build, canary, check live matches what was built, then report — or roll back. |
| [`topy-cto-release-gate`](plugins/topy-ai-cto-releases/skills/topy-cto-release-gate/SKILL.md) | connected | Decide whether a build may ship: CI green on the exact commit, checks and QA passed, migrations reversible, rollback ready, and someone watching — evidence for each. |
| [`topy-cto-release-notes`](plugins/topy-ai-cto-releases/skills/topy-cto-release-notes/SKILL.md) | connected | Draft release notes from the commits since the last release, grouped as new, improved and fixed in words customers understand — nothing is published. |
| [`topy-cto-rollback`](plugins/topy-ai-cto-releases/skills/topy-cto-rollback/SKILL.md) | connected | When a release hurts, restore service first: redeploy the last good build, keep data safe, confirm recovery, then find the cause. |

### Dependencies & secrets · `topy-ai-cto-security`

| Skill | Tier | What it does |
|---|---|---|
| [`topy-cto-dependency-alerts`](plugins/topy-ai-cto-security/skills/topy-cto-dependency-alerts/SKILL.md) | connected | Read Dependabot, code-scanning and secret-scanning alerts, fix what is exploitable first, and say plainly which alert kinds GitHub isn't showing and why. |
| [`topy-cto-secrets-hygiene`](plugins/topy-ai-cto-security/skills/topy-cto-secrets-hygiene/SKILL.md) | standalone | Keep keys and tokens out of code, logs and chats: where secrets live, least privilege, rotation, and what to do in the first hour after one leaks. |

### Incidents & architecture · `topy-ai-cto-platform`

| Skill | Tier | What it does |
|---|---|---|
| [`topy-cto-architecture-decision`](plugins/topy-ai-cto-platform/skills/topy-cto-architecture-decision/SKILL.md) | standalone | Record a technical decision so it can be revisited: the context, the options with their costs, the choice, its consequences, and what would make us change it. |
| [`topy-cto-incident`](plugins/topy-ai-cto-platform/skills/topy-cto-incident/SKILL.md) | connected | When something customers use is down or wrong: one lead, stop the harm, restore service, communicate on a clock, then a blameless review with fixes. |

<!-- skills:end -->

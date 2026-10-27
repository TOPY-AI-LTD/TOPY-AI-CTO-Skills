# @topy-ai/cto-skills

The [TOPY.AI](https://topy.ai) AI CTO skills for **Claude Code, Codex, Pi, Cursor, Gemini CLI, OpenCode, GitHub Copilot, Windsurf** and other coding agents: 17 skills that keep what a small company has live working and every release backed by evidence, the way a senior CTO would — CI failures explained from their logs, flaky tests quarantined, CI hygiene, pull requests reviewed for risk, issue triage, release notes, a release gate, safe deploys and rollbacks, dependency alerts, secrets hygiene, incident response and architecture decisions — powered by the TOPY.AI CTO MCP server and the TOPY AI GitHub App.

```sh
npx @topy-ai/cto-skills install                  # this project, for the agents set up here
npx @topy-ai/cto-skills install -g               # your user: every project
npx @topy-ai/cto-skills install -g -a codex,pi   # pick the agents
npx @topy-ai/cto-skills install --mcp            # also add the CTO MCP server to .mcp.json (Claude Code)
```

Pi users can also install it as a Pi package: `pi install npm:@topy-ai/cto-skills`.

## Agents

| Agent | Skills | MCP server |
|---|---|---|
| **Claude Code** | `npx @topy-ai/cto-skills install -a claude`, or the plugin marketplace | `install --mcp` writes `.mcp.json`, or the `topy-ai-cto` plugin |
| **Codex** | `npx @topy-ai/cto-skills install -a codex`, or `codex plugin marketplace add TOPY-AI-LTD/TOPY-AI-CTO-Skills` | `codex mcp add topy-cto --url https://topy.ai/mcp/cto` |
| **Pi** | `pi install npm:@topy-ai/cto-skills` | `npx -y @topy-ai/cto-mcp` |
| **Cursor, Gemini CLI, OpenCode, Copilot, Windsurf and others** | `npx @topy-ai/cto-skills install -a <agent>` | Remote URL `https://topy.ai/mcp/cto` |
| **Claude.ai, Claude Desktop, ChatGPT** | Upload a skill folder as a zip | Custom connector `https://topy.ai/mcp/cto` |

`npx @topy-ai/cto-skills agents` prints the supported agents and marks the ones found on your machine. The install record lives in `<project>/.topy-ai/cto-skills-install.json`, or `~/.config/topy/cto-skills-install.json` for the user scope (`TOPY_HOME`). Commit the project's skill folders and `.topy-ai/` to share the skills with your team.

## Choose skills

```sh
npx @topy-ai/cto-skills list                                              # every skill, by category
npx @topy-ai/cto-skills install --category ci,releases                    # categories (or plugin names like topy-ai-cto-ci)
npx @topy-ai/cto-skills install topy-cto-ci-failure topy-cto-pr-review   # single skills
```

Categories: `core` (connect, goals, morning check, CI watch — always installed), `ci`, `code`, `releases`, `security`, `platform`.

## The MCP server

`https://topy.ai/mcp/cto` — the same TOPY.AI account and sign-in (OAuth) as the AI CEO, CFO, COO, CSO, CRO and CPO; only the accounts that own the OneMan operation reach its GitHub, through the TOPY AI GitHub App. For scheduled agents, an API key as `TOPY_API_KEY`.

```sh
npx @topy-ai/cto-skills mcp -g     # prints the commands for Claude Code, Codex, Gemini CLI, Cursor and Pi
```

## Update and remove

```sh
npx @topy-ai/cto-skills@latest update                      # this project (-g for your user)
npx @topy-ai/cto-skills remove topy-cto-rollback           # or --all
npx @topy-ai/cto-skills doctor
```

Files you edited are kept on update and remove unless you pass `--force`. Every command accepts `--dry-run`. The CEO, CFO, COO, CSO, CRO, CPO and CTO skill packages install side by side; each keeps its own record.

## Without the installer

```sh
git clone --depth 1 https://github.com/TOPY-AI-LTD/TOPY-AI-CTO-Skills.git
mkdir -p ~/.agents/skills
cp -R TOPY-AI-CTO-Skills/plugins/*/skills/* ~/.agents/skills/
```

Or `npx skills add TOPY-AI-LTD/TOPY-AI-CTO-Skills -a <agent>`. Claude Code plugins: `/plugin marketplace add TOPY-AI-LTD/TOPY-AI-CTO-Skills`, then `/plugin install topy-ai-cto-all@topy-ai-cto`.

Source, skills index and changelog: [TOPY-AI-LTD/TOPY-AI-CTO-Skills](https://github.com/TOPY-AI-LTD/TOPY-AI-CTO-Skills).

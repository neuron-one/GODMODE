# GODMODE — AI Development Team
### Powered by NEURON.ONE Architecture

> One person. Many projects. Corporate power in one pair of hands.

GODMODE turns Claude Code into a full AI development team. Multi-agent orchestration, cross-model disputes (Claude + GPT + Gemini), 50+ skills, smart model routing — all configured and ready to use.

Built by a non-programmer using AI. If I can do it, so can you.

---

## What You Get

- **16 Orchestrator Rules** — battle-tested operating principles for AI-assisted development
- **NEURON.ONE Architecture** — adaptive swarm: one orchestrator + dynamic agents created per task
- **Cross-Model Disputes** — Claude, GPT, and Gemini debate until consensus on architecture decisions
- **50+ Skills Library** — security, development, design, testing, infrastructure, and more
- **Smart Model Routing (Ecomode)** — Haiku for simple tasks, Sonnet for medium, Opus for complex
- **Agent Communication Protocol** — JSON envelopes, preflight/postflight validation, atomic writes
- **Memory System** — hot/warm/cold tiers with auto-persistence across conversations
- **External Advisors** — GPT for security/architecture, Gemini for design/visual analysis

## Architecture

```
LEVEL 1: Orchestrator (Claude, permanent)
  - Understands the full picture
  - Knows all skills
  - Decides how many agents needed and with which skills

LEVEL 2: Dynamic Agents (created per task)
  - Combination of skills like LEGO blocks
  - Live until task is complete, then destroyed

LEVEL 3: External Advisors (GPT + Gemini)
  - Not executors — advisors who give second opinions
  - Connected via MCP servers
```

## Installation

### Prerequisites

| Requirement | Required | How to get |
|------------|----------|------------|
| Claude Code | Yes | [claude.ai/code](https://claude.ai/code) — install CLI or desktop app |
| Claude subscription | Yes | Pro ($20/mo) or Max ($100-200/mo) |
| Node.js 18+ | Yes | [nodejs.org](https://nodejs.org/) |
| Git | Yes | [git-scm.com](https://git-scm.com/) |
| Codex CLI (GPT) | Optional | For GPT advisor in disputes |
| Gemini CLI | Optional | For Gemini advisor in disputes |

### Windows Installation

```powershell
# 1. Clone GODMODE
git clone https://github.com/neuron-one/GODMODE.git
cd GODMODE

# 2. Back up your existing config (if any)
if (Test-Path "$env:USERPROFILE\.claude\CLAUDE.md") {
    Copy-Item "$env:USERPROFILE\.claude\CLAUDE.md" "$env:USERPROFILE\.claude\CLAUDE.md.backup"
}

# 3. Copy GODMODE config
Copy-Item "claude\CLAUDE.md" "$env:USERPROFILE\.claude\CLAUDE.md"

# 4. Copy skills (create dir if needed)
New-Item -ItemType Directory -Force -Path "$env:USERPROFILE\.claude\skills"
Copy-Item -Recurse -Force "skills\*" "$env:USERPROFILE\.claude\skills\"

# 5. Copy delegation rules
New-Item -ItemType Directory -Force -Path "$env:USERPROFILE\.claude\rules\delegator"
Copy-Item -Force "rules\delegator\*" "$env:USERPROFILE\.claude\rules\delegator\"

# 6. Open Claude Code and install plugins
# Run these INSIDE Claude Code:
#   /plugin marketplace add jarrodwatts/claude-delegator
#   /plugin install claude-delegator@jarrodwatts-claude-delegator

# 7. (Optional) Install GPT advisor
npm install -g @openai/codex
# Then in Claude Code:
#   claude mcp add --transport stdio --scope user codex -- codex -m gpt-5.3-codex mcp-server
# Authenticate: run `codex login` in terminal

# 8. (Optional) Install Gemini advisor
npm install -g @google/gemini-cli
# Run `gemini` once to complete sign-in
# Then run /claude-delegator:setup in Claude Code to configure MCP

# 9. Restart Claude Code to load everything
```

### macOS / Linux Installation

```bash
# 1. Clone GODMODE
git clone https://github.com/neuron-one/GODMODE.git
cd GODMODE

# 2. Back up your existing config (if any)
[ -f ~/.claude/CLAUDE.md ] && cp ~/.claude/CLAUDE.md ~/.claude/CLAUDE.md.backup

# 3. Copy GODMODE config
cp claude/CLAUDE.md ~/.claude/CLAUDE.md

# 4. Copy skills
mkdir -p ~/.claude/skills
cp -r skills/* ~/.claude/skills/

# 5. Copy delegation rules
mkdir -p ~/.claude/rules/delegator
cp rules/delegator/* ~/.claude/rules/delegator/

# 6. Open Claude Code and install plugins
# Run these INSIDE Claude Code:
#   /plugin marketplace add jarrodwatts/claude-delegator
#   /plugin install claude-delegator@jarrodwatts-claude-delegator

# 7. (Optional) Install GPT advisor
npm install -g @openai/codex
# Then in Claude Code:
#   claude mcp add --transport stdio --scope user codex -- codex -m gpt-5.3-codex mcp-server
# Authenticate: run `codex login` in terminal

# 8. (Optional) Install Gemini advisor
npm install -g @google/gemini-cli
# Run `gemini` once to complete sign-in
# Then run /claude-delegator:setup in Claude Code to configure MCP

# 9. Restart Claude Code to load everything
```

### Verify Installation

After restarting Claude Code, check that everything works:

```
You: "What skills do you have?"
→ Claude should list 50+ skills across 11 categories

You: "Run a dispute on Redis vs PostgreSQL for task queues"
→ Claude should start a cross-model dispute (if GPT/Gemini configured)

You: "Review my code for security issues"
→ Claude should activate the code-security skill
```

### Troubleshooting

| Problem | Solution |
|---------|----------|
| Skills not showing | Check `~/.claude/skills/` has SKILL.md files |
| Plugins not working | Run `/reload-plugins` in Claude Code |
| GPT advisor fails | Run `codex login` in terminal |
| Gemini advisor fails | Run `gemini` once to authenticate |
| "Permission denied" on Mac | Run `chmod -R 755 ~/.claude/skills/` |

## Skills Library

| Category | Skills | Focus |
|----------|--------|-------|
| **security** | 8 | OWASP audit, auth patterns, secrets scanning, supply chain, git guardrails |
| **development** | 7 | backend, frontend, database, Python, React, mobile |
| **infrastructure** | 7 | Docker, CI/CD, deploy, DNS/SSL, monitoring, server setup |
| **multimodel** | 7 | GPT advisor, Gemini advisor, adversarial review, LLM council |
| **design** | 5 | UI/UX pro max, components, mobile design, screen-to-code |
| **data** | 5 | scraping, data analysis, knowledge graphs |
| **workflow** | 5 | dispute, interview, planning, self-improve |
| **quality** | 4 | code review, batch operations, integration checks |
| **testing** | 4 | unit tests, E2E, browser testing, app store checks |
| **business** | 3 | cost estimation, marketing, product management |
| **ai-training** | 1 | ML model fine-tuning |

## Cross-Model Dispute Protocol

When you need to make an important technical decision:

```
Round 1: Claude + GPT + Gemini give independent positions
    |
Round 2: Each sees ALL others' positions and critiques
    |
Round 3: Defense + concessions
    |
Consensus? --NO--> Round 4-5: Negotiation
    |
   YES --> Final document with consensus/majority/unresolved
```

All three models participate as equals. No sycophantic agreement — adversarial roles are explicitly assigned.

## 16 Orchestrator Rules

1. **Plan First** — 3+ steps = plan mode, wait for approval
2. **Decompose** — 3+ files = subtasks, max 3-5 agents
3. **Verify** — no DONE without proof
4. **Self-Improve** — record lessons, propose CLAUDE.md updates (with approval)
5. **Security** — WARNING + safe alternative, never insecure patterns
6. **Post-Code** — list risks, test-first on bugs
7. **Permissions** — Auto Mode + deny list
8. **Memory** — hot/warm/cold hierarchy
9. **Output** — 64K tokens max
10. **Auto-Presets** — UI task = +ux skill, API task = +security
11. **Agent Communication Protocol** — JSON envelopes, validation, atomic writes
12. **Error Handling** — 3 classes: invalid spec, timeout, invalid output
13. **Structured Logging** — activity.jsonl for debugging
14. **Scratch Pad** — large outputs to file
15. **Compression** — save state at 70% context
16. **Simple Tasks** — no agents for simple work

## Ecomode (Smart Model Routing)

| Complexity | Model | Use For |
|-----------|-------|---------|
| Simple | Haiku/Sonnet | formatting, renaming, git ops |
| Medium | Sonnet | features, bug fixes, code review |
| Complex | Opus | architecture, security audit, disputes |

## Project Structure

```
GODMODE/
  claude/
    CLAUDE.md           --> Global orchestrator rules (copy to ~/.claude/)
  skills/
    security/           --> 8 security skills
    development/        --> 7 development skills
    design/             --> 5 design skills
    ...                 --> 50+ skills total
  rules/
    delegator/          --> GPT/Gemini delegation rules
  docs/
    ARCHITECTURE.md     --> Detailed architecture description
    INSTALL_GUIDE.md    --> Step-by-step installation
    SKILL_GUIDE.md      --> How to create custom skills
  examples/
    dispute-example.md  --> Real dispute transcript
    skill-example/      --> Example skill structure
```

## FAQ

**Q: Do I need GPT and Gemini?**
No. GODMODE works with Claude alone. GPT and Gemini are optional advisors for disputes and second opinions.

**Q: Is this a framework I need to code with?**
No. It's a configuration layer for Claude Code. You install it and it works. No programming required.

**Q: Can I add my own skills?**
Yes. See `docs/SKILL_GUIDE.md` for the skill format. Skills are just markdown files.

**Q: Will this conflict with my existing Claude Code setup?**
It adds to your `~/.claude/` directory. Back up your existing config before installing.

## Limitations

- This is a **showcase/research project**, not a supported product
- Built and tested on Windows 11 — Mac/Linux should work but not extensively tested
- Skills are opinionated — they reflect one developer's workflow
- External model integration requires separate subscriptions (ChatGPT, Gemini)
- Limited support — issues may not receive replies

## License

MIT License — use it however you want.

## Author

Built by [neuron-one](https://github.com/neuron-one) — a solo non-programmer who builds real products entirely with AI. No CS degree. No dev team. Just one person and an AI army.

*GODMODE is not affiliated with Anthropic, OpenAI, or Google.*

# Archon — Nonprofit Solution Builder

**Build custom tools for your nonprofit by describing what you need. One sentence in, deployed app out.**

Archon is a multi-agent system that runs inside [Claude Code](https://docs.anthropic.com/en/docs/claude-code). You describe the tool your organization needs, and 9 specialized AI agents handle the rest — research, product design, accessible UI, engineering, testing, and deployment to free hosting.

**Cost:** $20/month for Claude Pro. $0/month to host what it builds.

---

## What You Need

- **A computer** running macOS, Linux, or Windows (with WSL)
- **Claude Pro** ($20/month) — [claude.ai/pro](https://claude.ai/pro)
- **Claude Code** (free, included with Pro) — runs in VS Code or the terminal
- **Node.js 18+** — [nodejs.org](https://nodejs.org)

You do NOT need to know how to code. You need to be comfortable copy-pasting commands into a terminal.

---

## Setup (5 minutes)

### Step 1: Install Claude Code

**Option A — VS Code (recommended for beginners):**
1. Open VS Code
2. Go to Extensions (Ctrl+Shift+X / Cmd+Shift+X)
3. Search "Claude Code" and install it
4. Open the Claude Code panel (look for the Claude icon in the sidebar)
5. Sign in with your Claude Pro account

**Option B — Terminal:**
```bash
npm install -g @anthropic-ai/claude-code
claude  # then sign in
```

### Step 2: Install Archon

Open a terminal (in VS Code: Terminal → New Terminal) and run:

```bash
chmod +x install.sh
./install.sh
```

You should see green checkmarks for all 12 files. That's it.

### Step 3: Build Something

In Claude Code, type:

```
/build A volunteer hour tracker where nonprofits can log volunteer hours, generate tax receipts, and see impact dashboards
```

Replace that with whatever your org actually needs. Archon will:
1. Research the problem and existing tools
2. Define requirements around impact (not revenue)
3. Design an accessible UI for non-technical staff
4. Pick a free tech stack
5. Write all the code
6. Test for accessibility and data privacy
7. Deploy to free hosting
8. Hand you a URL and an operator's guide

It pauses 3 times to check with you: after understanding your idea, after scoping the MVP, and when the app is live.

---

## The 9 Agents

| Agent | Role | What It Does |
|-------|------|-------------|
| **Scout** | Sector Researcher | Finds existing tools, gaps, and nonprofit-specific needs |
| **Compass** | Impact PM | Writes requirements focused on impact metrics, not revenue |
| **Palette** | Inclusive Designer | Designs accessible UI (WCAG AA) for non-technical users |
| **Architect** | $0 Stack Planner | Picks free-tier hosting and open-source tools |
| **Mason** | Engineer | Writes all the code with admin panels and data export |
| **Sentinel** | A11y + QA | Tests accessibility, data privacy, and functionality |
| **Tuner** | Budget Optimizer | Optimizes for free-tier hosting limits |
| **Deployer** | Free Hosting | Deploys to Vercel/Railway/Render at $0/month |
| **Validator** | Impact Checker | Verifies the app delivers on its impact promise |

---

## Example Ideas

- "A grant deadline tracker that sends email reminders and stores application notes"
- "A client intake form that saves to a database and generates weekly reports for our funder"
- "A donation thank-you letter generator that pulls from our donor list CSV"
- "A program waitlist manager where families can check their status online"
- "A board meeting agenda builder with voting and minutes export"

---

## FAQ

**Is the output production-ready?**
It's a working prototype — a real starting point. Have someone technical review it before putting real client data in.

**What if I already have a project started?**
If Archon's `.archon/state.json` file exists in your project, it picks up where it left off.

**What hosting does it use?**
Free tiers: Vercel, Railway, Render, or Fly.io. It always includes a Docker Compose file for self-hosting.

**What about data privacy?**
The AI sees your description, not your client data. The tools it builds handle data on hosting you control. The pipeline includes data privacy checks.

**Can I customize the agents?**
Yes. They're plain text files in `~/.claude/agents/`. Edit any of them.

---

## Uninstall

```bash
rm ~/.claude/agents/{scout,compass,palette,architect,mason,sentinel,tuner,deployer,validator}.md
rm ~/.claude/commands/build.md
rm -rf ~/.claude/skills/archon-orchestrator
```

---

**Built by Abdul Al-Basith** — [Amplify Impact](https://amplifyimpact.ca)

Questions? Reach out at abdul@amplifyimpact.ca

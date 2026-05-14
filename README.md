# AI Chief of Staff — Starter Kit

Build a personal AI system that knows how you work, preps your meetings, reviews your week, and gets smarter over time.

---

## What This Is

This is a framework for building your own AI chief of staff using [Claude Code](https://claude.ai/download). It's not a product you install — it's a system you grow. The kit gives you:

- **Guided workbooks** to teach your AI about you (your work patterns, team, priorities, tools)
- **A workspace template** to organize your AI's knowledge and outputs
- **Example skills** you can customize and run immediately
- **Architecture patterns** that work regardless of which tools you use

## What This Isn't

This is **not** a copy of someone else's system with the names removed. Your AI chief of staff needs to understand YOUR work patterns, YOUR team dynamics, YOUR priorities. The workbooks in this kit help you discover and articulate those things — they don't prescribe answers.

The example skills are starting points, not finished products. They'll be mediocre on the first run. That's by design. Each run teaches you what to refine.

---

## Prerequisites

- **Claude Code** installed ([claude.ai/download](https://claude.ai/download))
- **A calendar** you can connect (Google Calendar, Outlook, etc.)
- **1-2 hours** for initial setup, then 15-30 minutes of refinement per week
- **No coding experience required** — you're writing plain English prompts and organizing files
- **A markdown editor** — [Obsidian](https://obsidian.md) (free) is recommended. It makes reading and editing `.md` files feel like using a notes app instead of wrestling with code. You can also use any text editor.

### Optional but valuable:
- A task manager with an MCP connector (OmniFocus, Todoist, Asana, etc.)
- A notes app with an MCP connector (Evernote, Notion, Obsidian, etc.)
- Slack or Teams access via MCP connector

The system works with just a calendar. Each additional tool you connect makes it more useful, but none are required to start.

---

## Quick Start with `/init`

The fastest way to get started is the interactive setup wizard. Open Claude Code in your workspace and type:

```
/init
```

It will walk you through 5 questions, then generate your starter files automatically. Takes about 10 minutes.

After `/init`, you can expand your system with:
- `/init-team` — build your relationship map
- `/init-priorities` — define your strategic focus
- `/init-meeting-prep` — activate your first skill
- `/init-weekly-review` — set up your weekly anchor habit

Each one is a guided conversation that generates real files from your answers. Run `/init` anytime to see your progress and pick what to set up next.

**Prefer to set things up manually?** Skip to [Getting Started](#getting-started-suggested-order) below — the workbooks in `me/` guide you through the same process at your own pace.

---

## What's in This Kit

```
starter-kit/
│
├── README.md                    ← You are here
├── CLAUDE-template.md           ← Workspace rules template
├── architecture-patterns.md     ← The 3 ideas that make it work
│
├── me/                          ← Guided self-discovery workbooks
│   ├── how-i-work.md            ← Your rhythms, habits, capture methods
│   ├── my-team.md               ← Your people and relationships
│   ├── my-priorities.md         ← What matters most right now
│   └── my-tools.md              ← Your tool inventory + connections
│
└── skills/                      ← Skill architecture + examples
    ├── README.md                ← How skills work
    ├── init/                    ← Interactive setup wizard
    │   └── SKILL.md
    ├── init-team/               ← Build your relationship map
    │   └── SKILL.md
    ├── init-priorities/         ← Define your strategic focus
    │   └── SKILL.md
    ├── init-meeting-prep/       ← Activate meeting prep skill
    │   └── SKILL.md
    ├── init-weekly-review/      ← Activate weekly review skill
    │   └── SKILL.md
    ├── example-meeting-prep/    ← Meeting prep reference template
    │   └── SKILL.md
    └── example-weekly-review/   ← Weekly review reference template
        └── SKILL.md
```

---

## Getting Started (Suggested Order)

### Week 1: Foundation

**Day 1 — Set up your workspace (30 min)**
1. Create a workspace folder (e.g., `~/ai-workspace/`)
2. Initialize git: `git init`
3. Copy `CLAUDE-template.md` to your workspace root and rename to `CLAUDE.md`
4. Fill in the placeholders (your name, workspace path)
5. Create the folder structure: `me/`, `outputs/`, `reference/`, `_claude/`

**Day 1-2 — Fill in your workbooks (60-90 min total)**
Work through each file in `me/`, one at a time:
1. Start with `how-i-work.md` — this is the foundation
2. Then `my-team.md` — list your top 5 people
3. Then `my-priorities.md` — your top 3 priorities
4. Then `my-tools.md` — inventory what you use

Don't try to be comprehensive. Answer what comes to mind. You'll refine over time.

**Day 3-4 — Run your first skill**
1. Copy `skills/example-meeting-prep/` to `.claude/skills/meeting-prep/` in your workspace
2. Read through the SKILL.md and customize the meeting categories for your role
3. Open Claude Code in your workspace and type `/meeting-prep`
4. Evaluate the output. What's useful? What's wrong? What's missing?
5. Refine the skill based on what you observe

**Day 5 — First weekly review**
1. Copy `skills/example-weekly-review/` to `.claude/skills/weekly-review/`
2. Run `/weekly-review` on Friday afternoon
3. Use it to update your `me/` files with what you learned this week

### Week 2: Iterate

- Run `/meeting-prep` daily. Notice what's improving and what's still off.
- Add more detail to your `me/` files based on what the AI gets wrong.
- Read `architecture-patterns.md` now that you have context for why each pattern matters.
- Consider connecting a second tool (task manager or notes app).

### Week 3+: Expand

- Build a new skill for something you do repeatedly (action item capture, email triage, etc.)
- Start thinking about the sub-agent pattern if your skills are getting slow.
- Your `me/` files should be getting richer and more accurate with each weekly review.

---

## How Long Before It's Useful?

| Milestone | Timeline |
|-----------|----------|
| First useful meeting prep | Day 3-4 |
| System feels personalized | Week 2-3 |
| You stop thinking of it as a tool and start thinking of it as a teammate | Week 3-4 |
| You build a skill without following an example | Month 2 |
| Someone asks "how do you do that?" | Month 2-3 |

---

## Key Principles

**1. Start simple, iterate often.**
Your first version of everything will be mediocre. That's fine. Run it, observe what's wrong, and fix one thing. Repeat. The people who get the most out of this iterate weekly, not monthly.

**2. 70% good is a trap.**
A skill that's 70% right feels impressive at first but creates trust debt. You'll start second-guessing every output, and eventually stop using it. Push each skill to 90%+ before building the next one. One great skill beats five mediocre ones.

**3. Honesty over aspiration.**
Write your `me/` files about how you ACTUALLY work, not how you wish you worked. If you never do a proper weekly review, say so. If you walk into every meeting unprepared, say so. Your AI can't help you improve a system it doesn't understand.

**4. Your system should be yours.**
Don't copy someone else's priorities, meeting categories, or reflection questions. The examples in this kit show different patterns so you can see the range — pick what resonates with YOUR work, or write your own.

**5. The `me/` files are the investment.**
Everything else — skills, outputs, architecture — follows from how well your AI understands you. If your skills feel generic, the fix is usually in your `me/` files, not in the skill instructions.

**6. Review and maintain.**
The system degrades if you don't maintain it. Stale priorities make your AI focus on the wrong things. Outdated team info makes meeting prep useless. The weekly review skill exists specifically to keep everything fresh.

---

## Further Reading

### In this kit
- **[Visual system overview](https://aneinstein.github.io/ai-chief-of-staff-starter-kit/overview.html)** — One-page visual walkthrough of what the full system looks like
- **`architecture-patterns.md`** — The 4 transferable ideas that make the system work
- **`skills/README.md`** — Deep dive on how to build and refine skills

### Background and lessons learned
- **[I Built Myself an AI Chief of Staff. Here's What It Looks Like.](https://www.linkedin.com/pulse/i-built-myself-ai-chief-staff-heres-what-looks-like-aaron-neinstein-keohc)** — Full walkthrough of the system, from individual agents to the compounding rhythm
- **[What I've Learned Building AI Agents for My Own Day-to-Day Use (Part 1)](https://www.linkedin.com/pulse/what-weve-learned-building-ai-agents-ourselves-aaron-neinstein-lxfkc)** — The five categories of agents that consistently deliver value
- **[How I Think About Building AI Agents That Actually Get Used (Part 2)](https://www.linkedin.com/pulse/how-i-think-building-ai-agents-actually-get-used-aaron-neinstein-hrgbc)** — Eight hard-won lessons, including why 70% good is a trap
- **[Where to Begin Without Feeling Overwhelmed](https://www.linkedin.com/posts/aaronneinstein_have-talked-to-a-lot-of-people-recently-who-activity-7442238969162915840-TGBu)** — Four practical steps for non-technical professionals who feel behind on AI
- **[5-minute video walkthrough of the live system](https://www.linkedin.com/posts/aaronneinstein_several-weeks-ago-i-published-an-article-ugcPost-7455089750731825152-27A6)** — Unscripted demo showing the system in action

### Tools
- **Claude Code** — [claude.ai/download](https://claude.ai/download)
- **Obsidian** (recommended markdown editor) — [obsidian.md](https://obsidian.md)

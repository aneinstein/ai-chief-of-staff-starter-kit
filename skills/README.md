# Skills — Your AI's Capabilities

## What is a Skill?

A skill is a reusable set of instructions that your AI can run on command. When you type `/meeting-prep` in Claude Code, it reads the skill file and executes those instructions.

Think of skills like recipes for your AI. Each one describes:
- What to do (gather context, analyze, produce an output)
- Where to look (which files to read, which tools to query)
- What to produce (a document, a task list, an analysis)

## Anatomy of a Skill

Each skill is a folder with a `SKILL.md` file inside:

```
.claude/skills/
  meeting-prep/
    SKILL.md          ← The instructions
  weekly-review/
    SKILL.md
  action-sweep/
    SKILL.md
```

A SKILL.md file has two parts:

```markdown
---
description: One-line description of what this skill does
user_invocable: true
---

# Skill Name

[The actual instructions — written in plain English]
```

The `---` block at the top (called "frontmatter") tells Claude Code:
- `description` — what shows up in the skill list
- `user_invocable: true` — you can trigger it by typing `/skill-name`

Everything below the frontmatter is the prompt — the instructions your AI follows when the skill runs.

## How to Write Good Skill Instructions

### 1. Start with context
Tell the skill what files to read first. Your `me/` files contain the context that makes the output personalized:

```markdown
Start by reading these files to understand my context:
- `me/how-i-work.md` — my daily rhythm and preferences
- `me/my-team.md` — the people I work with
```

### 2. Be specific about what to gather
Don't say "check my calendar." Say "check my calendar for today's meetings, including the meeting title, time, attendees, and any description or agenda."

### 3. Describe the output format
Show what the output should look like. Your AI will follow formatting examples closely:

```markdown
Format the output as:

## [Meeting Name] — [Time]
**Attendees:** [list]
**Context:** [what I need to know going in]
**My prep:** [what I should do or think about before this meeting]
```

### 4. Include decision logic
The best skills handle different scenarios:

```markdown
For each meeting, decide what kind of prep it needs:
- **1:1 with a direct report:** Focus on their recent work, any blockers
  they've mentioned, and career development themes
- **Cross-functional sync:** Focus on what my team owes theirs and what
  they owe us
- **Standup / status update:** Minimal prep — just list what I should
  mention from my team
- **External meeting:** Research the person/company, surface any recent
  news or past interactions
```

### 5. Tell it where to put the output

```markdown
Save the output to `outputs/meeting-preps/YYYY-MM-DD-meeting-prep.md`
```

## Building Your First Skill

See the two example skills in this folder:
- `example-meeting-prep/SKILL.md` — A meeting prep skill (the most universally useful first skill)
- `example-weekly-review/SKILL.md` — A weekly review skill (great second skill)

Both are fully functional starting points. Read them, customize them for your context, then copy them to `.claude/skills/` in your workspace.

## Tips for Skill Development

**Start simple, iterate often.** Your first version of any skill will be mediocre. Run it 3-4 times and notice what's missing or wrong. Each observation becomes a refinement.

**Read the output critically.** When the AI produces something unhelpful, ask yourself: did it have the information it needed? If not, add context to your `me/` files. Did it have the information but use it wrong? Refine the skill instructions.

**One skill per problem.** Don't build a mega-skill that does everything. Build a meeting prep skill, a weekly review skill, a task capture skill. Small skills are easier to debug and improve.

**Name skills as commands.** Use verb-noun: `meeting-prep`, `weekly-review`, `action-sweep`. When you type `/meeting-prep`, it should be obvious what's about to happen.

## When to Use Sub-Agents

As your skills get more complex, a single prompt might try to do too much at once — check calendar, read emails, search Slack, query your task manager, summarize everything. This can hit context window limits or get slow.

The solution is **sub-agents** — your skill launches smaller, focused tasks in parallel, each gathering one piece of context, and then synthesizes the results.

Example:
```markdown
Launch these research tasks in parallel:
1. Agent 1: Check today's calendar and list all meetings with attendees
2. Agent 2: Search Slack for messages from my direct reports in the last 24 hours
3. Agent 3: Check my task manager for items due this week

Then synthesize the results into a single briefing document.
```

You don't need sub-agents for simple skills. Start without them and add them when a skill starts feeling slow or hitting limits.

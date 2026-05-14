# CLAUDE.md — Your AI Workspace Rules

<!--
  HOW TO USE THIS FILE:
  1. Copy this file to the root of your workspace folder
  2. Rename it to CLAUDE.md
  3. Replace all [PLACEHOLDERS] with your information
  4. Read the comments (<!-- -->) — they explain WHY each section exists
  5. Delete sections you don't need. This is YOUR system — keep what's useful.
-->

<!--
  WHAT THIS FILE DOES:
  Claude Code reads this file at the start of every conversation. It's how
  your AI knows the rules: where files go, what it's allowed to do, and how
  to behave. Think of it as the employee handbook for your AI.

  Without this file, every session starts from scratch. With it, your AI
  has consistent behavior across conversations.
-->

## About This Workspace

This workspace belongs to [YOUR NAME]. It's the home base for my AI chief of staff system. Everything the AI needs to know about me, everything it creates, and everything I bring in for it to work with lives here.

**Workspace path:** `[YOUR WORKSPACE PATH, e.g. ~/ai-workspace/]`

## Folder Structure

<!--
  WHY THIS MATTERS:
  Without a clear folder structure, files pile up randomly and your AI
  can't find anything. This structure separates YOUR context (me/) from
  AI outputs (outputs/) from raw inputs (reference/) from AI scratch
  space (_claude/). This separation makes everything easier to find
  and prevents the AI from accidentally modifying your personal notes.
-->

- **`me/`** — Context about who I am and how I work. The AI reads these files to understand me. I update them periodically.
  - `how-i-work.md` — My daily rhythms, habits, capture methods
  - `my-team.md` — People I work with, relationship dynamics
  - `my-priorities.md` — What matters most right now
  - `my-tools.md` — Tools I use, accounts, integrations

- **`outputs/`** — Things the AI creates for me. Deliverables, preps, analyses, drafts.
  - Organized by topic: `outputs/meeting-preps/`, `outputs/weekly-reviews/`, etc.
  - Each file is date-prefixed: `2026-03-12-weekly-review.md`

- **`reference/`** — Documents I bring in for the AI to work with. Data files, PDFs, spreadsheets, reference material.

- **`_claude/`** — The AI's scratch space. Plans, intermediate work, scripts. I might look at these but they're for the AI's use.

<!--
  OPTIONAL FOLDERS — add these if/when you need them:
  - `health/` — personal health data (labs, fitness, etc.)
  - `docs/` — long-form documentation
  Add more as your system grows. The key principle: every file has a home.
-->

## Rules for the AI

<!--
  WHY RULES MATTER:
  Without explicit rules, the AI makes assumptions. Some of those
  assumptions will be wrong, and you won't notice until something
  breaks or gets weird. Rules prevent surprises.

  Start with these basics. Add more as you discover situations where
  the AI does something unexpected.
-->

### File Rules
- **Always read `me/` files before starting a task** — that's your context about who I am
- **Put finished work in `outputs/`** in the appropriate topic subfolder
- **Don't create files outside this workspace** without asking first
- **Don't modify files in `me/`** unless I explicitly ask — those are my source of truth

### Safety Rules
- **Ask before doing anything destructive** — deleting files, overwriting work, bulk changes
- **Ask before sending anything** — messages, emails, calendar invites
- **Ask before installing software** — no global installs without permission
- **Don't access sensitive paths** — no SSH keys, no credentials files, no env files

### Naming Conventions
<!--
  WHY NAMING CONVENTIONS:
  Consistent naming means files sort predictably in Finder and your AI
  can find things by pattern. Date prefixes mean things sort chronologically.
-->
- Lowercase, hyphens (no spaces, no underscores): `weekly-review.md` not `Weekly Review.md`
- Date prefix for files that accumulate: `2026-03-12-meeting-prep.md`
- No date prefix for files that get updated in place: `strategic-goals.md`

### Communication Style

<!--
  CUSTOMIZE THIS: Tell the AI how you like to receive information.
  This dramatically affects the quality of outputs.
-->

[Choose what fits you, or write your own:]

- Keep outputs concise — I scan, I don't read essays
- Use bullet points and headers — I need to be able to find things quickly
- Lead with the most important thing — don't bury the headline
- If something needs my decision, say so clearly and give me options
- Don't over-explain — if I want more detail, I'll ask
- **Use plain, non-technical language** when asking for permission or explaining what you're about to do. Say "I'd like to check your calendar for today's meetings" not "querying Google Calendar MCP connector." If an action makes changes, say so clearly: "This will create 3 tasks in your task manager." If it just reads something, say "This is safe — just reading a file."

<!--
  WHY PLAIN LANGUAGE MATTERS:
  Many people using this kit aren't software engineers. Your AI will
  sometimes need to ask permission or explain what it's doing. If it
  uses jargon (MCP connectors, API calls, git operations), you'll feel
  lost and either approve things you don't understand or get frustrated.
  Plain language builds trust. Trust leads to delegation. Delegation is
  the whole point.
-->

### Tool Permissions

<!--
  WHY TOOL PERMISSIONS:
  MCP connectors give your AI access to real tools — calendar, tasks,
  email, notes. Some of these can make changes. You want to be explicit
  about what's auto-approved and what requires your confirmation.

  Start restrictive. Loosen as you build trust.
-->

**Auto-approved (read-only is generally safe):**
- Reading my calendar
- Searching my notes
- Viewing my task list
- Reading files in this workspace

**Ask first (these make changes or are visible to others):**
- Creating or modifying calendar events
- Sending messages or emails
- Creating tasks in my task manager
- Writing to any location outside this workspace
- Any action that's visible to other people

## Git Workflow

<!--
  WHY GIT:
  Your workspace is a git repo. This means every change is tracked,
  you can undo mistakes, and you have a backup. The AI should commit
  after meaningful work so you never lose progress.

  If you don't use git, delete this section. But it's strongly recommended.
-->

- Commit after meaningful work sessions (creating files, finishing analyses)
- Keep commit messages short and descriptive
- Push after committing to back up to your remote
- Never force push or amend commits without asking

<!--
  WHAT TO ADD OVER TIME:
  As your system grows, you'll discover new rules you need. Common additions:

  - Specific instructions for how to format meeting preps
  - Rules about which calendar to check (work vs. personal)
  - Preferences for how action items should be formatted
  - Team-specific conventions (how your team names things, etc.)

  The best CLAUDE.md files grow organically. Start simple, add when you
  notice the AI doing something you don't want, or not doing something
  you wish it would.
-->

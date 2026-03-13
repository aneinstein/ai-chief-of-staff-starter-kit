# Architecture Patterns — The Ideas That Transfer

These three patterns are the architectural foundation of an AI chief of staff system. They work regardless of which tools you use. If you adopt nothing else from this kit, adopt these.

---

## Pattern 1: Workspace as Source of Truth

### The idea

Everything your AI needs to know about you — your context, your preferences, your priorities, your team — lives in plain text files in a single folder. Not in a tool's database. Not in your head. Not scattered across apps. In files you can read, edit, version, and back up.

### Why it matters

When your AI's knowledge lives in markdown files:
- **It persists across conversations.** Claude Code reads your `me/` files at the start of every session. It doesn't forget who you are between conversations.
- **It's editable.** You can update your priorities in a text file. You can't easily update what an AI "remembers" from past conversations.
- **It's versionable.** Git tracks every change. You can see how your priorities evolved. You can undo a bad edit.
- **It's portable.** If a better AI tool comes along next year, your context files move with you. You're not locked in.
- **It's inspectable.** You can read exactly what your AI knows about you. No black box.

### How to implement it

```
your-workspace/
  CLAUDE.md          ← Rules and structure (the "employee handbook")
  me/                ← Your context (the AI reads these)
    how-i-work.md
    my-team.md
    my-priorities.md
    my-tools.md
  outputs/           ← What the AI produces (you consume these)
  reference/         ← What you bring in (raw inputs)
  _claude/           ← AI scratch space (working memory)
```

The `me/` folder is the heart. Every skill starts by reading one or more files from here. The better these files are, the better everything else works.

### Common mistake

Trying to put too much in CLAUDE.md. The CLAUDE.md file should be rules and structure — not your entire life story. Your personal context belongs in `me/` files that skills read on demand. Keep CLAUDE.md focused on "how should the AI behave" not "who am I."

---

## Pattern 2: Sub-Agent Context Management

### The idea

When a skill needs to gather information from multiple sources (calendar, email, tasks, notes, messages), don't do it all in one giant prompt. Instead, launch smaller, focused agents in parallel — each one gathers one piece of context — then synthesize the results.

### Why it matters

- **Speed.** Parallel queries complete faster than sequential ones.
- **Reliability.** If one data source is slow or fails, the others still succeed. You get a partial briefing instead of nothing.
- **Context efficiency.** Each sub-agent only carries the context it needs, not the entire conversation. This prevents hitting context window limits.
- **Debuggability.** When something is wrong in the output, you can identify which sub-agent brought bad data.

### How it works

```
Main Skill (orchestrator)
  ├─→ Agent 1: "Check today's calendar, return meetings with attendees"
  ├─→ Agent 2: "Search Slack for messages mentioning me in the last 24 hours"
  ├─→ Agent 3: "Check my task manager for items due this week"
  └─→ Agent 4: "Read my last 3 voice memos and extract key themes"
       │
       ▼
  Synthesizer: Combine all results into a single briefing
```

In a skill prompt, this looks like:

```markdown
Launch these research tasks in parallel using the Agent tool:

1. **Calendar agent:** Check my calendar for today. Return each meeting's
   title, time, attendees, and description.

2. **Messages agent:** Search my recent Slack messages and emails for
   anything from the people I'm meeting with today.

3. **Tasks agent:** Check my task manager for anything due this week
   and any items tagged with people I'm meeting today.

Once all agents return, synthesize their findings into a meeting prep
document following the format in Step 5.
```

### When you need this

You don't need sub-agents for simple skills (editing a draft, capturing a note). You need them when:
- Your skill queries 3+ data sources
- The total data would be too large for a single context window
- Speed matters (morning briefing should be fast)
- Reliability matters (one failed query shouldn't kill the whole skill)

### Common mistake

Over-engineering. Don't launch 8 sub-agents for a simple meeting prep. Start with everything inline in one prompt. When you notice it's getting slow or hitting limits, break the expensive parts into sub-agents.

---

## Pattern 3: Shared Data Caching

### The idea

When multiple skills need the same data (your calendar, your tasks, your recent messages), query it once and save the results to a shared file. Other skills read the cached file instead of re-querying.

### Why it matters

- **Faster skills.** Reading a local file takes milliseconds. Querying an API takes seconds.
- **Fewer API calls.** Some integrations have rate limits. Caching means you hit them less.
- **Cascade protection.** If your calendar connector goes down, skills that already have cached calendar data still work.
- **Consistency.** Multiple skills running in the same session all see the same calendar data, not slightly different snapshots.

### How it works

```
Morning routine:
  1. Cache agent queries calendar → saves to _claude/cache/calendar.md
  2. Cache agent queries tasks   → saves to _claude/cache/tasks.md
  3. Cache agent queries messages → saves to _claude/cache/messages.md

Skills throughout the day:
  - /meeting-prep reads _claude/cache/calendar.md (fast)
  - /daily-briefing reads all three cache files (fast)
  - /action-sweep reads _claude/cache/tasks.md (fast)
```

### Freshness model

Cached data goes stale. You need a simple rule for when to re-query vs. when to trust the cache:

| Data age | Action |
|----------|--------|
| < 4 hours | Use cache as-is |
| 4-8 hours | Use cache but note it may be stale |
| > 8 hours | Re-query the source |

Add a timestamp to each cache file so skills know how old the data is:

```markdown
# Calendar Cache
**Last updated:** 2026-03-12 08:15 AM Pacific
**Source:** Google Calendar (work + personal)

## Today's Meetings
...
```

### When you need this

Not at first. Start with skills that query data directly. When you notice:
- The same data being queried multiple times per session
- Skills running slowly because of redundant API calls
- Failures in one connector breaking multiple skills

...that's when you add a caching layer.

### Common mistake

Caching too aggressively. Don't cache things that change frequently (like "unread messages") or things that are cheap to query. Cache things that are expensive to gather, change slowly, and are needed by multiple skills.

---

## How These Patterns Build on Each Other

```
Pattern 1 (Workspace as Truth)
    provides the foundation — everything lives in files

Pattern 2 (Sub-Agents)
    solves the problem of gathering too much data for one prompt

Pattern 3 (Shared Caching)
    solves the problem of multiple skills needing the same data
```

Start with Pattern 1. It's required. Patterns 2 and 3 are optimizations you add when your system grows complex enough to need them. Most people can run happily with just Pattern 1 for months.

# My Tools — Technology Inventory

This file maps out the tools you use daily so your AI knows where to find information and where to put things. Your skills read this to know which MCP connectors to use and how to route data.

**How to use this:** List every tool you use for work. Be honest about which ones you actually use vs. which ones you technically have access to but never open. Your AI should focus on the tools you live in.

---

## Discovery Questions

Before listing your tools, think about:

1. **Where does your calendar live?** (Google Calendar, Outlook, Apple Calendar?)
2. **Where do your emails live?** (Gmail, Outlook, multiple accounts?)
3. **Where do you manage tasks?** (OmniFocus, Todoist, Things, Asana, Linear, Jira, Apple Reminders, nowhere?)
4. **Where do you take notes?** (Notion, Obsidian, Apple Notes, Evernote, Google Docs, OneNote, paper?)
5. **Where does your team communicate?** (Slack, Teams, email, Discord?)
6. **Where do you store documents?** (Google Drive, Dropbox, SharePoint, Confluence, Notion?)
7. **Where do you track projects?** (Same as tasks? Different tool? Jira, Asana, Linear, Monday?)
8. **Do you have a CRM?** (Salesforce, HubSpot, a spreadsheet, nothing?)

---

## Your Tool Inventory

For each tool, capture:

```markdown
### [Tool Name]

**What I use it for:** [Be specific — "everything" isn't helpful]
**How central is it:** [Core (daily), Regular (weekly), Occasional, Rarely]
**Account:** [Personal account, work account, which email?]
**MCP connector available?** [Yes/No/Don't know]
**API access?** [Yes/No/Don't know]
**Notes:** [Quirks, multiple accounts, shared with others, etc.]
```

---

## Common Tool Stacks

Here are three common setups to give you a sense of what a tool inventory looks like. Yours will be different — that's the point.

### Stack A: Google + Slack + Notion

```
### Google Calendar
What I use it for: All meetings (work and personal, separate calendars)
How central: Core — I live in this
Account: work@company.com (work), personal@gmail.com (personal)
MCP connector: Yes (Google Calendar MCP)
Notes: Work calendar is the source of truth. Personal calendar has
family stuff that occasionally conflicts with work.

### Gmail
What I use it for: External communication, notifications, some internal threads
How central: Regular — I check 3x/day
Account: work@company.com
MCP connector: Yes (Gmail MCP)
Notes: Most internal communication happens on Slack, not email.
Email is more for external vendors and formal stuff.

### Slack
What I use it for: All internal communication, quick decisions, water cooler
How central: Core — it's always open
Account: Company workspace
MCP connector: Yes (Slack MCP)
Notes: I'm in 40+ channels but only actively read about 8. My DMs
are where the real decisions happen. I have notifications on for
my team channel and my manager's DMs only.

### Notion
What I use it for: Notes, meeting agendas, project docs, personal wiki
How central: Core — this is where I think
Account: work@company.com
MCP connector: Yes (Notion MCP)
Notes: I have a "Daily Log" database that I write in each day.
Team docs are in shared spaces. Personal thinking goes in my
private workspace.

### Todoist
What I use it for: Personal task management
How central: Regular — I review daily
Account: personal@gmail.com
MCP connector: Yes (Todoist MCP)
Notes: I use projects for areas of responsibility and labels for
context (@ home, @ laptop, @ call). Weekly review on Sunday evening.
```

### Stack B: Microsoft + Asana

```
### Outlook Calendar
What I use it for: All work meetings
How central: Core
Account: work@company.com
MCP connector: Yes (Microsoft 365 MCP)
Notes: My EA has edit access and schedules things for me.

### Outlook Email
What I use it for: All work communication
How central: Core — I process email in batches, 3x/day
Account: work@company.com
MCP connector: Yes (Microsoft 365 MCP)
Notes: I use categories to triage: Red = urgent, Yellow = this week,
Blue = reference. Unread count is meaningless because newsletters.

### Teams
What I use it for: Real-time chat, video calls, some channels
How central: Regular
Account: work@company.com
MCP connector: Yes (Microsoft 365 MCP)
Notes: Teams is our default for video. Chat is secondary to email
at our company (more formal culture).

### Asana
What I use it for: Project tracking, team task management
How central: Core — this is how my team coordinates
Account: work@company.com
MCP connector: Yes (Asana MCP)
Notes: Each project is a workstream. I use "My Tasks" view daily.
The board view is how we run standups.

### OneNote
What I use it for: Meeting notes, brain dumps
How central: Regular — I write in it daily, review weekly
Account: work@company.com
MCP connector: Limited (read-only via Microsoft MCP)
Notes: Organized by notebook (one per quarter) with sections for
each project. I use tags for action items.
```

### Stack C: Minimal / Apple-Native

```
### Apple Calendar
What I use it for: All calendars (work via Exchange, personal)
How central: Core
MCP connector: Limited (via Zapier or shortcuts)
Notes: I use calendar colors to distinguish work, personal, and
family events. No separate app — just the built-in one.

### Apple Mail
What I use it for: All email
How central: Regular — I check a few times a day
MCP connector: Limited
Notes: I use VIP for people whose emails I want to see immediately.
Everything else I batch process.

### Apple Notes
What I use it for: Everything — meeting notes, ideas, lists, links
How central: Core — it's fast and always there
MCP connector: Very limited
Notes: I have a "Work" folder and a "Personal" folder. That's about
as organized as it gets. Quick capture is the superpower here.

### Apple Reminders
What I use it for: Tasks and to-dos
How central: Regular
MCP connector: Limited (via Shortcuts)
Notes: I use lists for areas: Work, Home, Shopping, Someday.
Siri integration means I can add tasks by voice.
```

---

## Connecting Your Tools

Once you've listed your tools, the next step is connecting them to Claude Code via MCP connectors. Not every tool has a connector, and that's OK — your AI can still be useful by working with the tools that do connect.

**To check what MCP connectors are available:**
- Look at the MCP server directory in Claude Code settings
- Search for your tool name + "MCP server" online
- Some tools connect through Zapier or Make as an intermediary

**Priority order for connecting tools:**
1. **Calendar** — this unlocks meeting prep, which is the most immediately useful skill
2. **Notes/docs** — this lets your AI read your context and capture outputs
3. **Tasks** — this lets your AI suggest and create action items
4. **Communication (Slack/email)** — this lets your AI gather context from messages
5. **Everything else** — connect as needed for specific skills

**If a tool doesn't have a connector:** That's fine. Describe it in this file anyway. Your AI can still reference it in prep ("check your Apple Notes from yesterday's meeting") even if it can't directly access the data.

---

## Revisiting This File

Update when:
- You adopt a new tool or drop an old one
- You change accounts (new job, new email)
- You discover a new MCP connector for a tool you use
- You find a quirk or limitation with a connected tool (document it here so all your skills benefit)

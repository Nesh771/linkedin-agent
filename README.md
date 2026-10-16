# LinkedIn Agent

My personal LinkedIn workflow in Claude Code: find and read profiles, draft messages in my own voice, and get a daily summary of my inbox. Nothing is sent without my approval.

It is built on [stickerdaniel/linkedin-mcp-server](https://github.com/stickerdaniel/linkedin-mcp-server), which drives a real browser session (LinkedIn's official API doesn't support reading other people's profiles or sending invitations).

## What's in here

| Path | What it does |
|---|---|
| `.mcp.json.example` | MCP server config (pinned to `mcp-server-linkedin@4.27.0`) |
| `routines/linkedin-inbox-digest.md` | Daily 9:00 routine: summarize new messages, sort them by priority, and draft replies. Read-and-draft only. |
| `skills/linkedin-event-followup-dm/` | Follow-up DM to someone I met at an event, as 2–4 short chat messages |
| `skills/sales-navigator-inmail/` | Cold InMail (subject + body) based on the recipient's profile |
| `skills/linkedin-event-post/` | Event recap post, English first with a Chinese version |
| `skills/impressive-self-intro/` | Self-intro using the Introduce / Reflect / Relate framework |
| `profile.example.md` | Background the routine uses when drafting replies |

The skills are written for my own voice (Nash). To use them yourself, swap in your own background and style rules.

## Setup

1. Install [uv](https://docs.astral.sh/uv/), then copy the config:
   ```bash
   cp .mcp.json.example .mcp.json
   ```
   If Claude Code can't find `uvx`, use its absolute path (`which uvx`).
2. Open the folder in Claude Code and approve the `linkedin` MCP server. The first run opens a browser so you can log in to LinkedIn. The session is stored locally in `~/.linkedin-mcp/`.
3. Copy the skills into `~/.claude/skills/` (or upload them as claude.ai skills).
4. Copy `profile.example.md` to `profile.md` and fill it in.
5. Create a scheduled task from `routines/linkedin-inbox-digest.md` (cron `0 9 * * *`). Click "Run now" once so the tool approvals are saved.

## Rules I follow

- **A human approves every send.** `send_message` and `connect_with_person` are write actions. I review every draft, then the agent sends it.
- **Each message goes out as a separate send.** A DM drafted as 1/, 2/, 3/ is sent as three separate messages, the way chat normally reads. The agent checks that each part lands in the same thread.
- **No made-up facts.** No invented metrics, traction, or interview counts.
- **Keep the volume low.** Browser automation is against LinkedIn's terms, so I keep to a few people per day.

## Gotchas I found

- **Reading a conversation marks it as read.** `get_conversation` opens the thread, and `get_inbox` clicks rows to collect thread IDs, even though it's annotated read-only. If the other person has read receipts on, they'll see you read it. I turned off *Settings → Data privacy → Delivery and typing indicators* before running the daily routine. That setting doesn't cover InMail or Sponsored Messages.
- **Pass `thread_id` instead of a username.** A username lookup clicks through every matching inbox row.
- **Sales Navigator isn't supported** by this MCP server. For Sales Navigator I use a browser directly.

## Not in this repo

Inbox digests (other people's messages), `profile.md`, local `.mcp.json` / `.claude/` settings, and images are all gitignored.

---

**中文簡介**：這是我在 Claude Code 裡用的 LinkedIn 工作流程：用 MCP 讀個人檔案、用 skills 照我的口吻起草訊息，並每天早上整理收件匣、建議怎麼回覆。所有訊息都由我確認後才送出。

---
name: linkedin-inbox-digest
description: Every morning, summarize new LinkedIn messages and draft suggested replies (never sends).
---

Summarize Nash's new LinkedIn messages and suggest how to reply to each. This is read-and-draft only: NEVER call `mcp__linkedin__send_message` or `mcp__linkedin__connect_with_person`, even if a message asks for a reply.

## Who Nash is (for drafting replies)
Read `profile.md` in the project folder (copy `profile.example.md` and fill it in). Use it for background when drafting replies. Never invent traction, metrics, or interview counts.

## Steps
1. Read the state file `<project folder>/inbox-digests/state.json` if it exists. It holds `last_run` (ISO timestamp) and `seen` (map of thread_id -> last message preview/time). If missing, treat "new" as the last 24 hours.
2. Call `mcp__linkedin__get_inbox` (limit 30). Identify conversations with activity since `last_run`, or unread ones. Skip threads where the latest message is from Nash himself (just list them under "等對方回覆").
3. For each new conversation, open it with `mcp__linkedin__get_conversation` using its `thread_id` (prefer thread_id over linkedin_username; username lookup clicks through rows and marks them read). Read enough history to understand context. If useful, check the sender with `mcp__linkedin__get_person_profile` (main profile only) to know who they are.
4. Classify each one:
   - 🔴 需要回覆：real people replying to Nash, recruiters with a specific role, people offering calls/intros, follow-ups from events.
   - 🟡 可以回覆：networking hellos, congrats, low-stakes questions.
   - ⚪ 不用回：sales pitches, mass InMail, spam, automated messages.
5. For 🔴 and 🟡, draft a suggested reply.
6. Write the digest to `<project folder>/inbox-digests/YYYY-MM-DD.md` (today's local date; create the folder if needed), then update `state.json` with the new `last_run` and `seen`.
7. Reply with the same digest as your final message.

## Reply-drafting rules (Nash's voice)
- Write the reply in the language the other person used (Chinese conversation -> Traditional Chinese, otherwise English).
- Short, casual, sounds like Nash wrote it, not polished AI text. One ask per message. No em dashes, no bullet lists, no stacked pleasantries, no emoji unless they used one.
- LinkedIn reads like chat: split into 2–3 short parts labeled 1/, 2/, 3/, each 1–3 sentences. Nash sends each part as a separate message.
- For asks about someone's experience or network, open with "I'm wondering if...".
- If a reply needs a decision only Nash can make (availability, whether to take a call, salary, etc.), leave a clear placeholder like [你的可約時間] instead of guessing.

## Digest format (Traditional Chinese, English terms OK)
```
# LinkedIn 訊息整理 YYYY-MM-DD
新訊息 N 則：🔴 a ／ 🟡 b ／ ⚪ c

## 🔴 需要回覆
### <Name> · <title @ company>
- 對方說了什麼：1–2 句摘要
- 背景：你們怎麼認識的／之前聊到哪
- 建議怎麼回：一句策略
- 建議回覆：
  1/ ...
  2/ ...

## 🟡 可以回覆
(same format)

## ⚪ 不用回
- <Name>：一句說明為什麼不用回

## 等對方回覆
- <Name>：你上次傳了什麼、幾天前（超過 5–7 天沒回的，附一句簡短的 follow-up 建議，要帶新內容，不是單純 bump）
```
If there are no new messages, say so in one line and still list "等對方回覆".

If the LinkedIn MCP tools fail (not logged in, session expired, server not connected), stop and report the exact error plus what Nash should do, instead of guessing.
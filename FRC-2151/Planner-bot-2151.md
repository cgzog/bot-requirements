These are the current requirements for the Planner → Planner - Zog routine, taken from its saved instructions.

## Schedule and access
- The main run is daily at 5:51 AM CT, weekends included. A catch-up run around 7:15 AM CT finishes anything left unfinished.
- Teams web is used in my browser as xxx@gmail.com, a guest in the Dist 209 org. The Teams connector can't reach that org.
- The channel always opens from the saved `channelLink`, because it's a private channel and may not show in the channel list.
- Never sign in to Google.
- If Microsoft asks for sign-in, never submit the prefilled number 0102112229. Use xxx@gmail.com and send the emailed code, then hand you the screen to type it. Codes are never asked for in chat.
- If Planner shows HTTP 400 "Request Too Long," stop and ask you before clearing Microsoft cookies.

## Reliability
- Track progress with `checkpoint.py` (status, start, phases, posts, deletes, finish) and resume any unfinished earlier run first.
- The time budget is 40 minutes before posting starts and 50 minutes total. If it runs out, save state and hand back a partial note.
- Open Task Chat only for new, reopened, or changed tasks, and reuse the saved chat otherwise.
- Build posts with `gen-posts.py`.
- The state file keeps only 2 days of `posted` entries and 14 days of notes. Older entries are archived.

## Planner read
- Read General > Planner, plan "2026 Season," filtered to xxx (GUEST).
- For each task, capture the title, bucket, progress, labels, due date, priority, assignees, task id, Notes, and Task Chat.
- Skip Completed tasks and anything in the Done or Won't do buckets.
- If the read fails, post and delete nothing.
- Never create or edit tasks, and avoid clicking Add task rows.

## Chat block
- Show every Task Chat entry that's new since the last run, with no cap. The newest batch replaces the old block.
- If nothing is new, keep the previous block.
- A task seen for the first time shows all of its chat.
- A reopened task shows at most its last 5 messages.
- Put one blank line between chat entries.

## Notes block
- Include the full current Notes text under "Latest notes updates:" with one blank line after the heading.
- Leave the block out when Notes are empty.
- When there's a chat block above it, put two blank lines before the notes heading.

## Post order
1. Overdue tasks, most overdue first.
2. Other dated tasks: due today first, then by date.
3. Undated tasks with Progress set to In progress.
4. All other undated tasks.

Ties sort alphabetically by title, then by task id. The visible order is checked after posting, and any ordering problem is reported to you rather than claimed as verified.

## Post format
- The subject is `"Task Name" - Label(s) - Bucket`, with the labels part dropped when a task has none.
- The subject gets at most one prefix, based on the America/Chicago calendar date:
  - `OVERDUE:` when the due date is before today.
  - `DUE TODAY:` when it's due today.
  - `UPCOMING:` when it's due 1 to 5 days out.
  - No prefix when it's due later or has no due date.
- The body starts with an "Open in Planner" link built from `linkTemplate`. It never uses a tasks.teams.microsoft.com address.
- The link is followed by the optional chat and notes blocks.
- Before clicking Post again, check whether the post already went up, so nothing is double-posted.

## Refresh and cleanup
- Save state before posting.
- Post all the fresh posts first, then delete every earlier routine task post, with or without a prefix.
- Never delete this run's posts or anyone else's messages.
- If a delete fails, skip that post and tell you about it.

## Reporting
After every run, I send you the counts of posts deleted and posted, plus new, dropped, or reopened tasks, bucket or label changes, tasks with new chat, posts that included notes, failed deletions, and any blocker.

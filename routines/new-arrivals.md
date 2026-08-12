---
schedule: "0 15 * * 5"
timeout: 20m
active: true
skills: [slack-desk]
credentials: [slack_bot_token]
---

Your job is the week's library news, posted where the readers are: one
top-level message in the ask channel ($ASK_CHANNEL) that a teammate
skims in thirty seconds and knows what the library holds this week that
it didn't last week.

## 1. Gather the week

All of it is already in knowledge — this routine reads, it doesn't
sweep:

- **New and changed**: doc-watch's events — pages added, materially
  changed, reorganized. Its noise-collapsing already happened; don't
  re-report typo batches it summarized.
- **Mended and drafted**: what shelf-check fixed and gap-fill drafted,
  with their PRs' fates if known.
- **Asked at the desk**: the week's questions — answered (the topics,
  not a transcript) and missed (the gap board's movement: new gaps,
  gaps now over the bar, drafts that resulted).
- Fold in open Agent-owned tasks in your lane (library news) — a
  requested announcement belongs in this post.

## 2. Compose

Short sections in Slack mrkdwn, each entry linked on the words that
describe it: what's new on the shelf, what got fixed, what people
asked, what's still missing. Plain words, one line per item, the reader
never made to open a link to understand the line. A section with
nothing gets dropped, not padded — and a week where every section drops
means no post at all: skip, record the NO-OP, and let next week's post
cover two.

## 3. Post

One top-level message via the slack-desk skill (its threading rule
doesn't apply here — announcements are the exception it names).
Before posting, check the channel for this week's post already
delivered — a retried run edits nothing and posts nothing twice; your
ledger holds the last post's timestamp. Record the posted link as an
event.

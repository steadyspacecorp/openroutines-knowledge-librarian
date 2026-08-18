<img src="avatar.svg" alt="" width="96" align="right">

A librarian for your team's knowledge base, built on
[OpenRoutines](https://openroutines.dev). Point it at the git
repositories your team's knowledge lives in — a handbook, runbooks, a
KMS of markdown — and it keeps the library worth trusting: it watches
what changes, mends broken links and stale indexes, answers questions
from it in Slack with citations, and turns the questions it couldn't
answer into the library's next pages.

Everything it does is visible where you already work: answers in your
ask channel within a few minutes, focused PRs against the library,
a weekly what's-new post, and a daily check-in — and you can talk back:
ask it to do something in the channel and the ask becomes its task.

## The routines

| Routine | What it does |
|---|---|
| reference-desk | Answers questions in the ask channel from the library only, in-thread, citing the pages it drew from. What the library doesn't cover becomes a recorded gap — never an invented answer. |
| github-doc-watch | Watches the library repos for changes, records what changed and what it affects, and observes filing and tagging drift against the repo's own conventions. |
| shelf-check | Sweeps the whole shelf weekly — broken links, orphans, stubs, out-of-date indexes — and mends what's mechanical by PR; judgment calls get flagged. |
| gap-fill | Works the desk's recorded gaps with an evidence bar: recurring questions earn a clearly-marked draft page by PR; undocumented territory becomes a task for its owner. |
| new-arrivals | Posts the week's library news to the ask channel: what's new, what got fixed, what people asked, what's still missing. |
| slack-report | The agent's own daily check-in, posted to your check-in channel: what it did, what it will do, where it needs a human. |
| slack-inbox | Answers replies in the check-in's thread. Ships inactive; the librarian's Slack app already has the scope it needs. |

Each routine states its own boundary between what it fixes and what it
flags. The agent makes mechanical changes by pull request — never a
direct commit — and files a task for anything that needs judgment; read
any file in `routines/` to see exactly what it may touch.

## Take it for a spin

Every working routine has a rehearsal scenario in `rehearsals/` — one
consistent fictional company knowledge base with a week of questions,
gaps, moved pages, and a broken index. A fixtured rehearsal strips all
credentials and never writes anything, so this works before any setup
beyond the CLI and Docker:

```bash
openroutines routines run reference-desk --rehearse
openroutines routines run shelf-check --rehearse
openroutines routines run gap-fill --rehearse
```

Each prints exactly what it would have done — the answer it would post
with its citations, the PR it would open, the gap it would record and
why. Edit a prompt, rehearse again, watch the judgment change. That's
the
[write–rehearse–run loop](https://openroutines.dev/docs/local-development/)
you'll use for routines of your own.

## Setup

You need the [OpenRoutines CLI](https://openroutines.dev/docs/getting-started/)
and about ten minutes.

1. **Use this template** to create your agent's repository, and clone it.
2. `openroutines configure` — fills in the owner, timezone, and model,
   and generates the `master.key` that encrypts credentials (back it up;
   it stays out of git).
3. Set `repo` in `openroutines.yml` to your new repository's URL, then
   set the variables: the library repositories
   (`docs_repos`), your ask channel, and your check-in channel — and the
   ask channel's ID in `routines/reference-desk.md`'s trigger URL.
4. GitHub, as an App — so the agent's PRs are its own, and each run gets
   a short-lived installation token instead of a long-lived personal
   one. Create a GitHub App
   ([Settings → Developer settings → GitHub Apps](https://github.com/settings/apps/new)):
   name it after your agent, deactivate the webhook, and grant
   repository permissions Contents and Pull requests (read and write).
   Install it on the library repo(s), then put the App ID in
   `openroutines.yml` and store the key:
   `openroutines credentials set github_app_private_key < your-app.private-key.pem`
5. Slack, for the desk and the check-in: create the app described in
   `.openroutines/plugins/slack-report/PLUGIN.md`, adding
   `channels:history` beside `chat:write` in the manifest's scopes —
   that one extra scope is what lets the librarian read questions.
   `openroutines credentials set slack_bot_token`, invite the bot to
   both channels, and verify the wiring:
   `OPENROUTINES_LOG_LEVEL=warn openroutines routines run slack-verify --no-knowledge`
   To let the librarian answer replies on its check-in too, put the
   check-in channel's ID in
   `.openroutines/plugins/slack-report/routines/slack-inbox.md`'s trigger
   URL and set that routine `active: true`.
6. `openroutines check`, commit, and
   [deploy](https://openroutines.dev/docs/deploying/).

This is your teammate now — rename it in `openroutines.yml`, retune the
schedules, and edit the routine prompts like any other file in your
repo. Ask it for things in the channel ("go ahead and fix those links")
and the next relevant run picks them up. Prefer the check-in somewhere
else? Swap the destination:
`openroutines plugin add steadyspacecorp/openroutines-plugins --path discord-report`
(or `--path steady`).

## Working on this agent

```bash
openroutines status                # what the agent has and still needs
openroutines sync                  # pull the latest knowledge; read the files under knowledge/
openroutines routines new <name>   # add a routine
openroutines routines run <name>   # real run; knowledge writes discarded (--write-knowledge settles)
openroutines check                 # validate everything; run it in CI
```

Deploying, updating, and everything else:
[OpenRoutines documentation](https://openroutines.dev).

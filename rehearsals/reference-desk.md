Work as if it is Thu 2026-08-06 09:15 (America/Los_Angeles), woken by
your trigger, and as if you are Knowledge Librarian, the agent for
Acme's library: $DOCS_REPOS is acme/handbook, and $ASK_CHANNEL is
C0LIB123AB (#ask-library). The fixtures below replace every outside
read and their formats are authoritative: work from them, not from live
systems or the knowledge files on disk.

## Fixtures

Your ledger: watermark 1754499600.000200 (Wed 08-05 12:00); no open
threads. The gap board:

```markdown
## Gap board

- **SOC 2 compliance status** — count 3 (07-16 Priya, 07-28 Tomás,
  08-05 Lena), threads linked. Over the bar as of 08-05.
- **Conference expense policy** — count 1 (07-30 Marco).
```

knowledge/context.md (kept by doc-watch): "Release process docs live
under eng/releases/ since the 08-04 restructure (previously
eng/deploys.md). Handbook docs carry `tags:` frontmatter."

`knowledge/tasks.md`: both sections empty.

The ask channel since your watermark (oldest first; you are
`U0LIBRARIAN`):

- ts 1754510400.000300, Wed 15:00, @marco: "how do I rotate the staging
  TLS cert? cert expiry warning in the deploy logs"
- ts 1754515800.000400, Wed 16:30, @priya: "librarian — a bunch of
  pages still link to the old deploys page after yesterday's
  restructure. go ahead and fix those links."
- ts 1754575920.000500, Thu 09:12, @dana: "what's the deploy freeze
  policy? trying to plan a friday release"

The library, where you look:

- `eng/releases/freeze-policy.md` — "Deploys freeze Friday 16:00
  through Monday 09:00. The release manager can grant exceptions for
  sev-1 fixes only."
- `eng/tls.md` — production TLS rotation, step by step. Its only
  mention of staging: "Staging certs are managed separately."
- No page anywhere covers staging certificate rotation.
- `eng/on-call.md`, `people/onboarding.md`, `eng/README.md` still link
  to `eng/deploys.md` (gone since 08-04).

## Output

Print, and nothing else:

1. Each reply you would post, verbatim (mrkdwn, with its thread_ts),
   in order.
2. Every ledger update — watermark, gap board — and every task and
   event line, verbatim.
3. Decision notes: anything you considered and decided against.

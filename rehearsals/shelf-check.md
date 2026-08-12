Work as if it is Tue 2026-08-11 09:00 (America/Los_Angeles), and as if
you are Knowledge Librarian, the agent for Acme's library: $DOCS_REPOS
is acme/handbook. The fixtures below replace every outside read and
their formats are authoritative: work from them, not from live systems
or the knowledge files on disk.

## Fixtures

Your ledger: last sweep Tue 2026-08-04, clean except one accepted
orphan (`people/alumni.md` — deliberate, per its own frontmatter). No
open PRs of yours.

knowledge/context.md (kept by doc-watch): "Release process docs live
under eng/releases/ since the 08-04 restructure (previously
eng/deploys.md). Handbook docs carry `tags:` frontmatter."

`knowledge/tasks.md`:

````markdown
```
- [ ] `task-YYYYMMDD-<n>` what must be done — context. (raised by <routine> YYYY-MM-DD)
```

## Agent-owned

- [ ] `task-20260806-1` fix the inbound links still pointing at the old
  eng/deploys.md after the 08-04 restructure — asked by Priya in
  #ask-library (thread 1754515800.000400). (raised by reference-desk
  2026-08-06)

## Human-owned
````

The shelf, as it stands:

- `eng/on-call.md` links to `eng/deploys.md` ("see the deploy process")
  — target gone; the content moved to `eng/releases/process.md`.
- `people/onboarding.md` links to `eng/deploys.md` ("read the deploy
  guide before your first release") — same.
- `eng/README.md` (the eng index) lists `deploys.md` and does not list
  `releases/process.md` or `releases/freeze-policy.md`.
- `eng/releases/freeze-policy.md` has no `tags:` frontmatter; every
  other eng doc carries `tags: [eng, process]`-style values, and
  `eng/releases/process.md` has `tags: [eng, releases]`.
- `eng/deploys-faq.md` — still present; nothing links to it, the eng
  index doesn't list it, and its content restates what
  `eng/releases/process.md` now covers, less currently.
- `security/incident-response.md` — body is "TODO".
- Everything else checks out: no other broken internal links.

## Output

Print, and nothing else:

1. Each PR you would open: branch name, title, the file edits verbatim,
   and the PR body.
2. Anything you would flag instead: each Human-owned task, verbatim.
3. The ledger updates and every event line, verbatim.
4. Decision notes: anything you considered and decided against.

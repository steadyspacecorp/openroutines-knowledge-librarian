Work as if it is Fri 2026-08-07 15:00 (America/Los_Angeles), and as if
you are Knowledge Librarian, the agent for Acme's library: $DOCS_REPOS
is acme/handbook, and $ASK_CHANNEL is C0LIB123AB (#ask-library). The
fixtures below replace every outside read and their formats are
authoritative: work from them, not from live systems or the knowledge
files on disk.

## Fixtures

Your ledger: last post Fri 2026-07-31 15:02 (ts 1754062920.000100).
The channel holds no post of yours newer than that.

The week's knowledge, as recorded (Mon 08-03 → Fri 08-07):

- Events from github-doc-watch: "Release docs restructured (08-04):
  eng/deploys.md split into eng/releases/process.md and
  eng/releases/freeze-policy.md — the freeze window is now its own
  page. One batch of typo fixes across people/ collapsed." Observation
  attached: three pages still link to the old path.
- Events from reference-desk: answered Dana's deploy-freeze question
  (thread linked) and Marco's staging-TLS question partially
  (production page cited; staging uncovered, gap recorded). Recorded
  Lena's SOC 2 ask — the gap's third — and took Priya's link-fix
  assignment for shelf-check's Tuesday sweep.
- Events from gap-fill: drafted "SOC 2 compliance status"
  (security/soc2.md, `status: draft`) — PR
  https://github.com/acme/handbook/pull/88, open, drafted from
  security/overview.md plus the three asks. Staging-TLS and
  conference-expense gaps waiting below the bar.
- shelf-check ran Tue 08-04 before the restructure's fallout and found
  the shelf clean; its next sweep is Tue 08-11.
- `knowledge/tasks.md` open: the link-fix assignment (Agent-owned,
  shelf-check's lane).

## Output

Print, and nothing else:

1. The message you would post: the exact chat.postMessage payload as
   JSON, verbatim.
2. Your ledger update and the event line, verbatim.
3. Decision notes: what you left out and why — and what would have made
   you skip the post entirely.

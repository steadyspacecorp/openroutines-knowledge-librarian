Work as if it is Thu 2026-08-06 10:00 (America/Los_Angeles), and as if
you are Knowledge Librarian, the agent for Acme's library: $DOCS_REPOS
is acme/handbook. The fixtures below replace every outside read and
their formats are authoritative: work from them, not from live systems
or the knowledge files on disk.

## Fixtures

The gap board in the reference-desk ledger:

```markdown
## Gap board

- **SOC 2 compliance status** — count 3 (07-16 Priya, 07-28 Tomás,
  08-05 Lena), threads linked. Over the bar as of 08-05.
- **Staging TLS rotation** — count 1 (08-05 Marco).
- **Conference expense policy** — count 1 (07-30 Marco).
```

Your own ledger: one prior verdict — "Conference expense policy:
waiting below the bar (judged 07-30 at count 1)." `knowledge/tasks.md`:
both sections empty.

knowledge/context.md: "Release process docs live under eng/releases/
since the 08-04 restructure. Handbook docs carry `tags:` frontmatter.
Security docs live under security/."

The library, where you look:

- `security/overview.md` — "Acme undergoes an annual SOC 2 Type II
  audit; we've maintained a clean report since 2024. Compliance
  questions go to the security team." Nothing else on the shelf
  mentions SOC 2. The page's frontmatter names no owner; git blame on
  security/ shows @sam-osei as the author of nearly all of it.
- `people/expenses.md` — general expense policy; conferences are not
  mentioned.
- `eng/tls.md` — production TLS rotation; staging explicitly "managed
  separately", nowhere documented.

## Output

Print, and nothing else:

1. For each gap: your verdict, and the artifact it produces — a draft
   page PR (branch name, title, the page's full content verbatim
   including frontmatter, PR body naming the asks that earned it) or a
   Human-owned task verbatim, or the wait.
2. Your ledger updates and every event line, verbatim.
3. Decision notes: anything you considered and decided against.

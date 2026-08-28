# Working agreement for Claude in this repo

This file is read automatically by Claude Code / Cowork sessions opened in this repo. It exists so every teammate's Claude behaves the same way here, even though none of us are coordinating that by hand.

## What this project is

Team project for the Birmingham AI Community Impact Lab hack-a-thon (sponsored by Anthropic). We're building a practical solution to a real Birmingham community problem — not a research project, not a reinvented wheel. See `docs/problem-statement.md` for the actual problem, scope, and what "done" looks like. If that file still looks like a template, the team hasn't locked in the problem yet — check with the human before assuming scope.

## Git workflow — read this before touching the repo

We're multiple people (and multiple Claude sessions) working in the same repo at hack-a-thon speed. Follow this every time, no exceptions:

1. **Pull before you start.** Run `git pull` (or `git pull --rebase` if you have local uncommitted work queued) before making any changes. Never assume your working copy is current.
2. **Commit in small, logical chunks** with clear messages (what changed and why, not just "updates"). Don't let a session's work pile up uncommitted — commit as you finish each coherent piece.
3. **Push often.** Don't sit on local commits for long stretches — the longer you wait, the more likely you collide with a teammate. After a meaningful commit, pull (to catch anything new), resolve any conflicts, then push.
4. **If `git push` is rejected** (someone pushed first), do `git pull` to merge/rebase, resolve conflicts carefully (don't blindly take "ours" or "theirs" — read both sides), then push again. Never force-push to `main`.
5. **Never force-push (`--force`/`--force-with-lease`) to `main`** or rewrite shared history, even to "clean up." If a mistake needs undoing, use a new commit (`git revert`) instead.
6. **Ask before deleting** branches, tags, or files you didn't create, unless the human you're working with explicitly asked for it.
7. **Never commit secrets** — API keys, tokens, `.env` files, credentials. Check `.gitignore` covers what it should before committing new file types (e.g. anything under a new `config/` or `secrets/` folder).
8. Feature branches are fine and encouraged for anything nontrivial or experimental (`git checkout -b <short-descriptive-name>`), but for small/quick changes during the event, committing directly to `main` is acceptable — use judgment based on how disruptive a conflict would be.

## Where things live

- `docs/problem-statement.md` — the problem, who it affects, why it matters, what already exists, our approach, scope, success criteria
- `docs/decisions.md` — running log of key decisions with date + rationale. **Update this whenever a nontrivial decision gets made** (tech stack, architecture, scope cuts) so the whole team stays in sync without a meeting.
- `docs/team.md` — team roster and roles

## General expectations

- Prioritize realistic, practical solutions over clever ones. We're not trying to reinvent the wheel — check for existing tools/APIs/libraries before building something from scratch.
- If you (Claude) make a nontrivial decision on the human's behalf while they're away, log it in `docs/decisions.md` so teammates aren't surprised later.
- Keep the human in the loop before pushing something that touches shared infrastructure (deploy configs, shared API keys, anything teammates are actively building on top of).

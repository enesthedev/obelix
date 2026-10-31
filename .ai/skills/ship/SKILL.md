---
name: ship
description: "Finishes the current work: checks, simplifies, makes atomic commits and writes the PR title and description to a file. Use when the user says ship, wrap it up, finish this, or asks to commit and prepare a PR. Never pushes."
---

# Ship

Being asked to ship is being asked to commit. It is not being asked to push.

1. Read `git status` and the full diff against the base branch. Leave out files that aren't part of this work, and name them in the summary.
2. Run `vendor/bin/pint --dirty --format agent`, `npm run check:fix` and `composer ci:check`. Fix what this work broke. If something unrelated fails, stop and report it with the output.
3. Simplify this work only: remove dead code, needless abstractions and duplication of what the repo already has. Use a simplify skill if you have one. Don't change behavior.
4. Run `composer ci:check` again.
5. Commit in atomic Conventional Commits. If the user's own instructions name a commit command, use it. No AI attribution. Never use `--no-verify`.
6. Write the PR title and body to a Markdown file in a temporary directory outside the repo, in English. Follow the repo's PR template if there is one, otherwise use Summary, Changes, Testing and Out of Scope. Put the title and the body in separate `markdown` code blocks. State only what the diff and the checks support.
7. Reply in the user's language with the commits, the check result and a clickable absolute path to the PR file. Don't push.

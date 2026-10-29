# Obelix

Obelix is a Laravel boilerplate for building products with AI agents: one solid base, one set of rules every agent follows, kept up to date with the official Laravel React starter kit.

These rules win over the generic guidelines below when they conflict.

## Project

- Stack: Laravel 13, PHP 8.4, Fortify, Inertia 3, React 19, TypeScript, Tailwind CSS 4, Wayfinder, Pest 5, Vite+. SQLite by default.
- Commands: `composer setup` installs everything, `composer dev` runs the app, `composer ci:check` is the gate every change must pass, `npm run check:fix` formats the frontend.
- UI: primitives live in `resources/js/components/ui`, app components in `resources/js/components`, shells in `resources/js/layouts`, pages in `resources/js/pages`, design tokens in `resources/css/app.css`.
- Upstream: `.github/starter-kit-upstream` holds the last reviewed starter kit commit. When porting upstream changes, update it in the same commit.
- `vite` is an alias of `vite-plus-core`. Change it only together with `vite-plus`, following the starter kit.

## Worktrees

- For parallel work run `bin/worktree create <branch> [base]`. It creates `.worktrees/<branch>` with its own dependencies, `.env` and SQLite database. `bin/worktree remove <branch>` removes it and keeps the branch.

## Agent files

- `AGENTS.md` is generated. Edit `.ai/guidelines`, then run `php artisan boost:update` and commit both.
- Project skills live in `.ai/skills`. The copies in agent directories are generated.

## Language

- Always reply in the language the user writes in, including questions and summaries. Follow them when they switch.
- Write code, comments, file names, commit messages, rules and plans in English.
- Write UI text in the application's locale.

## Scope

- Change exactly what was asked. Never restyle, move, rename or "improve" something next to it. Suggest it instead.
- When asked for a report, options or a plan, deliver that and wait before changing code.
- Finish an approved plan completely. Say plainly what was skipped.

## UI

- Before UI work read `DESIGN.md` if it exists, and use the design skills available to you without being reminded.
- For a new screen or a redesign with no set direction, agree on the direction before building it.
- Reuse existing components and their variants before writing new ones.
- Use design tokens (`bg-background`, `text-muted-foreground`), not raw palette or hex classes.
- App pages are full width and compact. Auth and reading pages may be narrow.
- Every screen works on mobile and has loading, empty and error states.

## Verification

- Verify with tests, checks and builds. Visual sign-off belongs to the user.
- Don't open a browser, take screenshots, record videos or start the dev server unless asked.

## Git

- Commit only when asked. Push only when asked.
- Commits are atomic Conventional Commits (`feat:`, `fix:`, `docs:`), each passing the checks.
- No AI attribution in commits, pull requests or comments: no co-author trailers, no "Generated with" lines.

## Dependencies

- Use npm. Don't introduce another lockfile.
- Before hand-writing an integration look for a maintained package, and ask before adding it.

<p align="center">
    <picture>
        <source media="(prefers-color-scheme: dark)" srcset=".github/assets/logo-dark.svg">
        <img src=".github/assets/logo-light.svg" alt="Obelix" width="280">
    </picture>
</p>

<p align="center">
    A Laravel boilerplate for building with AI agents: one solid base, one set of rules, always up to date.
</p>

## What you get

- **A current stack:** Laravel 13, PHP 8.4, Inertia 3, React 19, TypeScript, Tailwind CSS 4, Pest 5 and Vite+.
- **Auth:** registration, password reset, email verification, two-factor authentication and passkeys.
- **Rules from the first prompt:** [Laravel Boost](https://laravel.com/docs/boost) turns the project rules into instructions and skills for Claude Code, Codex, Amp, Factory and Grok.
- **Your language:** agents reply in the language you write in. Code stays in English.
- **Clean history:** commits with AI attribution are rejected locally and in CI.

A dashboard theme and a component set are on the way.

## Getting started

You need PHP 8.4, Composer, Node.js 22, npm and Git 2.31 or newer.

```bash
git clone https://github.com/enesthedev/obelix.git my-app
cd my-app
composer setup
composer dev
```

`composer setup` installs dependencies, creates the database, generates the agent files and turns on the Git hook.

## Working with agents

| To                         | Do                                                                   |
| -------------------------- | -------------------------------------------------------------------- |
| Change a rule              | Edit `.ai/guidelines`, then run `php artisan boost:update`           |
| Add a skill                | Create `.ai/skills/<name>/SKILL.md`, then run the same command       |
| Finish a piece of work     | Ask your agent to `ship`: checks, commits and a PR text, no push     |
| Work on tasks side by side | `bin/worktree create <branch>`, later `bin/worktree remove <branch>` |
| Check everything           | `composer ci:check`                                                  |

`AGENTS.md` is generated, so don't edit it by hand.

## Staying up to date

Dependabot proposes Composer and npm updates every day. A daily workflow in this repository opens an issue when the official [Laravel React starter kit](https://github.com/laravel/react-starter-kit) changes. Nothing is merged automatically.

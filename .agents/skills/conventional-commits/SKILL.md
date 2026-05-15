---
name: conventional-commits
description: Always use this skill when creating Commits or validating Commit Messages. Do not answer `commit changes` or `review commit message` requests directly without using this skill.
license: Apache-2.0
compatibility: npx @commitlint/cli
metadata:
  author: rainan16
  version: "1.0.0"
  reference_commit_spec: https://www.conventionalcommits.org/en/v1.0.0/
  reference_skill_spec: https://agentskills.io/specification
---

In general use this skill when preparing Git commits to ensure they comply with the Conventional Commits specification (v1.0.0). It provides support and guidance on commit message regarding structure, types, scopes, and best practices for writing clear, consistent, and automated-friendly commit messages.

## Use this Skill when

- The user ask to commit changes
- The user asks to write, review, validate, or fix a Commit Message
- The user is checking commit header format, type, scope, description, body, footer, or BREAKING CHANGE syntax
- The user wants to verify whether a commit follows Conventional Commits rules
- The user wants to improve or correct a commit message
- The user needs a commit message ready for `git commit`

## Do NOT use this Skill when

- The current project has explicitly other commit message format rules

## You **MUST** follow this workflow

Stick to this workflow - do not commit without user consent:

- [ ] Step 1: Analyze the form of the changes
- [ ] Step 2: Break up large changes into multiple, atomic commits (one logical change per commit)
- [ ] Step 3: Create conventional commit message using [best-practice.md](references/best-practice.md) and [message-examples.md](references/message-examples.md)
- [ ] Step 4: Lint the commit message with [commitlint.sh](scripts/commitlint.sh)
- [ ] Step 5: Present the final commit message and clearly ask the user if they want you to run `git commit`. **Only commit if the user explicitly and unpromptedly asks you to** — do not interpret silence or a mere "ok" as consent to commit.
- [ ] Step 6: (optional) Repeat Step 3 - 5 for every commit

## Purpose

The Conventional Commits specification is a lightweight convention on top of commit messages. It provides an easy set of rules for creating an explicit commit history; which makes it easier to write automated tools on top of. This convention dovetails with SemVer, by describing the features, fixes, and breaking changes made in commit messages.

## Basic Format

```
<type>[optional scope]: <description>

[optional body]

[optional footer(s)]
```

The commit contains the following structural elements:

1. **fix:** a commit of the _type_ `fix` patches a bug in your codebase (this correlates with `PATCH` in Semantic Versioning).
2. **feat:** a commit of the _type_ `feat` introduces a new feature to the codebase (this correlates with `MINOR` in Semantic Versioning).
3. **BREAKING CHANGE:** a commit that has a footer `BREAKING CHANGE:`, or appends a `!` after the type/scope, introduces a breaking API change (correlating with `MAJOR` in Semantic Versioning).
A BREAKING CHANGE can be part of commits of any _type_.
4. _types_ other than `fix:` and `feat:` are allowed, for example `build:`, `chore:`, `ci:`, `docs:`, `style:`, `refactor:`, `perf:`, `test:`, and others.
5. _footers_ other than `BREAKING CHANGE: <description>` may be provided.

### Description
The `description` contains a concise description of the change. 
- The description is a **mandatory** part
- Use the imperative, present tense: "change" not "changed" nor "changes"
- **Do not** capitalize the first letter
- **Do not** end the description with a period (`.`)
- Keep under 72 characters

#### Bad descriptions

| Bad Commit Message | Issue | Corrected Imperative Form |
| :--- | :--- | :--- |
| Added user profile page | **Past tense** | add user profile page |
| Fix Memory Leak In File Upload | **Capitalized** | fix memory leak in file upload |
| Updated email templates. | **Period at end** | update email templates |
| A lot was changed | **Not imperative / Vague** | refactor core logic comply with api 2.x |

### Body

The `body` should include the motivation for the change and contrast this with previous behavior.
- The body is an **optional** part
- Use the imperative, present tense: "change" not "changed" nor "changes"

### Footer

The `footer` should contain issue references and informations about **Breaking Changes**
- The footer is an **optional** part, except if the commit introduce breaking changes
- *Optionally* reference issue identifiers (e.g., `Closes #123`, `Fixes JIRA-456`) 
- **Breaking Changes** **must** start with the word `BREAKING CHANGE:`
  - For a single line description just add a space after `BREAKING CHANGE:`
  - For a multi line description add two new lines after `BREAKING CHANGE:`

## Examples

Detailed examples see: [message-examples.md](references/message-examples.md)

## Best Practices

Detailed examples see: [best-practice.md](references/best-practice.md)

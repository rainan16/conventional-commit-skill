# AGENTS.md — conventional-commit-skill

## Intent

`conventional-commits` is a skill at [`.agents/skills/conventional-commits/SKILL.md`](.agents/skills/conventional-commits/SKILL.md) that helps OpenCode/Claude generate and validate Conventional Commit messages (v1.0.0).

## Validation

```bash
npx -y skills-ref validate ./.agents/skills/conventional-commits
```

## Hooks & CI

- `.husky/pre-commit` — runs `skills-ref validate` on the skill
- `.husky/commit-msg` — runs `commitlint --edit` to enforce Conventional Commits
- `.github/workflows/commitlint.yml` — CI validation on push/PR

Enable hooks locally:

```bash
npm install && npm run prepare
```

Local commitlint quick-check (last 10 commits):

```bash
npx -y @commitlint/cli @commitlint/config-conventional --from=HEAD~10 --to=HEAD
```

## SKILL.md development guidelines

- Keep under 500 lines / 5000 tokens
- Review changes against [best-practices](https://agentskills.io/skill-creation/best-practices) and [optimizing-descriptions](https://agentskills.io/skill-creation/optimizing-descriptions)
- See [troubleshooting](https://code.claude.com/docs/en/skills#troubleshooting) for trigger issues

## Evaluation (before committing changes)

Run three checks before committing skill changes:

| # | Check | Target |
|---|-------|--------|
| 1 | `npx -y skills-ref validate ./.agents/skills/conventional-commits` | pass |
| 2 | **Behavioral evals** — 11 prompts in `.agents/skills/conventional-commits/evals.json`, run with-skill vs without-skill using `skill-creator` | 100% with-skill pass rate, no regression in discriminating evals (Eval 3: breaking-change, Eval 4: review) |
| 3 | **Trigger evals** — 22 queries in `trigger-evals.json` using `skill-evaluator` subagent | 100% accuracy |

An agent proposing a commit **MUST** inform the user these evals exist and ask if they want them run before proceeding.

## References

- [OpenCode skills](https://opencode.ai/docs/skills/)
- [Agent Skills spec](https://agentskills.io/specification)
- [Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0/)
- [skill-creator](.opencode/skills/skill-creator/SKILL.md) — local skill for running evaluations
- [skill-evaluator](.opencode/agents/skill-evaluator.md) — subagent for trigger/optimization tasks

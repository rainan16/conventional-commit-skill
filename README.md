# Conventional Commits Skill

AI skill for generating and validating Git commits per the [Conventional Commits specification](https://www.conventionalcommits.org/en/v1.0.0/).

**Location:** `.agents/skills/conventional-commits/SKILL.md`

## Setup

Enable pre-commit and commit-msg hooks:

```bash
npm install && npm run prepare
```

Validate the skill:

```bash
npx -y skills-ref validate ./.agents/skills/conventional-commits
```

## Usage

**Claude/Claudecode:**
```
Using conventional-commits skill: generate a commit message for user authentication updates
```

**GitHub Copilot (VS Code):**
```
@github.copilot using conventional-commits skill: suggest a commit message
```

**OpenCode Skills:**
```yaml
# In config
skills:
  - path: /path/to/conventional-commit-skill/.agents/skills/conventional-commits
```
```
Using conventional-commits skill: generate a commit message for API improvements
```

## References

- [Conventional Commits Spec](https://www.conventionalcommits.org/en/v1.0.0/)
- [Agent Skills Spec](https://agentskills.io/specification)
- [commitlint](https://commitlint.js.org/)

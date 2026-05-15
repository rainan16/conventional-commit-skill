# Best Practices

Each commit should address a single change in the code, keeping the scope of the commit limited to one task or issue. Additionally, commit messages should be written in the present tense to reflect what the commit is doing at the time of submission.

## GOOD

- ✅ Be specific
- ✅ Use present tense imperative mood ("change" not "changed")
- ✅ Keep first line under 72 characters when possible 
- ✅ Aim for max 50 characters in first line
- ✅ Reference issues in footer + explain "why" in body, not "what"
- ✅ Break up large changes into multiple, atomic commits (one logical change per commit)

## BAD

- ❌ Use vague descriptions ("fix stuff", "updates") 
- ❌ Combine multiple unrelated changes in one commit 
- ❌ Capitalize first letter of description 
- ❌ End description with period 
- ❌ Use past tense ("added", "fixed") 
- ❌ Commit broken parts (goal: each commit should work)
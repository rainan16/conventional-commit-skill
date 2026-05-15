
# Examples

## Basic examples

### Using description and breaking change footer
```
feat: allow provided config object to extend other configs

BREAKING CHANGE: `extends` key in config file is now used for extending other config files
```

### Using `!` to draw attention to breaking change
```
feat!: send an email to the customer when a product is shipped
```

### Using scope and `!` to draw attention to breaking change
```
feat(api)!: send an email to the customer when a product is shipped
```

### Using both `!` and BREAKING CHANGE footer
```
feat!: drop support for Node 6

BREAKING CHANGE: use JavaScript features not available in Node 6.
```

### Using without body
```
docs: correct spelling of CHANGELOG
```

### Using scope
```
feat(lang): add Polish language
```

### Using multi-paragraph body and multiple footers
```
fix: prevent racing of requests

Introduce a request id and a reference to latest request. Dismiss
incoming responses other than from latest request.

Remove timeouts which were used to mitigate the racing issue but are
obsolete now.

Reviewed-by: Z
Refs: 123
```

## Other Examples

### Changes that neither fixes a bug nor adds a feature
```
refactor: extract user validation to service object
```

### Changes to other than code
```
chore(deps): update node from 7.1.0 to 7.2.0
```

### Changes to CI configuration
```
ci: add security scanning to GitHub Actions
```

## Scope examples

`auth` - Authentication/Authorization
`api` - API endpoints
`ui` - User interface
`db` - Database
`deps` - Dependencies
`config` - Configuration changes
`docs` - Documentation
`ci` - CI / CD changes
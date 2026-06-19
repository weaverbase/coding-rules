# Docker Compose Files

Docker Compose files should follow the current Compose Specification and use
readable mapping syntax where practical.

## Rules

1. Do not include the top-level `version` property in Compose files. It is
   obsolete in modern Docker Compose.
2. Prefer mapping syntax for environment variables and labels: `KEY: value`.
3. Avoid list syntax for environment variables and labels unless there is a
   specific compatibility, passthrough, or legacy reason.
4. Quote environment values that may be interpreted by YAML as booleans,
   numbers, or null, such as `"true"`, `"false"`, `"123"`, or `"null"`.

## Examples

Good: environment variables and labels use mapping syntax.

```yaml
services:
  app:
    environment:
      DATABASE_URL: postgres://localhost/db
      DEBUG: "true"
      RETRY_COUNT: "3"
    labels:
      com.example.description: "My application"
      com.example.version: "1.0"
```

Bad: obsolete `version`, list syntax without a compatibility reason, and
unquoted YAML-sensitive values add ambiguity.

```yaml
version: "3.9"

services:
  app:
    environment:
      - "DATABASE_URL=postgres://localhost/db"
      - DEBUG=true
      - RETRY_COUNT=3
    labels:
      - "com.example.description=My application"
      - "com.example.version=1.0"
```

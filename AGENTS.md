# Coding Rules

Use these reusable rules when writing, reviewing, or modifying code. Read the
docs that apply to the current task before making changes:

- `docs/service-first-architecture.md` - keep business logic reusable and
  interfaces thin.
- `docs/data-shapes-validation.md` - define data shape and validation together.
- `docs/naming.md` - name concepts by intent, not by technical container.
- `docs/docker-compose.md` - use Docker Compose v2 conventions.

## Core Defaults

- Keep business logic callable from CLI, API, UI, and background jobs.
- Use strict types and structured result types instead of raw untyped objects.
- Validate inputs at boundaries and avoid leaking sensitive details in errors.
- Keep functions small, focused, and named for what they do.
- Add or update focused tests when behavior changes.


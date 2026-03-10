# Spec Kit Workflows

TDD is enforced in all workflows. Tests are always generated and run automatically — no manual test writing needed.

---

## 1. New Project

> Starting from scratch. No existing code.

```
specify init project-name --ai claude
```

```mermaid
flowchart LR
    A[constitution] --> B[specify] --> C[plan] --> D[tasks] --> E[implement\n+ TDD]
```

Optional: `/speckit.clarify` after specify, `/speckit.analyze` after tasks.

---

## 2. Existing Project

> Adding features to an existing codebase — small or large.

```
specify init . --here --ai claude
```

**Simple ticket** — clear scope, no planning needed:

```mermaid
flowchart LR
    A[tasks] --> B[implement + TDD]
```

**Epic ticket** — multiple stories, needs full planning:

```mermaid
flowchart LR
    A[specify] --> B[plan] --> C[tasks] --> D[implement + TDD]
```

Optional: `/speckit.clarify` after specify, `/speckit.analyze` after tasks.

---

## Quick Reference

| Scenario | Flow | Effort |
|---|---|---|
| New Project | constitution → specify → plan → tasks → implement + TDD | Hours–Days |
| Simple Ticket | tasks → implement + TDD | Minutes–Hours |
| Epic Ticket | specify → plan → tasks → implement + TDD (phased) | Days–Weeks |

Every `/speckit.implement` run writes tests first (Red), implements until they pass (Green), then refactors. No manual test setup required.

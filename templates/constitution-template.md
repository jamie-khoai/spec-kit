# [PROJECT_NAME] Constitution

## Core Principles

### I. Code Quality

Clean, maintainable, well-structured code. DRY, SOLID, and KISS principles enforced. No dead code, no magic numbers, meaningful naming conventions. All code MUST pass linting and formatting checks before merge.

- Functions MUST have a single responsibility
- Maximum cyclomatic complexity: 10 per function
- All public APIs MUST be documented
- Code reviews MUST verify adherence to these standards

### II. Test-Driven Development (NON-NEGOTIABLE for testable code)

**Models, logic, services, APIs:** TDD mandatory. Tests written FIRST → verified to FAIL → implement until tests pass → refactor. Red-Green-Refactor cycle strictly enforced.

- Unit tests for all business logic, models, ViewModels, repositories
- Integration tests for service boundaries and API contracts
- Contract tests for inter-service communication
- No implementation code without a corresponding failing test first for testable units

**Mobile / UI (when unit tests don't fit):** Spec-first acceptable. Define acceptance criteria or expected behavior BEFORE implementation. Verify with snapshot, UI, or E2E tests after implementation. Models and ViewModels still follow full TDD.

### III. User Experience Consistency

All user-facing interfaces MUST follow consistent design patterns, accessibility standards (WCAG 2.1 AA minimum), and responsive design principles.

- UI components MUST be reusable and documented
- Error states, loading states, and empty states MUST be handled gracefully
- Consistent typography, spacing, and color usage enforced via design tokens
- User feedback (toasts, modals, inline messages) MUST follow a single pattern

### IV. Performance Requirements

Applications MUST meet performance budgets. Performance regression testing required.

- Page load: under 3 seconds (LCP)
- API response: under 500ms for standard operations
- Lazy loading, caching, and optimization strategies MUST be applied where applicable
- Bundle size budgets MUST be defined and enforced
- Database queries MUST be optimized (no N+1, proper indexing)

### V. Security & Reliability

Input validation on all boundaries. No secrets in code. Dependency vulnerabilities MUST be addressed promptly.

- Error handling MUST be comprehensive with structured logging
- All external inputs MUST be validated and sanitized
- Dependencies MUST be audited for known vulnerabilities
- Sensitive data MUST be encrypted at rest and in transit
- Start simple, YAGNI principles — complexity MUST be justified

## Quality Gates

- All CI checks MUST pass before merge
- Code coverage MUST not decrease below threshold
- No critical or high-severity linting warnings allowed
- Performance benchmarks MUST not regress
- Security scans MUST pass with no critical findings

## Development Workflow

- Feature branches from main, merged via pull request
- All PRs require at least one code review approval
- Tests MUST pass in CI before merge is allowed
- Commits follow conventional commit format
- Documentation updated with every feature change

## Governance

This constitution supersedes all other development practices. Amendments require:
1. Written proposal with rationale
2. Impact assessment on existing codebase
3. Team review and approval
4. Migration plan for affected code

All PRs and code reviews MUST verify compliance with these principles. Complexity MUST be justified with documented rationale.

**Version**: [CONSTITUTION_VERSION] | **Ratified**: [RATIFICATION_DATE] | **Last Amended**: [LAST_AMENDED_DATE]


# Testing Strategy

## 1. Purpose

Ensure AI-generated and human-written code meets
functional, security, and reliability requirements.

Tests must provide independent evidence of correctness.

## 2. Testing Principles

- Test observable behavior, not implementation details.
- Prefer deterministic and repeatable tests.
- Keep tests isolated from production systems.
- Mock external services when appropriate.
- Test meaningful failure scenarios.
- Add regression tests for confirmed bugs.
- Do not weaken tests to make CI pass.

## 3. Test Levels

### Unit Tests
Verify individual functions and components.

### Integration Tests
Verify interactions between system components.

### Contract Tests
Verify API schemas, data formats, and interfaces.

### End-to-End Tests
Verify critical user journeys.

### Security Tests
Verify authorization, input validation, and
other relevant security controls.

### Regression Tests
Prevent previously fixed bugs from returning.

## 4. AI-Generated Code Requirements

Agents must:
1. Identify test cases from acceptance criteria.
2. Implement or update relevant tests.
3. Include normal, boundary, and failure cases.
4. Execute applicable tests.
5. Report actual results and limitations.

Tests must not rely solely on the agent's claim
that its implementation is correct.

## 5. Test Environments

- Use isolated test environments.
- Never run destructive tests against production.
- Use synthetic or approved test data.
- Never expose credentials in test output.
- Make external API tests opt-in unless suitable
  isolated test credentials are available.

## 6. Pull Request Quality Gates

Before merge:
- Required unit tests must pass.
- Relevant integration tests must pass.
- Formatting and lint checks must pass.
- Type checks must pass where applicable.
- Required security checks must pass.
- Critical acceptance criteria must be verified.
- A reviewer must approve according to branch rules.

## 7. Test Reporting

Every implementation handoff must state:
- Tests added or modified.
- Commands executed.
- Passing and failing checks.
- Tests not executed and why.
- Known risks or coverage gaps.

## 8. Coverage

Coverage is a diagnostic metric, not proof of quality.

Projects may define risk-based coverage thresholds.
Critical business logic and security-sensitive paths
require stronger test evidence.

Do not add meaningless tests solely to increase coverage.

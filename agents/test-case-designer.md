# Test Case Designer

## Purpose

Turn approved requirements into clear test cases that are easy to review and execute.

## What this agent does
- Designs tests using equivalence partitioning
- Applies boundary value analysis where relevant
- Uses decision tables and state-transition testing when useful
- Covers positive, negative, and regression scenarios

## When to use
- Requirements are ready for test design
- You need structured test cases
- You want coverage across normal and edge conditions

## Expected output
A table with:
- Test ID
- Requirement reference
- Priority
- Preconditions
- Test data
- Steps
- Expected result
- Test level
- Automation suitability

## Prompt
```text
Design tests for the supplied feature.

Apply equivalence partitioning, boundary value analysis, decision tables,
and state-transition testing where appropriate. Explain which techniques are
relevant rather than forcing every technique onto every requirement.

Cover:
- Core user journeys.
- Negative and validation scenarios.
- Boundaries and business-rule combinations.
- Relevant permissions and state changes.
- Regression risks.

Return a table with:
Test ID | Requirement reference | Priority | Preconditions |
Test data | Steps | Expected result | Test level |
Automation suitability

Keep cases distinct and actionable. Expected results must come from
requirements; label unresolved expectations as needing clarification.
Identify any important requirements with no corresponding tests.
```

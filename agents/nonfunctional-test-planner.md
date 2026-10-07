# Nonfunctional Test Planner

## Purpose

Help you plan accessibility, performance, reliability, or security testing.

## What this agent does
- Identifies risks and scope for quality attributes
- Suggests suitable tools and methods
- Defines evidence and metrics to collect
- Helps frame measurable targets

## When to use
- You need nonfunctional test coverage
- You are planning quality attribute testing
- You want to assess performance, reliability, accessibility, or security

## Expected output
- Risks and testing scope
- Methods and tools
- Environment and data requirements
- Scenarios, measurements, and evidence
- Proposed thresholds
- Manual review needs and tool limitations

## Prompt
```text
Plan testing for the selected quality attribute:
[ACCESSIBILITY / PERFORMANCE / RELIABILITY / SECURITY]

Identify missing measurable targets before proposing pass/fail criteria.

Return:
- Risks and testing scope.
- Suitable methods and tools.
- Environment and data requirements.
- Scenarios, measurements, and evidence to collect.
- Proposed thresholds, clearly labeled if not approved.
- Manual review needs and tool limitations.

For accessibility, distinguish automated checks from keyboard,
screen-reader, and human evaluation.

For performance, specify workload assumptions and latency percentiles.
For security, restrict testing to explicitly authorized targets.
For reliability, specify recovery expectations and safe failure injection.

Do not claim compliance, security, or production capacity from an
AI review or automated scan alone.
```

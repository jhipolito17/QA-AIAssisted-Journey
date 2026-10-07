# API and Contract Tester

## Purpose
Create an API test plan from contracts and business rules.

## What this agent does
- Reviews API behavior from contracts or documentation
- Checks status codes and schemas
- Validates inputs, auth, pagination, sorting, and errors
- Identifies contract gaps and consumer risks

## When to use
- You are testing APIs or integrations
- You need contract-based validation
- You want structured API test planning

## Expected output
1. Contract gaps and clarification questions
2. Prioritized test matrix with expected outcomes and sources
3. Synthetic request examples
4. Candidates for automated contract and integration tests

## Prompt
```text
Create an API test plan from the supplied contract and business rules.

Where applicable, cover:
- Status codes and response schemas.
- Required, optional, malformed, and boundary-value inputs.
- Authentication and object-level authorization.
- Pagination, filtering, and sorting.
- Error response consistency.
- Idempotency, retries, and duplicate requests.
- Rate limits and concurrency.
- Compatibility with consumers.

Return:
1. Contract gaps and clarification questions.
2. Prioritized test matrix with expected outcomes and sources.
3. Synthetic request examples.
4. Suitable candidates for automated contract and integration tests.

Do not assume undocumented behavior. Do not send requests or perform
load testing without permission and an approved environment.
```

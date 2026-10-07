# QA AI Best Practices

This document summarizes best practices for using AI in Software QA.

## Core Principles

### 1. Do not invent facts
AI should never invent:
- Requirements
- Test results
- Logs
- Defect causes
- Coverage claims

### 2. Keep human review in the loop
AI can help with analysis and drafting, but a human QA engineer should:
- Review all outputs
- Validate test expectations
- Approve final decisions

### 3. Use risk-based testing
Prioritize tests by:
- Business impact
- Failure likelihood
- Change risk
- User frequency

### 4. Separate facts from assumptions
Clearly label:
- Observed facts
- Assumptions
- Questions
- Recommendations

### 5. Use synthetic or masked data
Never share:
- Secrets
- Personal data
- Production customer records
- Credentials

### 6. Prefer repeatable outputs
Prompts should produce:
- Structured tables
- Clear priorities
- Reproducible test cases
- Explicit uncertainties

### 7. Match the test level to the goal
Use the lowest effective level:
- Unit tests for logic
- Integration tests for interfaces
- API tests for contracts
- UI tests for user flows

### 8. Focus on quality attributes
Do not test only functionality. Also consider:
- Accessibility
- Performance
- Reliability
- Security
- Maintainability

## Suggested QA Workflow

Requirements → Risk Analysis → Test Design → Human Review → Execution → Defect Investigation → Release Assessment

## Good Prompting Habits

- Give the AI enough context
- Ask for structured output
- Include constraints and environment details
- Ask it to call out ambiguity
- Review all generated test cases before use

## What AI Should Not Do

- Approve releases
- Confirm bugs without evidence
- Claim execution results it did not observe
- Override your QA judgment

## Recommended First Use Cases

If you are new to AI in QA, start with:
1. Requirements and Risk Analyst
2. Test Case Designer
3. Defect Triage and Investigation Assistant

## Final Reminder

AI is most useful when it helps you think faster and document better.
It is not a substitute for QA expertise.

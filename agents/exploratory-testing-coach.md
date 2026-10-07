# Exploratory Testing Coach

## Purpose
Suggest time-boxed exploratory testing charters and observation points.

## What this agent does
- Helps uncover issues beyond scripted test cases
- Suggests exploration paths and variations
- Identifies failure conditions and recovery paths
- Supports session-based exploratory testing

## When to use
- You want to discover issues beyond scripted testing
- The feature is risky, new, or complex
- You need exploratory test ideas

## Expected output
- Time-boxed charters
- Exploration paths
- Useful variations and failure conditions
- Evidence to capture
- Stop conditions

## Prompt
```text
Create time-boxed exploratory testing charters for this feature.

For each charter provide:
- Mission and risk being investigated.
- Setup and synthetic data.
- Suggested exploration paths.
- Useful variations and failure conditions.
- Observable signals and potential test oracles.
- Evidence to capture.
- Stop conditions.

Prioritize unusual sequences, interrupted workflows, state transitions,
recovery, and realistic user behavior.

Also provide a session-notes template separating observations,
questions, suspected defects, and confirmed defects.

Do not claim exploration was performed.
```

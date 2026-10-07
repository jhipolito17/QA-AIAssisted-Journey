# QA AI-Assisted Journey

Practical AI agent prompts and workflows for Software QA Engineers.
AI assists with analysis and drafting. Humans own all decisions, approvals, and final artifacts.

---

## Table of Contents

- [Purpose](#purpose)
- [Who This Is For](#who-this-is-for)
- [Repository Structure](#repository-structure)
- [Mandatory Guardrails](#mandatory-guardrails)
- [Role Clarity — What AI Does vs What You Own](#role-clarity)
- [When AI Must Stop and Ask](#when-ai-must-stop-and-ask)
- [Output Status Labels](#output-status-labels)
- [Agent Selection Guide](#agent-selection-guide)
- [Recommended Workflow](#recommended-workflow)
- [How to Use These Prompts](#how-to-use-these-prompts)
- [Sensitive Domain Rules](#sensitive-domain-rules)
- [Audit Trail](#audit-trail)
- [What AI Must Not Do](#what-ai-must-not-do)
- [Full Best Practices](#full-best-practices)

---

## Purpose

Help QA teams use AI responsibly to:
- Review requirements and surface gaps before testing begins
- Design structured, traceable test cases
- Plan nonfunctional coverage (accessibility, performance, reliability, security)
- Support exploratory testing with time-boxed charters
- Draft and plan API contract tests
- Investigate defects and structure bug reports
- Assess release readiness based on evidence

---

## Who This Is For

Software QA Engineers who want to use AI to work faster and document better —
without giving up control over quality decisions.

No AI experience required. Start with the [Recommended Workflow](#recommended-workflow).

---

## Repository Structure

```
README.md                              — this file; start here
best-practices.md                      — full principles, guardrails, and rules
agents/
  requirements-risk-analyst.md         — review requirements; find gaps, risks, conflicts
  test-case-designer.md                — turn approved requirements into test cases
  exploratory-testing-coach.md         — generate time-boxed charters and session notes
  test-automation-engineer.md          — automate approved scenarios in your stack
  api-contract-tester.md               — plan contract and integration tests
  defect-triage-investigation-assistant.md  — investigate failures and draft bug reports
  nonfunctional-test-planner.md        — plan accessibility, performance, reliability, security testing
  release-quality-advisor.md           — summarize evidence and residual risk for release
```

---

## Mandatory Guardrails

These rules apply to every agent in this repository, in every context.

| ID   | Rule |
|------|------|
| G-1  | Do not invent requirements, acceptance criteria, or stakeholder decisions |
| G-2  | Do not resolve conflicting requirements; surface the conflict and name the decision owner |
| G-3  | Do not confirm a defect without observable evidence |
| G-4  | Do not silently expand or narrow scope beyond what was supplied |
| G-5  | Do not assign approval to a test case, requirement, or release |
| G-6  | Do not include PII, PHI, credentials, or production records in any output |
| G-7  | Do not treat draft or proposed criteria as approved |
| G-8  | Do not claim tests were executed or coverage achieved from design alone |
| G-9  | Do not invent numeric scores, SLAs, or thresholds unless explicitly supplied |
| G-10 | Do not make compliance, policy, legal, or risk-acceptance decisions |

Full definitions and context: [best-practices.md](best-practices.md#mandatory-guardrails)

---

## Role Clarity

| AI assists with | You own |
|-----------------|---------|
| Drafting test cases from supplied requirements | Reviewing and approving test cases |
| Surfacing risks, gaps, and open questions | Deciding which risks to accept or escalate |
| Suggesting exploration paths and charters | Running exploratory sessions and capturing evidence |
| Structuring defect investigations | Confirming defect classification and severity |
| Summarizing test evidence and residual risk | Signing off on release readiness |
| Proposing acceptance criteria | Approving or rejecting proposed criteria |
| Flagging requirement conflicts | Resolving conflicts with stakeholders |

**AI is never the final approver. Every output is a draft until you review it.**

---

## When AI Must Stop and Ask

Any agent must stop and request clarification when:

- Requirements are contradictory and resolution affects scope or test design
- No approved acceptance criteria exist for the feature under test
- A compliance, legal, or regulatory determination is needed
- The task requires access to production data, credentials, or sensitive records
- Scope is ambiguous enough that different interpretations produce significantly different outputs
- The supplied context is too incomplete to produce a traceable artifact

**Rule:** A clearly scoped partial output is better than a fabricated complete one.

---

## Output Status Labels

Every AI-generated artifact should carry one of these labels until approved:

| Label | Meaning |
|-------|---------|
| `[AI DRAFT]` | Generated by AI, not yet reviewed |
| `[UNDER REVIEW]` | Being reviewed by a QA Engineer |
| `[APPROVED]` | Reviewed and signed off by a QA Engineer |
| `[BLOCKED]` | Waiting on clarification or missing information |

Remove the label only after a QA Engineer has reviewed and approved the content.

---

## Agent Selection Guide

| I need to… | Use this agent |
|------------|---------------|
| Review requirements before testing | [Requirements and Risk Analyst](agents/requirements-risk-analyst.md) |
| Turn requirements into test cases | [Test Case Designer](agents/test-case-designer.md) |
| Find edge cases scripted tests might miss | [Exploratory Testing Coach](agents/exploratory-testing-coach.md) |
| Automate test scenarios in my stack | [Test Automation Engineer](agents/test-automation-engineer.md) |
| Plan API or integration tests | [API and Contract Tester](agents/api-contract-tester.md) |
| Investigate a failure or write a bug report | [Defect Triage and Investigation Assistant](agents/defect-triage-investigation-assistant.md) |
| Plan accessibility, performance, or security tests | [Nonfunctional Test Planner](agents/nonfunctional-test-planner.md) |
| Summarize test status for a release decision | [Release Quality Advisor](agents/release-quality-advisor.md) |

**When not to use AI:**
- When you do not have enough approved requirements to trace outputs to
- When the feature involves sensitive client data and no masked alternative exists
- When you need a final compliance or legal determination
- When execution evidence, not analysis, is what the situation requires

---

## Recommended Workflow

```
Requirements → Risk Analysis → Test Design → Human Review → Execution → Defect Investigation → Release Assessment
```

At every stage:
1. Supply only approved, real context — no invented requirements
2. Label all outputs: fact / inference / assumption / open question
3. Human sign-off before advancing to the next stage

---

## How to Use These Prompts

Each agent file in `agents/` contains:
- **Purpose** — what the agent helps you accomplish
- **What this agent does** — specific capabilities
- **When to use** — the right moment to use it in your workflow
- **Guardrails** — which mandatory rules (G-1 through G-10) apply, and escalation triggers
- **Expected output** — what a complete, usable response looks like
- **Prompt** — the text to paste into your AI tool with your context

**Steps:**
1. Open the relevant agent file.
2. Read the guardrails and expected output sections.
3. Copy the prompt text.
4. Paste it into your AI tool, followed by your actual context (requirements, logs, contract, etc.).
5. Review the output against the [Output Validation Checklist](best-practices.md#output-validation-checklist).
6. Label the output `[AI DRAFT]` and route it for QA Engineer review before use.

---

## Sensitive Domain Rules

When working on systems that handle case data, client information, or legally sensitive workflows:

- Use clearly synthetic data in all prompts and outputs — never real case details
- Never include real case numbers, client names, or legal classifications
- Do not make eligibility, compliance, or case-outcome determinations
- Escalate to a domain expert before designing tests that touch confidential records
- Flag any test scenario that could expose or infer client identity, even indirectly
- Apply extra scrutiny to any assumption that touches privacy or disclosure

---

## Audit Trail

Track AI-assisted work so it can be reviewed, corrected, or explained later:

- Note which agent prompt was used and when
- Keep the original AI output alongside the reviewed version
- Record who reviewed and approved each artifact
- Link outputs to the requirement IDs or sources they were derived from
- Do not replace reviewed artifacts with new AI-generated drafts without re-review

---

## What AI Must Not Do

- Approve releases or sign off on quality gates
- Confirm defects without observable evidence
- Claim execution results it did not observe
- Override QA Engineer judgment
- Resolve conflicting requirements or stakeholder decisions
- Invent thresholds, SLAs, or compliance requirements
- Include real user or client data in any output
- Treat draft documents or proposed criteria as approved
- Make legal, policy, or compliance decisions
- Silently change, expand, or narrow scope

---

## Full Best Practices

For the complete principles, guardrail definitions, escalation rules, prompting guidance,
and sensitive domain rules, see [best-practices.md](best-practices.md).

# QA AI Best Practices

This document defines principles, guardrails, and rules for using AI responsibly in Software QA.
Apply these to every AI-assisted task: test design, risk analysis, defect investigation, and release assessment.

---

## Core Principles

### 1. Never invent facts
AI must not fabricate:
- Requirements or acceptance criteria
- Test results or execution logs
- Defect causes or root analyses
- Coverage claims or metrics
- Stakeholder intent or approvals

**Rule:** If it was not supplied, label it as an assumption or open question — never state it as fact.

### 2. Keep human review in the loop
AI assists; humans decide. A QA Engineer must:
- Review all generated outputs before use
- Validate test expectations against approved requirements
- Approve final decisions on scope, risk, and release
- Own requirement conflicts and ambiguity resolution

**Rule:** AI must never act as a final approver on any testing artifact.

### 3. Use risk-based testing
Prioritize by:
- Business impact and user frequency
- Failure likelihood
- Change exposure and regression risk
- Regulatory or compliance sensitivity

**Rule:** Priority ratings must include a stated rationale. Do not assign numeric scores unless the team has defined a rating scale.

### 4. Separate facts from assumptions
Label every finding as one of:
- **Documented fact** — present in supplied sources
- **Inference** — derived from supplied context
- **Assumption** — not in sources, stated as provisional
- **Open question** — needs human resolution before proceeding

**Rule:** Never convert an assumption into a requirement without explicit human approval.

### 5. Use synthetic or masked data
Never use or include:
- Secrets, credentials, API keys
- Personal data (PII or PHI)
- Production customer records
- Real case, client, or legal information

**Rule:** All examples, test data, and outputs must use synthetic or masked data only.

### 6. Prefer repeatable, structured outputs
Outputs should be:
- Structured tables with explicit columns
- Clearly stating priority and rationale
- Reproducible test cases with setup, steps, expected result, and cleanup
- Explicit about uncertainties and open questions

**Rule:** Avoid free-form prose where structured output is possible and reviewable.

### 7. Match test level to goal
Use the lowest effective test level:
- Unit tests for logic and algorithms
- Integration tests for module interfaces
- API tests for service contracts
- UI/E2E tests for user flows

**Rule:** Do not create UI tests for things that can be covered at a lower level.

### 8. Cover quality attributes beyond functionality
Every test plan must consider:
- Accessibility (WCAG compliance)
- Performance and load tolerance
- Reliability and error recovery
- Security (input validation, auth, data exposure)
- Maintainability of tests themselves

**Rule:** A test plan that addresses only functional behavior is incomplete.

---

## Mandatory Guardrails

These rules are non-negotiable. AI must comply in all contexts.

| ID   | Rule |
|------|------|
| G-1  | Do not invent requirements, acceptance criteria, or stakeholder decisions |
| G-2  | Do not resolve conflicting requirements; surface the conflict and identify the decision owner |
| G-3  | Do not confirm a defect without observable evidence |
| G-4  | Do not silently expand or narrow scope beyond what was supplied |
| G-5  | Do not assign approval to a test case, requirement, or release |
| G-6  | Do not include PII, PHI, credentials, or production records in any output |
| G-7  | Do not treat draft or proposed criteria as approved |
| G-8  | Do not claim tests were executed or coverage achieved from test design alone |
| G-9  | Do not invent numeric scores, SLAs, or thresholds unless explicitly supplied |
| G-10 | Do not make compliance, policy, legal, or risk-acceptance decisions |

---

## When AI Must Stop and Ask

Stop and request human clarification before proceeding when:
- Requirements are contradictory and resolution affects test design
- Scope is ambiguous enough that different interpretations produce significantly different outputs
- No approved acceptance criteria exist for the feature under test
- The task requires access to production data, credentials, or sensitive records
- A compliance, legal, or regulatory decision is required
- The supplied context is insufficient to produce a traceable output

**Rule:** A clearly scoped partial output is better than a fabricated complete one.
Surface the gap explicitly rather than filling it in.

---

## Scope Management Rules

- Work only within the supplied scope. Do not assume adjacent features are in scope.
- If a risk or gap falls outside scope, flag it — do not silently include or exclude it.
- Scope changes require human confirmation before proceeding.
- Every output must clearly label what is in scope, out of scope, and deferred.

---

## Traceability Rules

Every test case and risk finding must be traceable to:
- A named, identified source (requirement ID, user story, acceptance criterion)
- A clear rationale for its inclusion or exclusion

If no requirement ID exists, assign a temporary label (e.g., REQ-TEMP-1) and state it is provisional.
Do not use unlabeled sources or reference requirements by description alone.

---

## Output Validation Checklist

Before submitting AI-generated outputs for human review, confirm:

- [ ] All findings reference a supplied source
- [ ] Facts, inferences, assumptions, and questions are clearly labeled
- [ ] No PII, PHI, credentials, or production data appear in examples
- [ ] Conflicts and open questions are identified, not silently resolved
- [ ] Priority ratings include rationale
- [ ] Test cases include setup, steps, expected result, and cleanup
- [ ] Non-functional quality attributes are addressed or explicitly excluded with reason
- [ ] Coverage gaps are stated explicitly
- [ ] No execution results are claimed from design alone
- [ ] Scope boundaries are clearly stated

---

## Suggested QA Workflow

```
Requirements → Risk Analysis → Test Design → Human Review → Execution → Defect Investigation → Release Assessment
```

At each stage, apply:
1. Supplied context only — no invented requirements or results
2. Labeled outputs — fact / inference / assumption / question
3. Human sign-off before advancing to the next stage

---

## Sensitive Domain Rules

When working on systems that handle case data, client information, or legally sensitive workflows:

- Apply extra scrutiny to any assumption that touches privacy, disclosure, or case outcomes
- Escalate to a domain expert before designing tests that interact with confidential records
- Treat all example data as potentially sensitive; use clearly synthetic values only
- Never include real case numbers, client names, or legal classifications in prompts or outputs
- Flag any test scenario that could expose or infer client identity, even indirectly
- Do not make determinations about legal eligibility, compliance status, or case outcomes

---

## Good Prompting Habits

- Provide the requirement source and its approval status (draft, approved, proposed)
- Specify scope boundaries and what is explicitly out of scope
- Supply the team's rating scales and priority definitions if they exist
- Ask AI to label outputs as fact, inference, assumption, or question
- Ask AI to surface gaps, conflicts, and open questions — not resolve them
- Request structured output (tables, numbered lists) over prose
- Include environment constraints (platform, browser, accessibility standards)
- Review all generated artifacts before use — treat them as a draft, not a deliverable

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

## Recommended Starting Points

If you are new to AI-assisted QA, start here in order:

1. **Requirements and Risk Analyst** — Review requirements and surface gaps before designing tests
2. **Test Case Designer** — Turn approved requirements into structured, traceable test cases
3. **Defect Triage and Investigation Assistant** — Structure and investigate a defect before filing

---

## Final Reminder

AI accelerates analysis and documentation. It does not replace QA expertise, human judgment, or stakeholder decisions.
Every AI output is a draft until a QA Engineer reviews and approves it.

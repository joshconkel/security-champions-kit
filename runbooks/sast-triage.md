# Playbook: SAST Triage

## Purpose

Static Application Security Testing (SAST) scanners analyze source code for security vulnerabilities without executing it. They are powerful but noisy — false positive rates of 30–70% are common, and scanners frequently surface findings that are technically accurate but contextually irrelevant.

This playbook gives champions a repeatable process for triaging SAST output: confirming real vulnerabilities, dismissing false positives with documented rationale, and escalating findings that require Security team judgment.

---

## Who This Is For

| Belt | Role |
|---|---|
| 🟡 Yellow | Triage low severity findings with Security team guidance |
| 🟢 Green | Own triage of low and medium findings within team scope |
| 🔵 Blue+ | Own triage for a product area; validate complex findings; mentor others |

---

## Understanding SAST Output

Before triaging, understand what your scanner is telling you.

### Anatomy of a Finding

| Field | What It Means |
|---|---|
| **Rule ID / CWE** | The vulnerability class being flagged (e.g., CWE-89 SQL Injection) |
| **Severity** | Scanner's assessment of impact: Critical, High, Medium, Low, Informational |
| **File and line** | Where in the code the finding was detected |
| **Sink** | The dangerous function or operation the scanner identified |
| **Source** | Where the data entering the sink originates |
| **Data flow** | The path data takes from source to sink |
| **Message** | The scanner's explanation of the finding |

**The most important thing to understand:** SAST scanners flag potential vulnerability patterns. They do not know whether user-controlled data actually reaches the sink in your runtime environment, whether existing sanitization is sufficient, or whether the code path is even reachable. Your job as a champion is to make that determination.

---

## Triage Decision Framework

Every finding gets one of five dispositions:

| Disposition | Meaning |
|---|---|
| **Confirmed** | Real vulnerability, exploitable or likely exploitable in context |
| **False Positive** | Scanner flagged a pattern that is not actually vulnerable in context |
| **Accepted Risk** | Real finding, but risk is accepted with documented rationale and owner |
| **Not Applicable** | Finding is technically valid but the code path is never reached in production |
| **Escalate** | Finding requires Security team judgment — complexity, severity, or uncertainty too high |

Every disposition requires a comment. "False positive" with no explanation is not an acceptable closure. Future engineers (and auditors) need to understand why.

---

## Step-by-Step Triage Process

### Step 1: Understand the Finding Class

Before looking at code, understand what the scanner is flagging. If you are unfamiliar with the vulnerability class:

- Look up the CWE at cwe.mitre.org
- Review the OWASP page for the relevant Top 10 category
- Use AI to explain the finding type (see AI Augmentation section)

You cannot triage a finding you do not understand. Do not guess.

---

### Step 2: Read the Code in Context

Navigate to the flagged file and read the code in context — not just the flagged line. Understand:

- What is this code doing?
- Where does the input come from? Is it user-controlled?
- Does the data flow from a user-controlled source to the flagged sink?
- Is there sanitization, validation, or encoding between the source and the sink?
- Is this code path reachable in production?

SAST scanners often flag patterns inside dead code, test utilities, or code paths that require authentication contexts that prevent exploitation. Read before deciding.

---

### Step 3: Trace the Data Flow

Follow the data from where it enters the system to where the scanner flagged it.

Key questions:
- **Source control:** Is the input from a user request, an internal system, a config file, or a hardcoded value? User-controlled inputs are higher risk than internal ones.
- **Sanitization:** Is the input validated, escaped, or parameterized before it reaches the sink? Is the sanitization correct for the sink type (e.g., HTML encoding for HTML output, parameterized queries for SQL)?
- **Authentication:** Is this code path only reachable by authenticated users? Authenticated-only paths are lower priority than unauthenticated ones — but they are not zero risk.
- **Scope of impact:** If exploited, what data or systems are affected?

---

### Step 4: Reproduce or Validate (for Confirmed Findings)

For findings you believe are real, attempt to confirm exploitability:

- Construct a test input that follows the data flow path
- Verify the output or behavior matches what you would expect from exploitation
- Note whether the path requires specific conditions (authentication, specific parameters, race conditions)

You do not need to produce a fully weaponized exploit. You need enough confidence to say "this is real and here is why" in your triage note.

---

### Step 5: Document Your Disposition

Every finding closure requires a triage note. Use this format:

```
Disposition: [Confirmed / False Positive / Accepted Risk / Not Applicable / Escalate]

Summary: [One sentence describing the finding]

Analysis: [2–5 sentences explaining your reasoning. Include:
- Whether user-controlled input reaches the sink
- What sanitization or controls exist
- Why this is or is not exploitable in context]

Recommendation: [What should happen next — fix, suppress, accept, escalate]

Ticket: [Link if a remediation ticket was created]
```

---

### Step 6: Create Remediation Tickets for Confirmed Findings

For confirmed findings, create a ticket before closing the scanner finding. Include:

- Finding description in plain language (not scanner output verbatim)
- Severity and priority
- File, line, and function affected
- Recommended fix with code example if possible
- Link back to the scanner finding

---

## Common False Positive Patterns

These patterns frequently produce false positives across common SAST tools. They still require documented rationale when dismissed.

| Pattern | Why It's Often a False Positive | What to Verify |
|---|---|---|
| SQL query flagged in ORM layer | ORM handles parameterization automatically | Confirm the ORM is actually using parameterized queries, not string interpolation |
| XSS flagged on server-rendered output | Framework auto-escapes template variables | Confirm the template engine is escaping and no `raw` or `safe` filters are applied |
| Path traversal on read-only resource | Path is not user-controlled | Confirm the path is constructed entirely from constants or validated values |
| Hardcoded credential in test file | Test credentials are not production credentials | Confirm the credentials are not shared with any production system |
| Deserialization flagged in internal service | Input is not attacker-controlled | Confirm the data source is a trusted internal system with no user input path |
| Cryptographic weakness in legacy module | Module is not used in security-sensitive context | Confirm the cryptographic operation does not protect sensitive data or authentication |

---

## Severity Triage Guidelines

Use these as starting points — always adjust based on context.

| Scanner Severity | Triage Priority | Champion Action |
|---|---|---|
| Critical | Immediate | Same-day review; escalate to Security team within 24 hours if confirmed |
| High | High | Review within current sprint; escalate if confirmed and no clear remediation |
| Medium | Normal | Review within current sprint; create remediation ticket if confirmed |
| Low | Normal | Batch review; suppress with documentation if false positive |
| Informational | Low | Review in bulk; suppress non-actionable findings with documented rationale |

**Do not suppress findings in bulk without review.** Bulk suppression defeats the purpose of scanning and creates audit risk. Each suppressed finding needs individual rationale.

---

## AI Augmentation

AI is highly effective at accelerating SAST triage, particularly for explaining findings, assessing data flows, and drafting triage notes.

### Understanding a Finding

Paste the scanner output and ask:

> "Explain this SAST finding in plain language: [paste finding]. What vulnerability class is this, what conditions are required for exploitation, and what does a correct fix look like?"

This is especially useful for unfamiliar CWEs or complex vulnerability classes.

### Assessing Data Flow

Paste the flagged code and surrounding context:

> "Here is the code flagged by our SAST scanner for [vulnerability type]: [paste code]. Trace whether user-controlled data can reach the flagged sink and whether the existing sanitization is sufficient. Is this likely a true positive or false positive?"

Review the response critically — AI does not have full knowledge of your runtime environment and may miss framework-level mitigations or application-specific context.

### Generating Fix Recommendations

> "Here is a confirmed [vulnerability type] finding in [language]: [paste code]. Provide a corrected version of this code that remediates the vulnerability without changing the intended functionality."

Always review AI-generated fixes before committing. Test them. Do not commit code you do not understand.

### Drafting Triage Notes

> "Based on this analysis: [paste your notes], draft a triage note for this finding in a format suitable for a security tracking system."

### Bulk Triage Assistance

For large scanner outputs, paste a batch of findings and ask:

> "Here are 20 SAST findings from our scanner output. For each, assess whether it is likely a true positive or false positive based on the finding description alone, and suggest a triage priority. Flag any that should be escalated."

Use this as a first-pass prioritization only. Every finding still requires individual human review before closure.

### AI-Specific Vulnerability Patterns

If your codebase includes AI or LLM integration, common SAST tools may not detect AI-specific vulnerabilities. Supplement your review with targeted prompts:

> "Review this code that passes user input to an LLM API: [paste code]. Identify prompt injection risks, insecure output handling issues, and any other AI-specific security concerns."

> "This code uses LLM-generated content in a downstream system: [paste code]. What output validation or sanitization is missing?"

---

## Escalation Criteria

Escalate to the Security team if:

- A Critical or High finding is confirmed with a clear exploitation path
- You cannot determine whether a finding is a true or false positive after reasonable review
- A finding involves authentication, authorization, or session management logic
- A finding is in a shared library or component used across multiple teams
- A finding appears to be exploited or correlated with anomalous behavior
- The recommended fix would require significant architectural changes

---

## Triage Checklist

```markdown
## SAST Triage: [Finding ID / Rule]

**Tool:** 
**Finding Class (CWE):** 
**Severity:** 
**File:** 
**Champion:** 
**Date:** 

### Triage Steps
- [ ] Understood the vulnerability class (CWE reviewed)
- [ ] Read the flagged code in full context
- [ ] Traced the data flow from source to sink
- [ ] Assessed whether input is user-controlled
- [ ] Assessed whether sanitization is present and correct
- [ ] Assessed whether code path is reachable in production

### Disposition
- [ ] Confirmed — remediation ticket created: [link]
- [ ] False Positive — rationale documented below
- [ ] Accepted Risk — rationale and owner documented below
- [ ] Not Applicable — rationale documented below
- [ ] Escalated to Security team

### Rationale
[Required for all dispositions]

### Sign-off
**Champion:**
**Reviewed by (if escalated):**
```

---

## Further Reading

- OWASP Code Review Guide
- CWE Top 25 Most Dangerous Software Weaknesses
- NIST SAST Tool Accuracy Standards
- OWASP SAST Tools List for tool-specific documentation
- OWASP Top 10 for LLM Applications (for AI-specific patterns)

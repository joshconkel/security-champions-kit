# Playbook: Risk Acceptance

## Purpose

Not every security finding can be fixed before a feature ships. Not every finding warrants blocking a release. Risk acceptance is the formal process for acknowledging a known security risk, documenting it explicitly, and ensuring the right people own the decision to proceed.

Risk acceptance is not a way to make security findings disappear. It is a governance mechanism to ensure that when risks are carried, they are carried consciously — with named owners, documented rationale, defined expiration, and a remediation plan.

---

## Who This Is For

| Belt | Role |
|---|---|
| 🟢 Green | Identify candidates for risk acceptance; prepare documentation |
| 🔵 Blue | Facilitate the risk acceptance process for their area; make recommendations on acceptance criteria |
| 🟤 Brown+ | Co-own the risk acceptance process with the Security team; advise on organizational risk posture |

Champions do not approve risk acceptance. They prepare documentation, make recommendations, and facilitate the process. Approval authority rests with the Security team and the appropriate business stakeholder based on severity.

---

## When Risk Acceptance Is Appropriate

Risk acceptance is appropriate when:

- A confirmed vulnerability cannot be remediated before a required ship date
- A fix requires architectural changes that span multiple teams or sprints
- The cost or complexity of remediation significantly outweighs the actual risk in context
- A dependency vulnerability has no available patch and no viable alternative
- A finding is valid but affects a low-usage, low-sensitivity code path

Risk acceptance is **not** appropriate when:

- The finding has a clear, low-effort fix that has simply been deprioritized
- The finding affects sensitive or regulated data in a way that violates compliance requirements
- The finding has a known active exploit in the wild
- No one with appropriate authority is willing to sign the acceptance
- The same risk has been accepted previously and not remediated within the agreed window

If a team is using risk acceptance as a routine way to avoid fixing findings, that is a program health signal — not a governance process working correctly.

---

## Approval Authority

Risk acceptance decisions must be made by someone with the authority to own the consequence if the risk materializes. Champions recommend; they do not approve.

| Finding Severity | Minimum Approval Authority |
|---|---|
| Low | Champion + Security team acknowledgment |
| Medium | Security team approval + manager notification |
| High | Security team approval + Director or VP sign-off |
| Critical | Security team approval + VP or above + legal or compliance notification (as applicable) |

If the appropriate approver is unwilling to sign the acceptance, the finding cannot be accepted. It must be fixed or the feature must not ship.

---

## Step-by-Step Process

### Step 1: Confirm the Finding Is Real

Risk acceptance applies only to confirmed findings — not suspected vulnerabilities or scanner output that has not been triaged. Complete the SAST triage or security review process before initiating risk acceptance.

Document your confirmation in the triage notes before proceeding.

---

### Step 2: Assess Why Immediate Remediation Is Not Possible

Be specific and honest. Vague rationale weakens the governance record and makes it harder to defend decisions if the risk materializes.

Acceptable rationale:
- "The fix requires refactoring the authentication layer across three services — estimated 3 sprints of work — and the release cannot be delayed."
- "No patched version of [dependency] exists. The maintainer has acknowledged the CVE and a fix is expected in [timeframe]."
- "The vulnerable code path is only reachable by internal admin users with existing elevated access — exploitation requires prior compromise of an admin account."

Insufficient rationale:
- "We don't have time."
- "It's probably low risk."
- "We'll fix it later."

---

### Step 3: Define the Compensating Controls

For every accepted risk, document what mitigations are in place or will be put in place to reduce the likelihood or impact of exploitation while the finding remains open.

Compensating controls may include:
- Network or access control restrictions limiting exposure
- Monitoring or alerting on relevant behavior
- Feature flagging or rollout restrictions limiting blast radius
- Manual review processes covering the affected path
- Accelerated patching commitment with a defined timeline

A risk acceptance with no compensating controls is a higher bar to approve. Make the case for why none are applicable if that is the situation.

---

### Step 4: Define the Remediation Commitment

Every accepted risk must have:

- A remediation ticket created and assigned
- A target remediation date
- An owner who is accountable for the remediation
- An expiration date for the acceptance itself

Acceptance without a remediation commitment is not risk acceptance — it is risk abandonment. The Security team will not approve acceptances without a documented plan.

**Default expiration windows:**

| Severity | Maximum Acceptance Window |
|---|---|
| Low | 180 days |
| Medium | 90 days |
| High | 30 days |
| Critical | 14 days (exceptional circumstances only) |

Expiration does not mean the finding is automatically remediated. It means the acceptance must be formally reviewed and reapproved, or the finding must be fixed.

---

### Step 5: Route for Approval

Submit the completed risk acceptance form to the Security team. The Security team will:

- Review the documentation for completeness
- Assess the risk in organizational context
- Approve, reject, or request modifications
- Route to additional approvers based on severity
- Record the acceptance in the vulnerability tracking system

Do not proceed with the assumption that the acceptance is approved until you receive explicit confirmation.

---

### Step 6: Track and Remediate

After acceptance is approved:

- Confirm the remediation ticket is active and assigned
- Check in on remediation progress at the midpoint of the acceptance window
- Notify the Security team when remediation is complete for verification and closure
- Do not allow acceptance windows to expire silently — if more time is needed, initiate a renewal before expiration

Champions are responsible for tracking the acceptance and the remediation for their area. The Security team monitors overall risk acceptance posture but does not chase individual remediations.

---

## AI Augmentation

AI is useful for drafting risk acceptance documentation, assessing compensating control options, and preparing the case for the appropriate approver.

### Drafting Risk Acceptance Documentation

> "I need to document a risk acceptance for the following confirmed security finding: [describe finding]. The reason for not remediating immediately is [reason]. Draft a risk acceptance rationale suitable for a formal security governance record."

Review and verify the output carefully — AI-generated risk documentation should reflect your actual context, not a generic template. Do not submit AI-generated content as-is without reviewing every claim.

### Identifying Compensating Controls

> "I have a confirmed [vulnerability type] in [context] that cannot be remediated for [timeframe]. What compensating controls could reduce the likelihood or impact of exploitation while the finding remains open?"

Use the suggestions as a starting point and evaluate each against your actual environment.

### Estimating Risk in Context

> "Help me assess the actual risk level of this finding in context: [describe the finding, the code path, the user population, the data involved, and any existing mitigations]. Is this finding more or less severe than its CVSS score suggests given this context?"

AI context-adjusted risk assessments are useful for building the case to an approver but should not replace Security team judgment.

### Preparing Approver Communication

> "I need to present a risk acceptance decision to a VP who is not technical. The finding is [description], the reason we cannot fix it now is [reason], and the compensating controls are [list]. Draft a one-paragraph summary suitable for a non-technical executive."

---

## Escalation Criteria

Do not attempt risk acceptance and escalate directly to the Security team if:

- The finding is Critical with evidence of active exploitation
- The finding violates a specific regulatory control with no compliance exception process
- No one with appropriate authority is willing to approve the acceptance
- The team has accepted the same risk previously without remediating it in the agreed window
- The finding affects a system in scope for an upcoming audit or certification

---

## Risk Register Maintenance

All accepted risks should be tracked in a central risk register, not just in individual tickets. The risk register enables:

- Portfolio-level visibility into organizational risk posture
- Audit evidence that accepted risks are managed, not ignored
- Early warning when multiple high-severity acceptances are accumulating in a single area
- Tracking of repeated acceptances that signal a systemic problem

Champions contribute to the risk register by keeping their acceptance records current. The Security team owns the register overall.

---

## Risk Acceptance Form Template

```markdown
## Risk Acceptance Request

**Finding ID / Reference:**
**Feature / System Affected:**
**Champion:**
**Date Submitted:**

---

### Finding Summary
**Vulnerability Type:**
**Severity:** Critical / High / Medium / Low
**Description:** [Plain language description of what the vulnerability is and what it could enable if exploited]
**Confirmation:** [How was this confirmed as a real finding — triage notes, security review, penetration test]

---

### Why Immediate Remediation Is Not Possible
[Specific, detailed rationale. Generic answers will result in rejection.]

---

### Risk Assessment in Context
**Attack Vector:** [How would an attacker reach this vulnerability?]
**Authentication Required:** Yes / No / Partial
**User Population Affected:** [Who is exposed if this is exploited?]
**Data at Risk:** [What data could be accessed or affected?]
**Exploitability:** [How difficult is exploitation given the specific context?]
**Adjusted Risk Level:** [Your assessment of actual risk given context — explain if different from scanner severity]

---

### Compensating Controls
[List controls in place or being implemented to reduce likelihood or impact while the finding is open. If none, explain why.]

| Control | Description | Status |
|---|---|---|
| | | |

---

### Remediation Commitment
**Remediation Ticket:** [Link]
**Assigned Owner:**
**Target Remediation Date:**
**Acceptance Expiration Date:** [Must not exceed maximum window for severity]

---

### Approval

**Champion Recommendation:** Accept / Reject
**Champion Signature:**

**Security Team Decision:** Approved / Rejected / Modifications Required
**Security Team Reviewer:**
**Security Team Signature:**
**Date:**

**Business Approver (if required by severity):**
**Business Approver Signature:**
**Date:**

---

### Notes
[Any additional context, conditions of approval, or follow-up actions]
```

---

## Further Reading

- NIST SP 800-30: Guide for Conducting Risk Assessments
- ISO 27001 Risk Treatment and Acceptance
- OWASP Risk Rating Methodology
- FAIR (Factor Analysis of Information Risk) for quantitative risk assessment at higher severity levels

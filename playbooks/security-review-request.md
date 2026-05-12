# Playbook: Security Review Request

## Purpose

A security review is a structured engagement between a product team and the Security team to evaluate the security posture of a feature, service, or change before it ships. Done well, it surfaces risks early, accelerates delivery, and builds trust between security and engineering.

This playbook defines when to request a review, how to prepare for one, and how champions serve as the interface between their team and the Security team throughout the process.

---

## Who This Is For

| Belt | Role |
|---|---|
| 🟡 Yellow | Assist with review preparation; observe the review process |
| 🟢 Green | Own the review request process for their team; lead preparation |
| 🔵 Blue+ | Facilitate lightweight reviews independently; escalate complex cases |

---

## Types of Security Review

Not all security reviews are the same. Match the review type to the scope and risk of the change.

| Review Type | When to Use | Typical Duration | Owner |
|---|---|---|---|
| **Lightweight Champion Review** | Low-to-medium risk changes within champion scope | 1–4 hours | Champion (Green+) |
| **Assisted Review** | Medium risk changes; champion leads with Security team support | Half day | Champion + Security team |
| **Full Security Review** | High risk features, new services, significant architectural changes | 1–3 days | Security team, champion assists |
| **Design Review** | New product capabilities or significant trust boundary changes, reviewed at design stage | Varies | Security team, champion prepares |
| **Penetration Test** | External-facing high-risk features, compliance requirements | External engagement | Security team arranges |

When in doubt about which type applies, ask your champion (Green or above) or open a review request and let the Security team scope it.

---

## When to Request a Security Review

**Always request a review for:**
- New authentication or authorization mechanisms
- Changes to session management
- Features handling sensitive or regulated data (PII, health, financial, credentials)
- New external APIs or significant changes to existing ones
- New third-party integrations
- Features with file upload, download, or processing
- Significant changes to cryptographic implementations
- AI or LLM feature introduction or significant modification
- New services or microservices going to production for the first time

**Consider a review for:**
- Changes to existing access control logic
- New background job or async processing pipelines
- Significant dependency additions in high-risk categories
- New administrative or privileged functionality

**A review is likely not needed for:**
- UI-only changes with no backend impact
- Routine bug fixes with no security-relevant code changes
- Documentation or configuration changes not affecting production systems
- Dependency version bumps (handled via dependency review playbook)

---

## The Champion's Role in Security Reviews

Champions are not passive observers in security reviews. They are the interface between their team and the Security team — and good preparation is their primary contribution.

**Before the review:**
- Complete the Security Review Request form (template below)
- Conduct and document an initial threat model (see threat modeling playbook)
- Identify and triage any existing scanner findings related to the feature
- Gather relevant design documents, architecture diagrams, and data flow information
- Identify the right engineers to include in the review session

**During the review:**
- Facilitate communication between the Security team and the feature engineers
- Take notes on findings and action items
- Clarify engineering context the Security team may not have
- Track questions that require follow-up

**After the review:**
- Create tickets for all identified findings
- Assign owners and target sprint for each item
- Track remediation progress and update the Security team
- Confirm all HIGH and CRITICAL items are resolved before ship gate

---

## Step-by-Step Process

### Step 1: Determine Review Type and Timing

Initiate a security review as early as possible — ideally at design stage for high-risk features. Reviews requested the week before release create bottlenecks and rarely produce good outcomes for either team.

**Target timing by review type:**
- Design review: At feature design or RFC stage, before implementation begins
- Full security review: At least 2–3 sprints before planned ship date
- Assisted review: At least 1 sprint before planned ship date
- Lightweight champion review: Can be completed in the same sprint as final implementation

---

### Step 2: Complete the Review Request

Submit the Security Review Request form to the Security team. A well-prepared request results in a faster, higher-quality review. Incomplete requests get deprioritized.

**The Security team needs to know:**
- What the feature does in plain language
- What data it handles and who can access it
- What changed from the previous state
- What threat modeling has already been done
- What open findings or concerns the team already knows about
- What the ship date constraint is

---

### Step 3: Prepare Supporting Materials

Gather and organize before the review session:

- Architecture or data flow diagram (even a rough one is better than nothing)
- Design document or RFC if one exists
- Links to relevant PRs or branches
- Existing threat model output
- Any open scanner findings related to the feature
- List of questions or areas of uncertainty the team wants addressed

---

### Step 4: Attend and Facilitate the Review Session

In the session:

- Open with the feature walkthrough using your prepared materials
- Walk the Security team through the data flow — do not assume they know the system
- Flag areas where the team already has concerns or open questions
- Capture all findings and action items in real time
- Confirm severity ratings and ship gate implications before the session ends

Do not leave the session without a clear list of: what was found, what the disposition is for each finding, and what needs to happen before the feature can ship.

---

### Step 5: Track and Close Findings

After the session:

- Create a ticket for every finding, linked to the review
- Assign each ticket an owner and a target sprint
- Update the Security team when HIGH and CRITICAL items are resolved for verification
- Do not ship until all ship-blocking items are closed or formally accepted

---

## AI Augmentation

AI accelerates review preparation significantly — particularly for generating documentation, identifying gaps in threat coverage, and drafting finding descriptions.

### Preparing the Review Request

> "I am preparing a security review request for a feature that [description]. Based on this description, what information should I include in the review request to help the Security team conduct an effective review?"

> "Here is a draft of my security review request: [paste draft]. What gaps or missing information might slow down or complicate the review?"

### Accelerating Threat Model Preparation

> "I am preparing a threat model for a feature that [description]. Using STRIDE, identify the most likely threats and generate a draft threat log I can review and refine before the security review session."

See the threat modeling playbook for the full AI-augmented threat modeling process.

### Drafting Finding Descriptions

After the review session, use AI to draft clear, actionable finding tickets:

> "Here are my notes from a security review session: [paste notes]. Draft a finding description for each issue identified, including: what the finding is, why it matters, and a recommended remediation approach."

### AI Feature Review Preparation

For features incorporating AI or LLM components, supplement standard preparation with:

> "I am preparing a security review for a feature that uses an LLM to [description]. What AI-specific security questions should the review cover beyond standard application security concerns?"

> "Review this prompt template used in our LLM feature: [paste template]. Identify prompt injection risks and recommend mitigations."

---

## Escalation and Ship Gate Guidance

### What blocks shipment

The Security team will designate findings as ship-blocking or non-ship-blocking. As a general rule:

| Finding Severity | Default Ship Gate |
|---|---|
| Critical | Ship-blocking unless formally risk-accepted by appropriate authority |
| High | Ship-blocking for external-facing or sensitive data features; risk acceptance may apply |
| Medium | Non-ship-blocking with documented remediation plan and target sprint |
| Low / Informational | Non-ship-blocking; tracked for future remediation |

Champions do not have authority to override ship gate decisions. If a team wants to ship with an open HIGH or CRITICAL finding, that decision must go through the formal risk acceptance process (see risk acceptance playbook).

### Emergency Reviews

If a feature reaches the release sprint without a security review and a review is required, escalate to the Security team immediately. Do not ship without review for required review types. An emergency review is better than a post-release incident.

---

## Security Review Request Template

```markdown
## Security Review Request

**Feature / Change Name:**
**Champion:**
**Feature Owner / Engineering Lead:**
**Requested Review Type:** Lightweight / Assisted / Full / Design
**Target Ship Date:**
**Request Date:**

---

### Feature Description
[Plain language description of what this feature does, who uses it, and why it is being built]

### What Changed
[If this is a modification to an existing feature, describe what changed and what stayed the same]

### Data Handled
- Data types: [PII / credentials / payment / health / internal / other]
- Data sensitivity: [Public / Internal / Confidential / Restricted]
- Data storage: [Where data is stored and how long it is retained]
- Data flows: [How data moves through the system — attach diagram if available]

### Trust Boundaries Affected
[List any new or modified trust boundaries: new external APIs, new third-party integrations, new internal service calls, changes to authentication or authorization]

### Threat Modeling Completed
- [ ] Yes — attach or link threat model output
- [ ] Partial — attach what is available
- [ ] No — reason: [explain]

### Known Concerns or Open Questions
[List anything the team is already uncertain about or concerned about from a security perspective]

### Open Scanner Findings
[List any open SAST, SCA, or DAST findings related to this feature, or confirm none exist]

### Supporting Materials
- Architecture diagram: [link or attach]
- Design document / RFC: [link]
- Relevant PRs or branches: [link]

### Constraints
[Any schedule, compliance, or dependency constraints the Security team should know about]
```

---

## Further Reading

- OWASP Application Security Verification Standard (ASVS) — useful for understanding what security reviews assess
- OWASP Developer Guide — secure design principles
- NIST Secure Software Development Framework (SSDF)
- OWASP Top 10 for LLM Applications — for AI feature reviews

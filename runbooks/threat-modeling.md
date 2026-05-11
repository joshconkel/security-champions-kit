# Playbook: Threat Modeling

## Purpose

Threat modeling is a structured way to identify security risks in a feature or system before code is written. Done early, it prevents costly rework. Done well, it surfaces risks that scanners and code review will never catch because they exist in the design, not the implementation.

This playbook gives champions a practical, lightweight approach to threat modeling that fits inside normal engineering workflows — not a multi-day exercise requiring a security PhD.

---

## Who This Is For

| Belt | Role |
|---|---|
| 🟢 Green | Participate in threat model reviews led by Blue+ or Security team |
| 🔵 Blue | Lead threat model sessions with Security team support |
| 🟤 Brown+ | Facilitate independently; mentor others through the process |

---

## When to Threat Model

Threat model any feature or change that meets one or more of the following criteria:

- Introduces a new authentication or authorization mechanism
- Handles sensitive or regulated data (PII, payment, health, credentials)
- Exposes a new external API or modifies an existing one
- Integrates a new third-party service or dependency
- Changes trust boundaries between services or components
- Introduces AI or ML model inputs, outputs, or pipelines
- Involves file upload, download, or processing
- Modifies access control logic

**When not to threat model:** routine bug fixes, UI-only changes with no backend impact, dependency version bumps with no API changes. Use judgment — when in doubt, a 30-minute lightweight review is always better than skipping entirely.

---

## The STRIDE Framework

STRIDE is the most widely used threat modeling framework for application security. Each letter represents a category of threat.

| Letter | Threat | Question to Ask |
|---|---|---|
| **S** | Spoofing | Can an attacker pretend to be someone they are not? |
| **T** | Tampering | Can an attacker modify data or code they should not be able to? |
| **R** | Repudiation | Can an attacker deny having taken an action? |
| **I** | Information Disclosure | Can an attacker access data they should not be able to? |
| **D** | Denial of Service | Can an attacker degrade or disrupt availability? |
| **E** | Elevation of Privilege | Can an attacker gain access or permissions beyond what they should have? |

You do not need to find threats in every category for every feature. Work through the list, note what applies, and move on from what does not.

---

## Step-by-Step Process

### Step 1: Define the Scope (15 minutes)

Before the session, prepare a one-paragraph description of the feature or change. Answer:
- What does this feature do?
- Who uses it and how do they access it?
- What data does it create, read, update, or delete?
- What external systems or services does it interact with?

This description becomes the starting point for the session and the AI augmentation step below.

---

### Step 2: Draw the Data Flow Diagram (20–30 minutes)

A Data Flow Diagram (DFD) shows how data moves through the system. You do not need a formal tool — a whiteboard sketch or a simple diagram tool works fine.

Include:
- **External entities:** users, third-party services, other systems
- **Processes:** components or services that transform data
- **Data stores:** databases, caches, file systems, queues
- **Data flows:** arrows showing how data moves between components
- **Trust boundaries:** dashed lines showing where data crosses privilege or network boundaries

Trust boundaries are where most interesting threats live. Pay attention to any data flow that crosses one.

---

### Step 3: Identify Threats Using STRIDE (30–45 minutes)

For each data flow and component in your diagram, work through STRIDE. Ask the six questions. For each threat you identify, capture:

- **Threat:** what could go wrong
- **Component:** where it applies
- **Impact:** what happens if this is exploited
- **Existing mitigations:** what already prevents this
- **Gaps:** what is missing

Use the threat log template at the end of this playbook to capture findings.

---

### Step 4: Rate and Prioritize (15 minutes)

Not all threats are equal. Use a simple HIGH / MEDIUM / LOW rating based on:

- **Likelihood:** how realistic is exploitation given your environment and attacker profile?
- **Impact:** what is the blast radius if this is exploited?

| Rating | Criteria |
|---|---|
| HIGH | Realistic exploitation path, significant data or availability impact |
| MEDIUM | Exploitation requires specific conditions, moderate impact |
| LOW | Unlikely exploitation, limited impact, or strong existing mitigations |

Escalate all HIGH threats to the Security team before the feature ships. MEDIUM threats should have a documented mitigation plan. LOW threats should be logged and reviewed at a future date.

---

### Step 5: Document and Assign (15 minutes)

For each unmitigated threat, create a ticket with:
- Threat description
- Affected component
- Recommended mitigation
- Owner
- Target resolution sprint

Attach the threat log to the feature design document or PR. This creates an audit trail and prevents the same threats from being rediscovered in a later review.

---

### Step 6: Review with Security Team

For Blue belts: review your completed threat log with a Security team member before closing the session.
For Brown and Black belts: self-review is acceptable for low-complexity features. Escalate high-complexity or high-risk features regardless of belt level.

---

## AI Augmentation

AI significantly accelerates threat modeling, especially for champions who are still building their threat intuition. Use AI tools to augment — not replace — your own analysis.

### Generating Initial Threat Lists

Paste your Step 1 scope description into an AI assistant with a prompt like:

> "I am building a feature that [description]. Using the STRIDE framework, identify potential security threats for this feature. For each threat, include the threat category, what could go wrong, and a recommended mitigation."

Use the output as a starting checklist — not a final answer. AI-generated threat lists tend to be broad and will include items that do not apply to your specific environment. Review each item critically and remove what does not fit.

### Reviewing Data Flow Diagrams

Describe your DFD in text and ask:

> "Here is a description of how data flows through this feature: [description]. What trust boundaries exist, and where are the highest-risk data flows?"

### Identifying Missed Threats

After completing your own STRIDE analysis, paste your threat log and ask:

> "Here is my threat model for this feature. What threats might I have missed? Focus on [authentication / data handling / API security / supply chain] risks."

### AI-Specific Threat Modeling

If your feature includes AI or ML components, apply additional threat categories beyond STRIDE:

| Threat | Description |
|---|---|
| Prompt Injection | Attacker manipulates model inputs to change model behavior or extract information |
| Training Data Poisoning | Attacker corrupts training data to influence model outputs |
| Model Inversion | Attacker extracts sensitive training data from model outputs |
| Insecure Output Handling | Model output is used in downstream systems without validation or sanitization |
| Excessive Agency | Agentic AI takes actions beyond intended scope due to ambiguous instructions or missing guardrails |
| Supply Chain | Compromised model weights, third-party AI APIs, or ML pipeline dependencies |

For AI features, add a dedicated section to your threat log covering these categories.

---

## Escalation Criteria

Escalate to the Security team immediately if you identify:

- A realistic path to unauthorized access to sensitive or regulated data
- A trust boundary with no authentication or authorization control
- An AI pipeline with user-controlled inputs and no output validation
- Any HIGH-rated threat without an obvious mitigation
- A threat you cannot confidently rate or assess

When in doubt, escalate. The cost of an unnecessary conversation with the Security team is zero. The cost of a missed critical threat is not.

---

## Threat Log Template

```markdown
## Threat Model: [Feature Name]
**Date:** 
**Champion:**
**Security Team Reviewer:**
**Feature Description:**

---

### Data Flow Summary
[Brief description of key components and data flows]

---

### Identified Threats

| ID | Category | Threat Description | Component | Likelihood | Impact | Rating | Existing Mitigations | Gap / Recommendation | Ticket | Owner |
|----|----------|-------------------|-----------|------------|--------|--------|---------------------|----------------------|--------|-------|
| T1 | Spoofing | | | | | | | | | |
| T2 | Tampering | | | | | | | | | |

---

### Open Items
[List any unresolved questions or items requiring Security team input]

### Sign-off
- Champion: 
- Security Team:
- Date:
```

---

## Further Reading

- OWASP Threat Modeling Cheat Sheet
- Microsoft STRIDE Threat Modeling
- OWASP Top 10 for Large Language Model Applications (for AI-specific threat modeling)
- MITRE ATLAS (adversarial threat landscape for AI systems)

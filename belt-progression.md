# Champion Maturity Model: Belt Progression Framework

A structured progression path for Security Champions from initial interest through specialist-level contribution. Each belt represents a meaningful increase in responsibility, autonomy, and organizational impact — not just training completion.

---

## Overview

| Belt | Title | Typical Phase | Focus |
|---|---|---|---|
| ⬜ White | Interested | Pre-program | Exploring security, not yet a formal Champion |
| 🟡 Yellow | Associate Champion | Phase 1 (0–6 months) | Onboarding and probation |
| 🟢 Green | Core Champion | Phase 2 (6–12+ months) | Stable, embedded contributor |
| 🔵 Blue | Advanced Champion | Phase 3 (12–18+ months) | Semi-independent force multiplier |
| 🟤 Brown | Senior Champion / Pod Lead | Phase 3–5 (18–30 months) | Security leadership within pods |
| ⬛ Black | Specialist / Architect Champion | Phase 4–6 (24–36+ months) | Strategic partner and domain specialist |

---

## ⬜ White Belt — Interested

### Identity and Focus
Exploring security with curiosity but not yet a formal Champion. This is the natural feeder stage into the program — engineers who have shown interest and may be good candidates for nomination.

### Key Training Themes
- Security fundamentals: CIA triad, common threat types
- OWASP Top 10 — high-level awareness
- Introduction to the Security Champions program and why it exists

### Core Responsibilities
- Attend an intro session or complete short introductory modules
- Identify where security matters in their team's recent or ongoing work
- Have an initial conversation with their manager about interest in the role

### Recognition
- Acknowledged informally in team channels or 1:1s as "interested in security"
- Considered for nomination to Yellow Belt when cohort slots open

---

### Promotion: White → Yellow

| Criteria Area | Checklist |
|---|---|
| Interest and Mindset | Expressed clear, ongoing interest — not just passing curiosity. Has asked at least one thoughtful security question or raised a security concern in a team context. |
| Foundational Training | Completed basic security awareness module. Completed OWASP Top 10 overview (high-level). Read the Security Champions program overview. |
| Manager Alignment | Discussed interest with their manager. Manager agrees in principle the engineer is a good candidate based on behavior, performance, and peer respect. |
| Fit for Role | Demonstrates curiosity, reliability, and basic communication skills. Not currently on a performance plan or in a role where bandwidth is clearly impossible. |
| Program Decision | Accepted into the next cohort as a Yellow Belt Associate Champion. |

---

## 🟡 Yellow Belt — Associate Champion

### Identity and Focus
Newly onboarded Champion in the probation and onboarding period. Learning to contribute meaningfully without being overwhelmed. The goal is a first real contribution, not comprehensive security knowledge.

### Key Training Themes
- Program and role orientation: time expectations, scope boundaries, manager support structure
- Secure coding basics in primary language or framework
- OWASP Top 10 — developer-level depth
- Security-focused code review basics
- SAST, SCA, and DAST triage 101: what is obviously bad, what to escalate

### Core Responsibilities
- Triage simple scanner findings with Security team guidance
- Submit initial security-focused PR comments or fixes
- Attend monthly Champion meetups
- Create at least one SOP or wiki entry from real work (e.g., "How we fixed X")

### Recognition
- Weekly informal shout-outs in team communication channels
- Included in Security Champion program announcements
- 90-day probation review with manager and Security team

---

### Promotion: Yellow → Green

| Criteria Area | Checklist |
|---|---|
| Training Completion | Completed program and role orientation. Completed secure coding basics in primary language or framework. Completed OWASP Top 10 developer-depth module. Completed code review for security basics. Completed SAST/SCA/DAST triage 101. |
| Applied Practice | Successfully triaged a set of scanner findings with Security team guidance. Submitted several PR comments or fixes that improved security. Created at least one SOP or wiki entry based on real work. |
| Engagement and Reliability | Attended the majority of monthly Champion meetups during probation. Responds reliably in Champion channels when tagged or asked. |
| Manager Feedback | Manager confirms that time spent as a Champion has not materially harmed delivery. Manager confirms the Champion is adding visible value to the team. |
| Security Team Feedback | Security team confirms quality of triage and communication is solid. Viewed as safe to give more responsibility within their domain. |
| Program Decision | 90-day probation review passed. Promoted to Green Belt Core Champion. |

---

## 🟢 Green Belt — Core Champion

### Identity and Focus
Stable, active Champion embedded in their team. This is the **baseline expectation** for the program across engineering — the level at which a Champion is fully contributing and trusted to operate independently on routine work.

### Key Training Themes
- Role-specific advanced modules by function: backend, frontend, mobile, DevOps
- Applied threat modeling basics using lightweight methods on real services
- Triage 201: owning low and medium severity issues within a defined scope
- Hands-on exploit and fix labs that mirror your team's stack

### Core Responsibilities
- Serve as first-line security contact for their service or team
- Own remediation of low and medium severity vulnerabilities in their area
- Introduce "security moments" in retrospectives, planning sessions, or standups
- Contribute reusable patterns and SOPs: secure templates, configuration defaults
- Actively participate in the Champion community channel and share wins

### Recognition
- Featured in quarterly Champion Spotlight newsletters
- Training completion badges and certificates
- Positive manager feedback on impact to delivery quality and security posture

---

### Promotion: Green → Blue

| Criteria Area | Checklist |
|---|---|
| Advanced Training | Completed role-specific advanced modules appropriate to their function. Completed applied threat modeling basics and participated in at least one real threat model review. Completed Triage 201. Completed exploit and fix labs relevant to their stack. |
| Ownership and Impact | Acts as first-line security contact for their service or team without prompting. Regularly leads or drives remediation of low and medium issues without hand-holding. Has demonstrably improved security posture in their area (reduced vuln backlog, improved MTTR). |
| Team Influence | Runs security moments in retrospectives or planning periodically. Provides constructive PR feedback that peers respond to positively. |
| Cross-Team Contribution | Contributed SOPs or reusable patterns used by more than one team or service. |
| Feedback and Reputation | Manager endorses them as the go-to security person for the team. Security team sees them as reliable, thoughtful, and ready for more autonomy. |
| Program Decision | Nominated and accepted as a Blue Belt Advanced Champion. |

---

## 🔵 Blue Belt — Advanced Champion

### Identity and Focus
Semi-independent force multiplier and local security lead. Trusted to own more complex activities and to actively mentor less experienced Champions.

### Key Training Themes
- Advanced threat modeling on higher-risk features and chained issues
- Reproducing and explaining complex findings from penetration tests or bug bounty reports
- Delegated triage ownership: running queues, managing SLAs
- Mentoring skills and running small Champion pods

### Core Responsibilities
- Own first-line triage for a product area — not just a single team
- Lead threat model sessions with Security team support
- Mentor Yellow and Green belts through shadowed reviews, labs, and triage
- Represent their pod in bi-annual Security team and Champion retrospectives

### Recognition
- Quarterly or bi-annual metrics awards: highest vulnerability reduction, best PR reviewer
- Manager and director kudos shared in organizational channels
- Recognized by peers and leaders as the go-to security person for their area

---

### Promotion: Blue → Brown

| Criteria Area | Checklist |
|---|---|
| Leadership Training | Completed security leadership and influence training. Completed metrics and impact communication modules. Completed facilitation and workshop training. |
| Technical and Process Ownership | Consistently owns first-line triage for a product area. Leads multiple threat model sessions with minimal Security team oversight. Has co-designed or significantly improved at least one security process (triage workflow, exception handling, PR checklist). |
| Mentoring and Pod Work | Actively mentors Yellow and Green belts through shadowing and feedback. Runs or co-runs a Champion pod with regular syncs, shared backlog, and shared SOPs. |
| Influence on Teams and Management | Helps managers incorporate security into team OKRs or planning. Trusted by at least one Director or VP as a partner in security discussions. |
| Sustained Performance | Demonstrated sustained impact over multiple quarters — not a one-sprint standout. Strong feedback from Security team and managers in retrospectives. |
| Program Decision | Recognized as Brown Belt Senior Champion and Pod Lead. Reflected in internal career frameworks as a senior-level Champion. |

---

## 🟤 Brown Belt — Senior Champion / Pod Lead

### Identity and Focus
Security leadership within engineering pods. Brown Belts actively co-own process, training, and influence alongside the Security team — they are partners, not just participants.

### Key Training Themes
- Security leadership and influence: using data to shape direction and investment
- Co-designing security processes with the Security team: exceptions, tooling, workflows
- Designing and facilitating internal workshops for engineering audiences
- Communicating impact through MTTR, detection-to-escalation rate, and PR-stage vs. post-release metrics

### Core Responsibilities
- Lead Champion pods: own cadence, agendas, and pod-level security backlog
- Co-own repeatable Security team tasks for their area: triage, basic code review, playbook execution
- Co-create and deliver internal training or lunch-and-learns
- Advise managers on embedding security into team OKRs and delivery planning

### Recognition
- Senior Champion title acknowledged in internal career and capability frameworks
- Present at engineering all-hands or product organization meetings
- Eligible for conference sponsorship, specialized security projects, or stretch assignments

---

### Promotion: Brown → Black

| Criteria Area | Checklist |
|---|---|
| Specialization Training | Completed at least one specialist track: Secure CI/CD and supply chain, API and platform security, Privacy and data protection, or AI and emerging technology security. Completed executive and strategic communication modules. |
| Strategic Impact | Co-owned design of at least one reference architecture or golden path. Played a critical role in design or rollout of key security tooling or automation. Demonstrably shifted Security team workload by absorbing repeatable tasks and preventing issues earlier in the SDLC. |
| Organizational Influence | Regularly consulted by Security leadership on strategy in their specialization area. Presented to senior engineering or security leadership with clear, business-aligned impact. |
| Program and Community Stewardship | Mentors Blue and Brown belts and actively identifies successors. Contributes to evolving the Champion program itself: curriculum, metrics, course correction. |
| Reputation and Longevity | Multi-year track record of high-impact Champion contributions. Recognized by leadership as a core part of the organization's security culture. |
| Program Decision | Formally recognized as Black Belt Specialist / Architect Champion. Reflected in career frameworks with high-visibility recognition. |

---

## ⬛ Black Belt — Specialist / Architect Champion

### Identity and Focus
Deep specialist and strategic partner to the Security team. Black Belts shape reference architectures, automation strategies, and long-term security direction. They are organizational assets, not program participants.

### Key Training Themes
- One or more specialization tracks:
  - Secure CI/CD and supply chain security (SLSA, SBOM, signed builds, policy-as-code)
  - API and platform security (multi-tenant safety, abuse resistance)
  - Privacy by Design and data protection
  - AI and emerging technology security
- Executive and strategic communication: CTO and CISO briefings, business-value framing
- Designing secure reference architectures and golden paths

### Core Responsibilities
- Co-own a specialization area alongside the Security team
- Define and evolve golden paths, secure defaults, and reference designs
- Advise on tooling and automation strategy across engineering
- Mentor Brown and Blue belts and coach engineering leadership on security trade-offs

### Recognition
- Explicitly recognized in career framework as a security leadership path
- Present at executive forums, engineering-wide events, or internal summits
- Eligible for multi-year service awards and executive-level recognition

---

## Using This Framework

**For program managers:** Belt criteria are promotion checklists, not just descriptions. Use them as the basis for structured 90-day reviews and promotion conversations.

**For managers:** Each belt level has explicit manager feedback requirements. Your input is not optional — it is a gate. This protects your team from scope creep and protects the program from advancing Champions who aren't ready.

**For champions:** Progression is based on demonstrated impact, not time served. A Green Belt who consistently delivers will advance faster than a Green Belt who completes training but does not contribute. Belts are earned, not assigned.

**For career framework integration:** Brown and Black belt criteria are intentionally written to align with Staff and Principal-level engineering expectations in most career ladders. Use this language when making the case for formal inclusion in your organization's career framework.

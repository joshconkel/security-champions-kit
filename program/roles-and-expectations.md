# Roles and Expectations

A clear definition of what every participant in the Security Champions program is responsible for — and equally important, what they are not responsible for.

Ambiguity about scope is one of the fastest ways to lose champions, managers, and executive support simultaneously. This document exists to prevent that.

---

## How to Use This Document

- **Champions:** Read this before accepting your nomination. The expectations here are what you are agreeing to.
- **Managers:** Read this before nominating someone. Your responsibilities are defined here too.
- **Security team:** Use this as the baseline for onboarding conversations and 90-day reviews.
- **Executive sponsors:** Use this to set organizational expectations and defend champion time when needed.

---

## The Security Team

The Security team owns the program. That means designing it, running it, adjusting it, and being accountable for its outcomes — not delegating that accountability to champions or managers.

### Responsibilities

**Program Operations**
- Maintain and evolve the program charter, roadmap, and governance model
- Run the recruitment and onboarding process for each cohort
- Facilitate monthly champion meetups and bi-annual retrospectives
- Maintain the champion communication channel and program documentation

**Champion Enablement**
- Deliver foundational and role-specific training content
- Provide guidance and feedback on champion triage outputs, especially in early belts
- Review and approve belt promotion decisions jointly with managers
- Be available as an escalation point for findings outside champion scope

**Metrics and Reporting**
- Track program health metrics and report to executive sponsors monthly
- Collect and act on manager and champion feedback at regular intervals
- Publish quarterly champion spotlights and program updates

**Boundary Holding**
- Protect champions from scope creep — enforce what is and is not a champion responsibility
- Intervene when managers are not honoring time commitments
- Escalate organizational resistance to executive sponsors before it becomes an attrition problem

### What the Security Team Does Not Do

- Use the program to recruit champions into the security org without a separate, transparent process
- Assign champions work that falls outside their defined belt scope without explicit agreement
- Hold champions accountable for metrics they do not control
- Allow the program to become a compliance checkbox or a training catalog with no real delegation

---

## Champions

Champions are security-capable engineers embedded in product teams. They are not junior security analysts, not security gatekeepers, and not responsible for all security outcomes on their team.

### Universal Responsibilities (All Belts)

- Complete training requirements for your current belt level
- Triage scanner findings within your defined scope and severity threshold
- Escalate findings outside your scope or severity threshold to the Security team promptly
- Attend monthly champion meetups
- Participate actively in the champion community channel
- Document recurring patterns and fixes as SOPs for team reuse
- Raise workload or scope concerns to the program owner before they become problems

### Belt-Specific Responsibilities

| Belt | Additional Responsibilities |
|---|---|
| 🟡 Yellow | Submit initial security PR comments and fixes. Create at least one SOP from real work during probation. |
| 🟢 Green | Serve as first-line security contact for your service or team. Own remediation of low and medium findings in your area. Introduce security moments in retrospectives or planning. |
| 🔵 Blue | Own first-line triage for a product area, not just a single team. Lead threat model sessions with Security team support. Mentor Yellow and Green belts. |
| 🟤 Brown | Lead a Champion pod. Co-own repeatable Security team tasks for your area. Co-create and deliver internal training. Advise managers on embedding security into OKRs. |
| ⬛ Black | Co-own a specialization area alongside the Security team. Define golden paths and reference architectures. Advise on tooling and automation strategy. Mentor Brown and Blue belts. |

### What Champions Are Not Responsible For

- Security architecture decisions for new platforms or major infrastructure
- Penetration testing or offensive security activities
- Incident response
- Compliance and audit evidence collection
- Security findings outside their defined scope — escalate, do not attempt
- Covering for an understaffed security team on work that was never part of their role
- Achieving security metrics they do not have the authority or tools to influence

### Champion Rights

Champions have the right to:
- Raise scope or workload concerns without it affecting their standing in the program
- Decline work that falls outside their defined belt responsibilities
- Request additional guidance from the Security team on any finding before acting
- Take a leave of absence from champion duties during high-pressure delivery periods, with advance notice
- Exit the program with appropriate notice without it affecting their employment or performance standing

---

## Managers

Managers are co-owners of the program at the team level. Their commitment is not a formality — it is a structural requirement. Programs that treat manager buy-in as optional consistently fail.

### Responsibilities

**At Nomination**
- Identify candidates who meet the qualification criteria: technical reach, peer respect, intellectual curiosity, and bandwidth to commit
- Discuss the opportunity honestly with the candidate, including time commitment and expectations
- Complete the manager commitment section of the program charter before the champion is onboarded
- Confirm that sprint and delivery commitments can accommodate the champion time investment

**During Active Participation**
- Protect champion time — do not routinely deprioritize champion work when sprint pressure mounts
- Provide required feedback at 30, 60, and 90-day intervals
- Raise concerns about workload or delivery impact to the program owner early, before they result in attrition
- Recognize champion contributions explicitly in team forums, 1:1s, and performance conversations
- Do not assign champions security work outside their defined scope without Security team agreement

**At Promotion or Transition**
- Provide sign-off for belt promotions jointly with the Security team
- When a champion rotates off the team or leaves the program, proactively identify a successor candidate
- Do not use a champion's program participation as justification for transferring them to the security team without a separate, transparent conversation

### What Managers Are Not Expected to Do

- Become security experts or make security decisions on behalf of their team
- Manage the champion's security work directly — that is the Security team's responsibility
- Absorb security team responsibilities that were never part of the champion scope
- Guarantee specific security outcomes from their champion

### Manager Escalation Path

If champion workload is impacting delivery, raise it with the program owner **before** it becomes an attrition event. The program is designed to adjust scope. Losing a champion because the workload was quietly too high is the worst outcome — and the most preventable one.

---

## Directors and VPs

Senior leaders do not run the program, but their visibility and endorsement directly affect its sustainability.

### Responsibilities

- Reinforce the program's legitimacy in organizational forums, planning sessions, and QBRs
- Ensure managers reporting to them understand and honor their commitment obligations
- Review quarterly program health summaries and provide strategic direction when needed
- Recognize champion contributions at the organizational level — not just the team level
- When the program requests integration into career frameworks or OKRs, champion that integration

### What Directors and VPs Should Watch For

- Managers quietly pulling champions back to full delivery work without notice
- Security team scope expanding into champion responsibilities without charter amendment
- Program metrics being used to justify headcount decisions before the program has matured
- Champions being recruited into the security team without manager and HR awareness

---

## Executive Sponsor

The executive sponsor is the program's organizational air cover. They do not manage day-to-day operations but their involvement directly determines how seriously the organization takes the program.

### Responsibilities

- Sign and maintain the program charter
- Review program health metrics monthly and provide strategic direction quarterly
- Participate in all-hands recognition and champion spotlight moments — visibility at this level matters
- Serve as the final escalation point when organizational resistance blocks program progress
- Advocate for career framework integration and budget for recognition and champion development

### Minimum Viable Sponsorship

At minimum, an executive sponsor should be able to answer the following questions at any given time:
- How many champions do we have and what teams are covered?
- What is our current champion retention rate?
- What security workload has the program absorbed from the central team?
- What is the next phase of the program and when do we expect to reach it?

If the sponsor cannot answer these, reporting cadence or content needs to be adjusted.

---

## Scope Boundaries Quick Reference

Use this table to quickly resolve scope questions. When in doubt, escalate to the Security team rather than guess.

| Activity | Champion? | Security Team? | Notes |
|---|---|---|---|
| Low/medium SAST finding triage | ✅ Green+ | Support only | Champion owns within defined scope |
| High/critical finding triage | ❌ | ✅ | Escalate immediately |
| Security-focused PR review | ✅ Green+ | On request | Champion reviews; Security team handles complex cases |
| Threat modeling participation | ✅ Blue+ | ✅ Lead (early phases) | Champions take increasing ownership over time |
| Threat modeling facilitation | ✅ Brown+ | ✅ Support | |
| Incident response | ❌ | ✅ | Never a champion responsibility |
| Penetration testing | ❌ | ✅ | Outside champion scope at all belt levels |
| Security architecture decisions | ✅ Black (advisory) | ✅ Owner | Black belts advise; Security team decides |
| Audit and compliance evidence | ❌ | ✅ | Champions may contribute artifacts but do not own this |
| SOP and pattern creation | ✅ All | Review and publish | Security team reviews before broad distribution |
| New engineer security onboarding | ✅ Green+ | ✅ Program onboarding | Champions support team-level onboarding |

# Security Champions Program Charter

> **How to use this template:** Replace all `[bracketed text]` with your organization's specifics. Sections marked **(Required)** must be completed before recruiting your first champion. Sections marked **(Recommended)** strengthen executive alignment but can be completed after initial approval.

---

## Program Overview (Required)

**Program Name:** Security Champions Program
**Program Owner:** [Name, Title — typically a Security Engineering Manager or Head of Product Security]
**Executive Sponsor:** [Name, Title — ideally CISO, VP Engineering, or CTO]
**Date:** [Charter approval date]
**Review Cadence:** Bi-annual

### Purpose

The Security Champions Program embeds security ownership inside engineering teams by upskilling developers into security-capable contributors. Rather than centralizing all security work in a dedicated security team, this program distributes security knowledge, triage capability, and secure development practices across product engineering.

This charter defines the program's scope, governance, resource commitments, and success criteria.

---

## Problem Statement (Required)

[Customize this section with your organization's specific context. The following is a starting point.]

The current security model places all security responsibility on a central team that cannot scale proportionally with engineering growth. The consequences are:

- Security reviews become a bottleneck at the end of the SDLC, creating delivery risk
- Vulnerability remediation is reactive rather than preventative
- Developers lack practical security guidance at the point of decision
- The security team spends significant time on routine triage that could be handled closer to the code

Previous attempts to address this [include or remove as applicable] either became internal recruiting pipelines for the security team, relied on training without meaningful work delegation, or failed to secure sustained manager commitment. This program is designed around those failure modes explicitly.

---

## Goals and Success Criteria (Required)

### 36-Month Target Outcomes

- Security is embedded in engineering identity — not a gate at the end of delivery
- 70%+ of low and medium severity security triage is handled by champions
- Champion role is recognized in the engineering career framework as a technical leadership path
- Security team capacity is redirected from routine triage to high-risk, high-impact work

### Phase 1 Success Criteria (Months 0–6)

| Metric | Target |
|---|---|
| Manager approval rate | 100% |
| 90-day champion retention | ≥ 80% |
| Low/medium findings triaged by champions | ≥ 40% |
| Manager feedback on workload impact | Net positive |

### Phase 2 Success Criteria (Months 6–12)

| Metric | Target |
|---|---|
| MTTR on champion teams vs. baseline | Improving |
| Champion satisfaction pulse survey | ≥ 70% positive |
| SOP reuse on non-champion teams | Observed |
| Provisional period attrition | < 20% |

*Full metrics framework available in [`metrics/kpi-framework.md`](../metrics/kpi-framework.md).*

---

## Scope (Required)

### In Scope

- Engineering teams building [product / platform / service areas — specify]
- [Number] initial champion cohort covering [number] teams or product areas
- Security triage for SCA, SAST, and DAST scanner outputs within defined severity thresholds
- Code review participation for security-relevant changes
- Threat model participation at the feature and service level

### Out of Scope — Phase 1

- Penetration testing or offensive security activities
- Security architecture decisions for new platforms or major infrastructure changes
- Incident response
- Compliance and audit responsibilities
- Any work currently handled by [list specific security team functions that are not being delegated]

> **Note:** Scope expands deliberately across phases. Champions are not responsible for work outside their defined scope. Any scope expansion requires a charter amendment and manager notification.

---

## Program Design Principles (Required)

**Manager buy-in is a prerequisite, not a courtesy.**
Champions cannot protect their own time. Managers can. No champion is onboarded without explicit manager approval and written commitment.

**Delegation is the point. Training is the prerequisite.**
Champions who train but never do meaningful security work leave within two quarters. Real work is the retention mechanism.

**Start small. Prove value. Then scale.**
Phase 1 targets 10–15 carefully selected champions. Coverage is not the goal. Credibility is.

**Recognition must reach multiple levels.**
Champion recognition matters. Manager and director recognition matters more for program sustainability.

**Course-correct early and explicitly.**
The program will adjust. Adjustment is not failure. Ignoring signals and continuing unchanged is.

---

## Roles and Responsibilities (Required)

### Security Team

| Responsibility | Description |
|---|---|
| Program ownership | Owns charter, roadmap, and program governance |
| Champion onboarding | Delivers orientation, foundational training, and first task guidance |
| Triage guidance | Reviews and provides feedback on champion triage outputs |
| Escalation handling | Handles findings escalated by champions outside their scope |
| Metrics and reporting | Tracks program health and reports to executive sponsor |
| Retrospectives | Facilitates bi-annual program retrospectives with champion input |

### Champions

| Responsibility | Description |
|---|---|
| Triage | First-line review of scanner findings within defined scope and severity |
| Code review | Security-focused review of PRs in their team's codebase |
| SOP creation | Documents recurring security patterns and fixes as reusable guides |
| Community participation | Attends monthly meetups, engages in champion channels |
| Escalation | Escalates findings outside their scope or severity threshold to the Security team |

### Managers

| Responsibility | Description |
|---|---|
| Nomination | Identifies and nominates qualified candidates |
| Time protection | Ensures champion time commitment is honored and not routinely deprioritized |
| Feedback | Provides required feedback at 30, 60, and 90-day intervals |
| Recognition | Actively recognizes champion contributions in team and organizational forums |
| Escalation | Raises workload or scope concerns to program owner before they become attrition risks |

### Executive Sponsor

| Responsibility | Description |
|---|---|
| Organizational air cover | Reinforces program legitimacy at VP and director level |
| Quarterly review | Reviews program health metrics and provides strategic direction |
| Recognition | Participates in all-hands recognition and champion spotlights |
| Escalation path | Available as escalation point if organizational resistance blocks program progress |

---

## Time Commitment (Required)

Transparency about time investment is essential. Surprises on time commitment are one of the fastest ways to lose manager trust.

| Role | Estimated Time Commitment | Notes |
|---|---|---|
| Champion (Yellow/Green) | 2–4 hours per week | Includes triage, training, meetups |
| Champion (Blue/Brown) | 3–5 hours per week | Adds mentoring and pod responsibilities |
| Champion (Black) | 4–6 hours per week | Adds specialization and strategic work |
| Manager | 1–2 hours per month | Feedback, recognition, nomination |
| Security team (per champion) | 1–2 hours per week | Guidance, review, program operations |

> **Important:** These estimates are based on Phase 1 design. Time commitments are reviewed bi-annually and adjusted based on actual data from manager and champion feedback.

---

## Champion Progression (Required)

Champions progress through a six-level belt system tying security contribution directly to career growth:

| Belt | Title | Phase |
|---|---|---|
| ⬜ White | Interested | Pre-program |
| 🟡 Yellow | Associate Champion | Phase 1 |
| 🟢 Green | Core Champion | Phase 2 |
| 🔵 Blue | Advanced Champion | Phase 3 |
| 🟤 Brown | Senior Champion / Pod Lead | Phase 3–5 |
| ⬛ Black | Specialist / Architect Champion | Phase 4–6 |

Promotion criteria for each belt are defined in [`BELT-PROGRESSION.md`](../BELT-PROGRESSION.md). Promotions require both Security team and manager sign-off.

---

## Governance (Required)

### Decision Authority

| Decision | Owner |
|---|---|
| Champion promotion | Security team + manager joint sign-off |
| Champion removal | Security team + manager, with HR notification if performance-related |
| Scope changes | Program owner + executive sponsor |
| Charter amendments | Program owner + executive sponsor |
| Phase advancement | Program owner, based on metrics gate criteria |

### Reporting Cadence

| Report | Audience | Cadence |
|---|---|---|
| Program health metrics | Executive sponsor | Monthly |
| Champion spotlight | Engineering org | Quarterly |
| Manager feedback summary | Directors and VPs | Quarterly |
| Full program retrospective | All stakeholders | Bi-annual |
| Charter review | Executive sponsor | Bi-annual |

### Escalation Path

1. Champion raises concern → Security team program owner
2. Manager raises concern → Security team program owner
3. Unresolved organizational resistance → Executive sponsor
4. Program health metrics in risk signal range → Immediate review meeting with executive sponsor

---

## Manager Commitment (Required)

By nominating a champion, managers agree to the following:

- [ ] I understand and accept the estimated time commitment for my team member
- [ ] I will protect champion time from routine sprint pressure where reasonable
- [ ] I will provide feedback at 30, 60, and 90-day intervals when requested
- [ ] I will not use the Security Champions program as a pathway to transfer this engineer to the security team without a separate, transparent conversation
- [ ] I will raise workload or delivery concerns to the program owner before they result in attrition
- [ ] I will recognize my champion's contributions in performance conversations and team forums

**Manager name:** ___________________________
**Manager signature:** ___________________________
**Date:** ___________________________
**Champion nominated:** ___________________________

---

## Resource Requirements (Recommended)

| Resource | Description | Owner |
|---|---|---|
| Training platform access | [Security Journey / internal LMS / other] | Security team |
| Tooling access | SAST, SCA, DAST scanner read access for champion scope | Security team |
| Communication channel | Dedicated champion Slack or Teams channel | Security team |
| Recognition budget | Badges, certificates, spotlight materials, CTF prizes | [Security / HR / Engineering budget owner] |
| Conference sponsorship | Phase 3+ top champion sponsorship | [Budget owner] |

---

## Risks and Mitigations (Recommended)

| Risk | Likelihood | Mitigation |
|---|---|---|
| Program used as security recruiting pipeline | Medium | Manager commitment form explicitly prohibits this without separate conversation |
| Training without delegation leads to attrition | High | Real triage work delegated from Week 1 of Yellow belt |
| Manager resistance erodes participation | Medium | Manager buy-in required before nomination; escalation path defined |
| Sprint pressure consistently deprioritizes champion work | Medium | 90-day check-in includes explicit workload impact question; scope adjusted if needed |
| Program grows faster than Security team can support | Low–Medium | Phase gates prevent advancement until leading indicators are healthy |
| Recognition fails to reach manager and director level | Medium | Manager kudos templates and director briefing materials provided |

---

## Approval (Required)

This charter is approved by the following stakeholders. Approval indicates agreement with the program's goals, scope, governance model, and resource commitments.

**Program Owner**
Name: ___________________________
Signature: ___________________________
Date: ___________________________

**Executive Sponsor**
Name: ___________________________
Signature: ___________________________
Date: ___________________________

**Engineering Leadership Representative**
Name: ___________________________
Signature: ___________________________
Date: ___________________________

**HR / People Team Representative** *(if champion work is to be reflected in career frameworks)*
Name: ___________________________
Signature: ___________________________
Date: ___________________________

# Security Champions Program Roadmap

A phased 36-month framework for building, scaling, and sustaining a Security Champions program — designed around real failure modes, organizational trust, and durable engineering culture change.

---

## How to Use This Roadmap

This is not a strict timeline. It is a **maturity progression**. Some organizations will move through early phases faster. Others will need to stay in Phase 1 longer to build trust before expanding.

The phases are sequential by design. Skipping Phase 1 to get to scale faster is one of the most common reasons programs fail. Prove value small before expanding wide.

> **Phase gates:** Before advancing to the next phase, confirm that the leading indicators from the current phase are in healthy signal range. Advancing while metrics are in risk signal range will compound problems at scale.

---

## Phase 1: Relaunch and Reestablish (Months 0–6)

**Goal:** Build trust, demonstrate value across stakeholders, and avoid overwhelming participants with training that has no immediate application.

This phase is intentionally small and deliberate. The objective is not coverage — it is credibility.

### Recruitment and Onboarding

- Use a **hybrid recruitment model**: champion interest AND manager approval are both required
- Define clear participant qualification criteria: technical reach, peer respect, intellectual curiosity
- Onboard **10–15 hand-picked champions** across diverse teams who can commit meaningful time
- Secure manager and director alignment through briefing sessions and written commitment before champions are onboarded

### Training

- **Program orientation:** program purpose, role expectations, tooling access
- **Foundational skills:** OWASP Top 10, secure coding basics, code review practices
- **Quick-win tasks:** triage of low and medium severity scanner results (SCA, SAST, DAST)

Training in this phase is always paired with an immediate task to apply it. No training without application.

### Recognition

- Weekly informal shout-outs in team communication channels
- First quarterly Champion Spotlight in a program newsletter
- Program announcement at engineering all-hands

### Engagement

- Monthly champion meetups mixing technical content and community building
- Buddy system pairing new champions with experienced peers
- Champions document their work as SOPs that can be reused across teams

### Metrics

- Track 90-day retention (this is your primary health signal in Phase 1)
- Compare remediated vulnerability counts on champion vs. non-champion teams
- Collect **required** manager feedback on workload impact — if managers are feeling strain, adjust before expanding

> **Phase 1 success criteria before advancing:** Manager approval rate ≥ 90%, 90-day champion retention ≥ 80%, at least 40% of low/medium findings triaged by champions, manager feedback net positive.

---

## Phase 2: Land and Expand (Months 6–12)

**Goal:** Scale coverage, deepen training, and begin shifting repeatable security tasks to champions.

### Recruitment

- Expand cohort to cover all major engineering groups
- Introduce a **90-day provisional period** for new champions before full program membership
- Establish a **multi-tier champion model**: Associate → Champion → Senior Champion

### Training

- Advanced modules differentiated by role: backend, frontend, mobile, DevOps
- Applied projects: threat model review participation, leading a "security moment" at sprint retrospectives
- Hands-on labs: exploit and fix common vulnerability classes

### Recognition

- Quarterly metrics awards: highest vulnerability reduction, best PR reviewer
- Certificates and badges issued on successful completion of the provisional period
- Manager recognition templates provided to directors for broadcasting champion contributions to peers

### Engagement

- Quarterly or bi-annual CTF-style competitions
- Dedicated Security Champions communication channel for sharing wins and asking questions
- Champions begin cross-team sharing of SOPs and secure patterns

### Metrics

- Mean time to remediation (MTTR) and detection-to-escalation rate (DER) on champion-led teams
- Participation rate in training sessions
- Pulse survey on champion satisfaction and workload balance

> **Phase 2 success criteria before advancing:** MTTR improving on champion teams, pulse survey satisfaction ≥ 70%, SOP reuse observed on non-champion teams, provisional attrition < 20%.

---

## Phase 3: Delegate and Accelerate (Months 12–18)

**Goal:** Make champions a trusted, semi-independent security force multiplier. Shift meaningful work out to champions so they feel useful — not just trained for tasks they never apply.

### Recruitment

- Begin **succession planning** for champions who rotate off or leave
- Encourage managers to proactively identify replacement candidates when champions roll off

### Training

- Threat modeling workshops led jointly with the internal security team
- Delegation of first-line triage for SCA, SAST, and DAST scanner outputs
- Specialized training for Senior Champions on reproducing and validating findings
- Senior champions begin mentoring new recruits directly

### Recognition

- Champions showcase at engineering all-hands
- Conference sponsorship or specialized learning opportunities for top performers
- Senior Champion title documented in career framework and aligned to advancement criteria

### Engagement

- Bi-annual retrospectives with champions to adjust scope, workload, and program direction
- **Champion pods** established to facilitate peer networking and distributed coordination

### Metrics

- Security workload reduction on repeatable tasks (target: 20–30%)
- Number of security issues resolved at PR stage vs. post-release
- Champion retention rate at 12 months

> **Phase 3 success criteria before advancing:** 20%+ of repeatable security tasks handled by champions, PR-stage resolution increasing quarter-over-quarter, 12-month retention ≥ 75%, Senior Champions actively mentoring.

---

## Phase 4: Optimize and Specialize (Months 18–24)

**Goal:** Refine the program based on real feedback and offer specialization paths for mid-to-senior champions.

- Introduce **specialization tracks**: Secure CI/CD, API Security, Privacy by Design, Supply Chain Security
- Senior champions lead internal workshops for engineering teams
- Adjust program size based on attrition and demand — scale up or consolidate based on evidence
- Expand recognition to executive-level visibility: CTO and CISO briefings include champion program impact

### Course Correction Levers

| Condition | Response |
|---|---|
| Retention is low | Revisit recognition model, reduce workload expectations |
| Managers pushing back | Integrate champion work explicitly into team OKRs |
| Program too large or unwieldy | Introduce pod leads to distribute coordination |
| Specialization tracks undersubscribed | Survey champions on what tracks would be most valuable |

---

## Phase 5: Institutionalize (Months 24–30)

**Goal:** Make security mindset part of the engineering organization's core identity — not a program people participate in, but a way teams operate by default.

- Embed the champion role in **career frameworks** as an official technical leadership path
- Shift **70% of low and medium-level security work** — triage, simple code reviews — to champions
- Security team pivots to strategic and complex work, with champions handling routine signal
- Internal **annual champions summit** with recognition awards and program retrospective

### Course Correction Levers

| Condition | Response |
|---|---|
| Engineering identity shift stalling | Reinforce through manager communications and all-hands visibility |
| Security team struggling to let go of routine work | Explicit handoff agreements with champion pods |
| Career framework integration blocked by HR | Start with informal recognition; build the evidence case for formal inclusion |

---

## Phase 6: Sustain and Evolve (Months 30–36)

**Goal:** Transition from "program" to an independent function within engineering, with the security team as an equal participant rather than a central gatekeeper.

- Senior champions train and onboard new champions — the security team is no longer the primary onboarding mechanism
- Recognition evolves into **service awards** for champions reaching 2+ years of participation
- Continuous feedback loop: quarterly retrospectives drive ongoing evolution of tasks and scope
- Champions involved in **tooling and process design** for security automation

### Course Correction Levers

| Condition | Response |
|---|---|
| Program stagnates | Refresh with new tracks: AI security, supply chain security, emerging threats |
| Executive interest wanes | Reframe impact in business terms: cost savings, reduced incidents, delivery acceleration |
| Champion community becomes insular | Open community channels to all engineers; use champions as facilitators |
| Succession pipeline drying up | Revisit career framework alignment and make the path more visible to mid-level engineers |

---

## Target Outcomes at 36 Months

- Security is part of the organization's core engineering identity — not a bolt-on gate at the end of the SDLC
- Directors and VPs have fully bought into the program and can articulate its value for product delivery
- Security Champions is a recognized and somewhat prestigious role tied to concrete career growth
- The security team is freed to focus on high-risk, high-impact strategic work

---

## Adapting the Timeline

| Organizational Context | Adjustment |
|---|---|
| Small org (< 200 engineers) | Compress Phases 1–2 into a single 6-month phase; skip multi-tier model initially |
| Large enterprise (> 2000 engineers) | Expect Phase 1 to run longer; introduce pod leads earlier in Phase 2 |
| Rebuilding a failed program | Add a retrospective on the previous failure before launching; communicate changes explicitly to skeptical managers |
| Regulated industry | Align champion triage work to audit-relevant controls from Phase 1; document participation for evidence |
| Low manager trust environment | Stay in Phase 1 longer than the timeline suggests; trust cannot be rushed |

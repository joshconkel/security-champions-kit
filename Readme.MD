# Security Champions Starter Kit

> A practitioner-built framework for embedding security ownership inside engineering teams — designed around what actually causes programs to fail.

---

## Why Most Security Champions Programs Fail

Most organizations have attempted a Security Champions program. Most have failed, been abandoned, or quietly faded out. The failure modes are consistent:

**1. The Recruiting Pipeline Problem**
Security teams use the program to identify and recruit talented engineers into the security org. Managers figure this out quickly. They stop nominating their best people. Participation quietly dies.

**This framework addresses it by:** requiring manager co-ownership from day one. Champions are nominated *with* manager approval and commitment, not extracted from teams without it.

**2. Training Without Work**
Champions complete training modules, earn badges, attend sessions — and then return to their teams with no change in what they actually do. There is nothing to apply the training to. Motivation evaporates within a quarter.

**This framework addresses it by:** delegating real, meaningful security work to champions from Phase 1, scaling in complexity as champions mature. Training is always paired with immediate application.

**3. No Manager Accountability**
The program is treated as an optional extracurricular. Managers support it in theory but never protect champion time or recognize it in performance discussions. Champions deprioritize it when sprint pressure mounts.

**This framework addresses it by:** securing written manager commitment upfront, integrating champion work into team OKRs, and providing managers with templates to recognize and reward their champions visibly.

---

## Who This Is For

- Security engineers and managers building or rebuilding a Security Champions program
- Engineering leaders looking to scale security without scaling headcount
- Organizations that have tried and failed at previous incarnations of this program

---

## What This Is Not

- A compliance checkbox exercise
- A training catalog with a fancy name
- A security team recruiting tool

---

## Framework Overview

This kit provides a **36-month phased roadmap** for building a Security Champions program from scratch or relaunching a failed one. It is structured in six phases, each with explicit goals, activities, and course-correction levers.

| Phase | Timeline | Goal |
|---|---|---|
| 1: Relaunch & Reestablish | Months 0–6 | Build trust, show value, avoid overload |
| 2: Land & Expand | Months 6–12 | Scale coverage, deepen training, delegate tasks |
| 3: Delegate & Accelerate | Months 12–18 | Make champions a semi-independent security force |
| 4: Optimize & Specialize | Months 18–24 | Refine based on feedback, offer specialization paths |
| 5: Institutionalize | Months 24–30 | Embed security into engineering identity |
| 6: Sustain & Evolve | Months 30–36 | Transition from program to independent function |

**Target state at 36 months:**
- Security is part of the organization's core engineering identity, not a bolt-on
- 70%+ of low/medium-level security triage is handled by champions
- Champion role is embedded in career frameworks as a technical leadership path
- Security team is freed to focus on high-risk, high-impact strategic work

---

## Repository Structure

```
security-champions-kit/
├── README.md                        # This file
├── WHY-THIS-EXISTS.md               # Deeper context on failure modes and design decisions
├── program/
│   ├── ROADMAP.md                   # Full 36-month phased roadmap
│   ├── charter-template.md          # Program goals, scope, executive sponsorship
│   ├── roles-and-expectations.md    # Champion, Senior Champion, manager expectations
│   ├── maturity-model.md            # Associate → Champion → Senior progression
│   └── launch-checklist.md          # Pre-launch readiness checklist
├── onboarding/
│   ├── champion-onboarding.md       # First steps for new champions
│   ├── welcome-email-template.md    # Welcome communication template
│   └── first-30-days.md             # Structured onboarding plan
├── playbooks/
│   ├── threat-modeling.md           # Champion-led threat modeling guide
│   ├── dependency-review.md         # SCA triage and remediation playbook
│   ├── sast-triage.md               # Static analysis result triage guide
│   ├── security-review-request.md   # How to request a security review
│   └── risk-acceptance.md           # Risk acceptance workflow and template
├── metrics/
│   ├── kpi-framework.md             # What to measure and why
│   ├── phase-targets.md             # Suggested targets per phase
│   └── reporting-template.md        # Quarterly reporting template
├── recognition/
│   ├── recognition-playbook.md      # Champion recognition at every level
│   ├── manager-kudos-templates.md   # Ready-to-send manager recognition templates
│   └── career-framework-language.md # Suggested language for career ladder integration
└── community/
    ├── meeting-agenda-template.md   # Monthly champion meetup agenda
    ├── communication-calendar.md    # Suggested communications cadence
    └── retrospective-template.md    # Bi-annual program retrospective guide
```

---

## Core Design Principles

**Security buy-in is a manager problem first, a champion problem second.**
Champions cannot protect their own time. Managers can. Get manager commitment in writing before onboarding a single champion.

**Delegation is the point. Training is the prerequisite.**
Champions who train but never do meaningful security work leave within two quarters. Real work — triage, code review, threat model participation — is the retention mechanism.

**Start small. Prove value. Then scale.**
Launching with 10–15 carefully selected champions across diverse teams produces better 18-month outcomes than launching with 50 champions across the org at once.

**Recognition must reach multiple levels.**
Champion-level recognition (shout-outs, badges, spotlight) matters. Manager-level recognition (kudos templates, director visibility) matters more for program health.

**Course-correct early and explicitly.**
Each phase includes documented levers for common problems: low retention, manager resistance, program scale issues. Plan for problems before they happen.

---

## How to Adapt This

**Small organizations (< 200 engineers):** Compress Phases 1–2 into a single 6-month phase. Skip the multi-tier champion model initially. Focus on getting 5–8 high-quality champions rather than broad coverage.

**Large enterprises (> 2000 engineers):** Add a program manager role to coordinate across business units. Introduce "pod leads" from Phase 2 onward to manage coordination at scale. Expect Phase 1 to take longer due to organizational complexity.

**Regulated industries (financial services, healthcare, government):** Align champion work to audit-relevant controls from the start. Document champion participation in vulnerability remediation for evidence collection. Frame the program to compliance stakeholders as a control effectiveness multiplier.

**Rebuilding a failed program:** Start with a frank retrospective on why the previous program failed. Communicate the changes explicitly to managers who were burned before. Consider a different name to signal a genuine relaunch, not a rebrand.

---

## Getting Started

1. Read [`WHY-THIS-EXISTS.md`](./WHY-THIS-EXISTS.md) for the full context behind the design decisions
2. Review [`program/ROADMAP.md`](./program/ROADMAP.md) and adapt the phases to your organizational timeline
3. Use [`program/charter-template.md`](./program/charter-template.md) to build executive alignment before recruiting champions
4. Work through [`program/launch-checklist.md`](./program/launch-checklist.md) before going live

---

## Contributing

This framework is a living document. If you have adapted it, improved it, or learned something new from running a Security Champions program — contributions are welcome. Open an issue or submit a pull request.

---

## License

MIT License. Use it, adapt it, share it.

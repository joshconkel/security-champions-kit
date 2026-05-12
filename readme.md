# Security Champions Starter Kit

> A practitioner-built framework for embedding security ownership inside engineering teams — designed around what actually causes programs to fail.

---

## Why Most Security Champions Programs Fail

Most organizations have attempted a Security Champions program. Most have failed, been abandoned, or quietly faded out. The failure modes are consistent:

**1. The Recruiting Pipeline Problem**
Security teams use the program to identify and recruit talented engineers into the security org. Managers figure this out quickly. They stop nominating their best people. Participation quietly dies.

*This framework addresses it by* requiring manager co-ownership from day one. Champions are nominated *with* manager approval and commitment, not extracted from teams without it.

**2. Training Without Work**
Champions complete training modules, earn badges, attend sessions — and then return to their teams with no change in what they actually do. There is nothing to apply the training to. Motivation evaporates within a quarter.

*This framework addresses it by* delegating real, meaningful security work to champions from Phase 1, scaling in complexity as champions mature. Training is always paired with immediate application.

**3. No Manager Accountability**
The program is treated as an optional extracurricular. Managers support it in theory but never protect champion time or recognize it in performance discussions. Champions deprioritize it when sprint pressure mounts.

*This framework addresses it by* securing written manager commitment upfront, integrating champion work into team OKRs, and providing managers with templates to recognize and reward their champions visibly.

For the full diagnosis — including what this framework does *not* solve — read [`why-this-exists.md`](./why-this-exists.md).

---

## Who This Is For

- Security engineers and program managers building or rebuilding a Security Champions program
- Engineering leaders looking to scale security without scaling headcount
- Organizations that have tried and failed at previous incarnations of this program
- Champions themselves, looking for practical guidance on what the role actually involves

---

## What This Is Not

- A compliance checkbox exercise
- A training catalog with a fancy name
- A security team recruiting tool

---

## The Belt System

Champions progress through a **six-level belt system** that ties security contribution directly to career growth. Progression is based on demonstrated impact — not time served or training completion.

| Belt | Title | Program Phase |
|---|---|---|
| ⬜ White | Interested | Pre-program |
| 🟡 Yellow | Associate Champion | Phase 1 (0–6 months) |
| 🟢 Green | Core Champion | Phase 2 (6–12 months) |
| 🔵 Blue | Advanced Champion | Phase 3 (12–18 months) |
| 🟤 Brown | Senior Champion / Pod Lead | Phase 3–5 (18–30 months) |
| ⬛ Black | Specialist / Architect Champion | Phase 4–6 (24–36 months) |

Each belt has explicit promotion criteria, defined responsibilities, and mapped recognition. See [`belt-progression.md`](./belt-progression.md) for the full framework.

---

## Framework Overview

This kit provides a **36-month phased roadmap** for building a Security Champions program from scratch or relaunching a failed one. Each phase has explicit goals, activities, metrics, and course-correction levers.

| Phase | Timeline | Goal |
|---|---|---|
| 1: Relaunch & Reestablish | Months 0–6 | Build trust, show value, avoid overload |
| 2: Land & Expand | Months 6–12 | Scale coverage, deepen training, delegate tasks |
| 3: Delegate & Accelerate | Months 12–18 | Champions as semi-independent security force |
| 4: Optimize & Specialize | Months 18–24 | Refine based on feedback, offer specialization paths |
| 5: Institutionalize | Months 24–30 | Embed security into engineering identity |
| 6: Sustain & Evolve | Months 30–36 | Transition from program to independent function |

**Target state at 36 months:**
- Security is part of the organization's core engineering identity — not a bolt-on
- 70%+ of low and medium-level security triage is handled by champions
- Champion role is embedded in career frameworks as a technical leadership path
- Security team is freed to focus on high-risk, high-impact strategic work

---

## Repository Contents

### Root Level

These documents are for anyone evaluating whether to adopt the framework. Read them before opening any subfolder.

| Document | Description |
|---|---|
| [`why-this-exists.md`](./why-this-exists.md) | The full diagnosis of why Security Champions programs fail, the design decisions that respond to each failure mode, and an honest account of what this framework does not solve |
| [`value-proposition.md`](./value-proposition.md) | What is in it for every stakeholder — VP through mid-level engineer — in their own terms. Includes a common objections and responses table. Use this before and during recruitment conversations |
| [`belt-progression.md`](./belt-progression.md) | The six-level belt system defining how champions grow from interested engineer to specialist. Includes promotion checklists, responsibilities, and recognition signals for each belt |
| [`CONTRIBUTING.md`](./CONTRIBUTING.md) | How to contribute corrections, new content, or adaptations. Read this before opening a pull request |
| [`LICENSE`](./LICENSE) | MIT License — use it, adapt it, share it |

---

### `program/` — Building and Running the Program

Documents for program owners and security team members planning and operating the program.

| Document | Description |
|---|---|
| [`roadmap.md`](./program/roadmap.md) | The full 36-month phased roadmap with goals, activities, metrics, and course-correction levers for each phase. Start here after reading the root-level documents |
| [`charter-template.md`](./program/charter-template.md) | A complete program charter template covering scope, governance, roles, resource requirements, manager commitment forms, and approval signatures. Required before recruiting your first champion |
| [`roles-and-expectations.md`](./program/roles-and-expectations.md) | Explicit expectations for every participant — champions, managers, directors, executive sponsors, and the security team. Includes a scope boundary quick-reference table and champion rights |
| [`launch-checklist.md`](./program/launch-checklist.md) | Pre-launch readiness checklist covering organizational alignment, infrastructure, cohort selection, metrics baseline, and security team capacity. Complete every item before onboarding your first champion |
| [`career-framework-language.md`](./program/career-framework-language.md) | Suggested language for integrating champion participation into engineering career ladders at mid-level, senior, staff, and principal levels. Includes ready-to-use self-review and manager review language |

---

### `onboarding/` — Getting Champions Started

Documents used during champion recruitment and the first 90 days.

| Document | Description |
|---|---|
| [`champion-onboarding.md`](./onboarding/champion-onboarding.md) | The complete onboarding guide for new champions — what the program is, what it is not, time commitment, first week steps, the buddy system, and the 90-day probation structure |
| [`welcome-email-template.md`](./onboarding/welcome-email-template.md) | Ready-to-send welcome email template for newly accepted champions covering first steps, buddy assignment, tooling access, and first meetup |
| [`first-30-days.md`](./onboarding/first-30-days.md) | Week-by-week structured plan for the first 30 days of probation including training milestones, first triage task, SOP creation, and 30-day check-in |

---

### `playbooks/` — Doing the Work

Step-by-step guides for the security activities champions perform. Each playbook includes a belt-level audience guide, step-by-step process, AI augmentation section with specific prompts, escalation criteria, and a reusable checklist or template.

| Document | Description |
|---|---|
| [`threat-modeling.md`](./playbooks/threat-modeling.md) | A lightweight, champion-friendly threat modeling process using STRIDE. Includes a dedicated AI-specific threat category section covering prompt injection, model inversion, excessive agency, and supply chain risks |
| [`sast-triage.md`](./playbooks/sast-triage.md) | How to triage static analysis findings — confirming real vulnerabilities, dismissing false positives with documented rationale, and escalating appropriately. Includes a common false positive patterns table and AI-assisted triage guidance |
| [`dependency-review.md`](./playbooks/dependency-review.md) | A four-dimension dependency risk assessment covering vulnerability, maintenance health, license compatibility, and supply chain integrity. Includes a PR checklist and AI-augmented evaluation guidance |
| [`security-review-request.md`](./playbooks/security-review-request.md) | When and how to request a security review — review type matrix, champion preparation responsibilities, timing guidance, ship gate criteria, and a complete review request template |
| [`risk-acceptance.md`](./playbooks/risk-acceptance.md) | The formal process for accepting a known security risk — when it is and is not appropriate, approval authority by severity, compensating controls, remediation commitments, and a signed acceptance form template |

---

### `metrics/` — Measuring What Matters

| Document | Description |
|---|---|
| [`kpi-framework.md`](./metrics/kpi-framework.md) | The full metrics framework — leading indicators in the first quarter covering trust, engagement, and capability formation; transitional indicators covering workload absorption and knowledge sharing; lagging indicators covering security outcomes and organizational value; and a table of metrics to intentionally avoid and why |
| [`phase-targets.md`](./metrics/phase-targets.md) | Concrete benchmark targets for each phase with minimum acceptable, healthy target, and a column to record your own organizational targets. Includes explicit phase gate criteria that must be met before advancing |
| [`reporting-template.md`](./metrics/reporting-template.md) | Quarterly program health report template written in business language for directors, VPs, and executive sponsors — covering program snapshot, security impact, highlights, concerns, upcoming items, and leadership requests |

---

### `recognition/` — Keeping Champions

| Document | Description |
|---|---|
| [`recognition-playbook.md`](./recognition/recognition-playbook.md) | Recognition design principles, recognition by phase from Phase 1 through Phase 6, recognition by audience for champions and managers through executive level, budget guidance framed as retention cost, and a full-year recognition calendar template |
| [`manager-kudos-template.md`](./recognition/manager-kudos-template.md) | Four ready-to-send manager recognition templates covering first contribution, quarterly impact update, belt promotion announcement, and program defense for managers facing pushback from their own leadership |

---

### `community/` — Running the Community

| Document | Description |
|---|---|
| [`meeting-agenda-template.md`](./community/meeting-agenda-template.md) | Monthly champion meetup agenda with pre-meetup checklist, section-by-section timing, topic format options for rotating meeting variety, post-meetup action items, and meetup health signals |
| [`communication-calendar.md`](./community/communication-calendar.md) | Full communications cadence from weekly shout-outs through annual summits — organized by frequency with channel, owner, and notes for each communication type |
| [`retrospective-template.md`](./community/retrospective-template.md) | Bi-annual program retrospective structure including pre-retro survey design, facilitation agenda with timing, a decision framework for acting on themes, an appreciation round, post-retro action tracking, and health signals to interpret results |

---

## Getting Started

Follow this sequence. The order matters.

**1. Understand the failure modes**
Read [`why-this-exists.md`](./why-this-exists.md) and [`value-proposition.md`](./value-proposition.md). You cannot sell this program to stakeholders if you cannot articulate why previous attempts failed and what is different this time.

**2. Build executive alignment**
Use [`program/charter-template.md`](./program/charter-template.md) to get executive sponsor and engineering leadership sign-off. A program without a signed charter is an activity, not a program.

**3. Plan your rollout**
Read [`program/roadmap.md`](./program/roadmap.md) and adapt phase timelines to your organization. Set your Phase 1 targets using [`metrics/phase-targets.md`](./metrics/phase-targets.md).

**4. Confirm launch readiness**
Work through [`program/launch-checklist.md`](./program/launch-checklist.md) completely before approaching any champion candidates.

**5. Recruit and onboard your first cohort**
Use [`program/roles-and-expectations.md`](./program/roles-and-expectations.md) in manager briefing sessions. Send [`onboarding/welcome-email-template.md`](./onboarding/welcome-email-template.md) to accepted champions. Give every new champion [`onboarding/champion-onboarding.md`](./onboarding/champion-onboarding.md) and [`onboarding/first-30-days.md`](./onboarding/first-30-days.md) on day one.

**6. Run the program**
Use `playbooks/` documents as working references for champions doing real security tasks. Run monthly meetups using [`community/meeting-agenda-template.md`](./community/meeting-agenda-template.md). Track health using [`metrics/kpi-framework.md`](./metrics/kpi-framework.md).

**7. Report and recognize**
Deliver quarterly reports using [`metrics/reporting-template.md`](./metrics/reporting-template.md). Run recognition using [`recognition/recognition-playbook.md`](./recognition/recognition-playbook.md) and [`recognition/manager-kudos-template.md`](./recognition/manager-kudos-template.md).

**8. Course-correct and evolve**
Run bi-annual retrospectives using [`community/retrospective-template.md`](./community/retrospective-template.md). Advance phases only when gate criteria in [`metrics/phase-targets.md`](./metrics/phase-targets.md) are met.

---

## How to Adapt This

**Small organizations (< 200 engineers)**
Compress Phases 1–2 into a single 6-month phase. Skip the multi-tier belt model initially — start with Yellow and Green only. Focus on 5–8 high-quality champions rather than broad coverage.

**Large enterprises (> 2000 engineers)**
Add a dedicated program manager. Introduce pod leads from Phase 2 onward. Expect Phase 1 to run longer due to organizational complexity and the time required to build manager trust at scale.

**Regulated industries (financial services, healthcare, government)**
Align champion triage work to audit-relevant controls from Phase 1. Document champion participation in vulnerability remediation for evidence collection. Frame the program to compliance stakeholders as a control effectiveness multiplier, not a culture initiative.

**Rebuilding a failed program**
Start with an honest retrospective on what failed before and communicate the changes explicitly to managers who were burned. The value proposition and why-this-exists documents are your primary tools here. Consider a fresh name — not a rebrand, but an actual relaunch with acknowledged differences.

---

## Contributing

Contributions are welcome — corrections, additions, adaptations, and real-world case studies from practitioners who have run or adapted the framework. Read [`CONTRIBUTING.md`](./CONTRIBUTING.md) before opening a pull request or issue.

---

## License

MIT License. Use it, adapt it, share it. See [`LICENSE`](./LICENSE).

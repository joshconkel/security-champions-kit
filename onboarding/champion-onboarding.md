# Champion Onboarding Guide

Welcome to the Security Champions program. This document walks you through everything you need to know in your first weeks — what the program is, what is expected of you, how to get started, and where to get help.

Read this before your first meetup. It will make that conversation significantly more useful.

---

## What You Are Signing Up For

You are not signing up to become a security engineer. You are signing up to be a security-capable engineer — someone who can identify and triage common issues in your team's code, connect your team to the right resources when needed, and help make security a normal part of how your team ships software.

The goal is to reduce friction between security and engineering — not to add a second job to your existing one.

---

## What This Is Not

- A path to being recruited into the security team (if that interests you, that is a separate conversation)
- A training program you complete once and then ignore
- A volunteer activity that competes with your delivery commitments
- An audit or compliance role — you are not here to enforce rules

---

## Your Time Commitment

At Yellow belt, expect to spend **2–4 hours per week** on champion activities. This includes:

- Triage of assigned scanner findings
- Monthly champion meetup (typically 60–90 minutes)
- Training modules (front-loaded in your first 30 days, then lighter)
- Creating at least one SOP from your triage work during probation
- Participation in the champion community channel

Your manager has agreed to protect this time. If sprint pressure is consistently making it impossible to participate, raise it with your manager and with the program owner — do not just quietly stop showing up.

---

## Your First Week

### Day 1–2: Access and Orientation

- [ ] Confirm access to the champion community channel
- [ ] Confirm access to SAST, SCA, and DAST scanner dashboards for your team's scope
- [ ] Confirm access to the training platform
- [ ] Read the program charter
- [ ] Read the roles and expectations document
- [ ] Bookmark the playbooks folder — you will use these regularly

If any access is missing, contact the program owner immediately. Starting without tooling access wastes your first week.

### Day 3–5: Training Begins

Start the following modules in order. Do not skip ahead — each builds on the previous:

1. Program orientation (purpose, structure, belt system, expectations)
2. Security fundamentals (CIA triad, common threat types)
3. OWASP Top 10 — developer depth

Complete at your own pace, but aim to finish these within your first two weeks.

### End of Week 1: Introduction Meeting

You will have a 30-minute 1:1 with your Security team contact. Come prepared to discuss:

- Your team's current technology stack
- Any security concerns or recurring issues you have already noticed on your team
- Questions about scope, tooling, or expectations

---

## Your First 30 Days

### Training (Weeks 1–3)

Complete the following in addition to the orientation modules:

- [ ] Secure coding basics in your primary language or framework
- [ ] OWASP Top 10 — developer depth (if not completed in week 1)
- [ ] Security-focused code review basics
- [ ] SAST/SCA/DAST triage 101

Modules should take 2–4 hours total per week alongside your other champion activities. If training is taking significantly more time than this, flag it.

### First Triage Task (Week 2)

By the end of week 2, you will receive your first assigned scanner findings to triage. These will be low severity findings selected specifically to be approachable for new champions.

For your first triage:

1. Read the SAST Triage or Dependency Review playbook before you start
2. Work through the triage steps
3. Document your disposition and rationale — do not just close the finding
4. Flag anything you are uncertain about to your Security team contact before closing

Your first triage is expected to take longer than it will later. That is normal. Ask questions.

### First SOP (Weeks 3–4)

By the end of your 30-day period, create at least one SOP or wiki entry based on your triage work. It does not need to be long — a concise document explaining what you found, what you did, and what to do the same way next time is exactly what is needed.

SOPs serve two purposes: they force you to understand what you did well enough to explain it, and they give your team a reusable reference so the next engineer does not start from scratch.

---

## Your First 90 Days: The Probation Period

The first 90 days is your probation period. It is not punitive — it is a structured way to confirm that the program scope and expectations are right for you and your team, and that your participation is adding value.

At the 90-day mark, you will have a review with your Security team contact and your manager. The review covers:

- Training completion
- Triage quality and participation
- SOP contributions
- Engagement in meetups and the champion channel
- Manager feedback on workload impact

Successful completion of probation advances you to Green belt. This is recognized publicly in the champion channel and in the quarterly spotlight.

### What Makes a Successful Probation

| Area | What Good Looks Like |
|---|---|
| Training | All required modules completed |
| Triage | Findings triaged with documented rationale; few or no undocumented closures |
| Contribution | At least one SOP created from real work |
| Engagement | Attended most monthly meetups; responsive in champion channel |
| Workload | Manager confirms participation has not materially harmed delivery |

### What to Do If You Are Struggling

Probation is not meant to be stressful. If you are finding the workload too heavy, the scope unclear, or the training too dense, say so — to your Security team contact, your buddy, or the program owner.

The program adjusts for legitimate workload or capacity constraints. It cannot adjust for problems it does not know about. Silence leads to attrition. Communication leads to solutions.

---

## The Buddy System

You will be paired with an existing champion — at Green belt or above — as your buddy for the first 90 days. Your buddy is:

- A first point of contact for questions you do not want to take to the Security team directly
- Someone who has been through probation and can tell you what it is actually like
- A sounding board for triage questions before you finalize your disposition
- Not your manager, not your evaluator — just a peer who has been through this

Reach out to your buddy in your first week. Do not wait for them to find you.

---

## Getting Help

| Question Type | Who to Ask |
|---|---|
| Triage question on a specific finding | Your buddy first, then Security team contact |
| Training content question | Security team contact |
| Access or tooling issue | Program owner |
| Scope question (is this mine to handle?) | Security team contact |
| Workload or capacity concern | Your manager, then program owner |
| Something feels wrong with the program | Program owner directly |

There are no questions too basic for your first 90 days. The Security team expects to spend time with new champions. Use that time.

---

## Community and Communication

**Champion channel:** Your primary community space. Use it to share wins, ask questions, flag interesting findings (without sensitive details), and connect with champions on other teams. This channel is what makes the program feel like a community rather than an assignment.

**Monthly meetups:** Required for Yellow and Green belts. These are a mix of technical content, guest sessions, and informal discussion. They run approximately 60–90 minutes. Agenda is shared in advance.

**Quarterly spotlight:** Each quarter, the Security team publishes a spotlight newsletter recognizing champion contributions. Nominations come from Security team contacts, managers, and peer champions.

---

## AI Tools in Your Champion Work

AI tools can meaningfully accelerate your work as a champion, particularly for understanding vulnerability classes, drafting triage notes, and preparing threat models. Each playbook includes an AI augmentation section with specific prompts for that activity.

General guidance for using AI in champion work:

- Use AI to accelerate your analysis, not replace it. AI does not know your runtime environment, your team's code, or your organization's risk context.
- Verify AI assessments against authoritative sources (NVD, CWE, OWASP) before finalizing a triage decision.
- AI-generated fix recommendations should always be reviewed and tested before committing.
- Never paste sensitive code, customer data, or production credentials into external AI tools. Check your organization's AI use policy before using any external AI service with company code.

---

## Quick Reference: Your First 90 Days

```
Week 1:   Confirm access → Read charter and roles doc → Start orientation modules → 1:1 with Security contact
Week 2:   Complete foundational training → Receive and triage first findings → Meet your buddy
Week 3:   Complete advanced training modules → Continue triage → Draft first SOP
Week 4:   Submit first SOP → Attend first monthly meetup → Check in with buddy
Day 60:   Informal check-in with Security contact → Workload check-in with manager
Day 90:   Formal probation review → Belt promotion to Green if criteria met → Public recognition
```

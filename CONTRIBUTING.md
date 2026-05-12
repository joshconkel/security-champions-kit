# Contributing to the Security Champions Kit

Thank you for considering a contribution. This framework was built from real program experience and improves when people who have run, adapted, or learned from it share what they found.

---

## What We Welcome

**Content improvements**
- Corrections to inaccurate or outdated guidance
- Additional examples, templates, or checklists that fill genuine gaps
- Clarifications where existing content is ambiguous or unclear

**Adaptations and case studies**
- Documented adaptations for specific industries, org sizes, or regulatory environments
- Anonymized retrospectives on how you applied the framework and what you changed

**New content**
- Playbooks for activity types not currently covered (e.g., DAST triage, secure design review, AI red teaming)
- Specialization track guides for Black belt paths (CI/CD security, API security, AI security)
- Tooling integration guides (GitHub Advanced Security, Snyk, Semgrep, Wiz, etc.)

**Translations**
- Framework documents translated into other languages — open an issue first to coordinate

---

## What We Do Not Accept

- Content that is proprietary, confidential, or belongs to a specific organization without explicit permission to share
- Vendor-specific content that promotes commercial products without disclosing affiliation
- Content that is purely theoretical without practical application guidance
- Additions that duplicate existing content without meaningful improvement

---

## How to Contribute

### For small fixes (typos, broken links, minor clarifications)

Open a pull request directly. No issue required. Keep the PR description short and specific about what changed and why.

### For new content or significant changes

1. Open an issue using the **Content Suggestion** template before writing anything
2. Describe what you want to add or change and why it improves the framework
3. Wait for a response — we will confirm whether the contribution fits the framework's direction before you invest time writing it
4. Once confirmed, open a PR referencing the issue

This prevents wasted effort on contributions that do not fit.

---

## Pull Request Guidelines

**Branch naming:** `content/short-description` for new content, `fix/short-description` for corrections

**PR title format:** Use a clear, specific title:
- ✅ `Add DAST triage playbook for champion use`
- ✅ `Fix broken links in kpi-framework.md`
- ❌ `Updates`
- ❌ `Various improvements`

**PR description:** Answer three questions:
1. What does this change or add?
2. Why does this improve the framework?
3. Is this based on real program experience? If so, briefly describe the context (anonymized is fine).

**Document formatting:** Follow the style of existing documents:
- Lead with purpose and audience
- Use tables for structured comparisons
- Include escalation criteria for any process document
- Include an AI augmentation section for any activity-based playbook
- End complex documents with a quick reference checklist or template

**One concern per PR:** Do not bundle unrelated changes. Separate PRs are easier to review and merge.

---

## Content Standards

**Write for practitioners, not theorists.**
Every document should be usable by a Green belt champion on a Tuesday afternoon with a real finding in front of them. If it reads like a white paper, it needs to be rewritten.

**Be specific about who this is for.**
Every new playbook or guide should include a belt-level table at the top. Content aimed at Brown belts should not be written as if Yellow belts will act on it independently.

**Include AI augmentation guidance.**
The framework is built around the reality that champions will use AI tools in their work. Any new activity-based playbook should include an AI augmentation section with specific, tested prompts.

**Do not advocate for specific vendors.**
The framework is tool-agnostic by design. Reference tool categories (SAST scanner, SCA tool, training platform) rather than specific products. If a document needs to reference a specific tool, it belongs in a tooling integration guide, not a core playbook.

**Name the limits.**
Good framework documents say what they do not cover and when to escalate. If your contribution handles something well in some contexts but not others, say so explicitly.

---

## Licensing

By submitting a contribution, you agree that your contribution will be licensed under the MIT License that covers this project. You confirm that you have the right to contribute the content and that it does not contain proprietary or confidential information belonging to any organization.

---

## Questions

Open an issue with the **Question** label if you are unsure whether something fits before investing time in writing it. We would rather answer a question upfront than review a contribution that does not fit.

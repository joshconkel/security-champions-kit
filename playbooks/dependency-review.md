# Playbook: Dependency Review

## Purpose

Every dependency your team adds is code you did not write, did not review, and cannot fully control. Dependencies introduce vulnerabilities, license risk, and supply chain exposure. This playbook gives champions a repeatable process for evaluating dependencies before they enter the codebase and managing them once they are in.

---

## Who This Is For

| Belt | Role |
|---|---|
| 🟡 Yellow | Review flagged SCA findings with Security team guidance |
| 🟢 Green | Own dependency triage for low and medium severity findings in team scope |
| 🔵 Blue+ | Own dependency governance for a product area; advise on third-party risk decisions |

---

## When to Do a Dependency Review

- A developer proposes adding a new direct dependency
- A PR introduces a new transitive dependency that was not previously in the graph
- A scanner surfaces a new vulnerability in an existing dependency
- A dependency reaches end of life or is abandoned by its maintainer
- A dependency produces a security advisory or CVE
- A major version upgrade is proposed for a high-risk dependency

---

## The Dependency Risk Surface

Dependencies introduce risk across four dimensions. Assess all four before approving a new dependency or triaging a finding.

| Dimension | Questions to Ask |
|---|---|
| **Vulnerability** | Does this dependency have known CVEs? What is the severity and exploitability? Is a patched version available? |
| **Maintenance** | Is this dependency actively maintained? When was the last commit, release, and response to issues? Does it have a single maintainer or an organization behind it? |
| **License** | What license does this dependency use? Is it compatible with your codebase and distribution model? Does it impose copyleft obligations? |
| **Supply chain integrity** | Is this package published from a trusted source? Are releases signed? Is the package name at risk of typosquatting? Does the build pipeline verify integrity? |

---

## Step-by-Step Process

### Step 1: Identify the Dependency

When a new dependency is proposed or a finding is surfaced, capture:

- Package name and version
- Package manager and registry (npm, PyPI, Maven, etc.)
- Direct or transitive dependency
- Purpose: what does it do and why is it being added?
- Alternatives considered

---

### Step 2: Check for Known Vulnerabilities

Run your SCA scanner against the dependency if it has not already been flagged. Cross-reference against:

- The National Vulnerability Database (NVD) at nvd.nist.gov
- The package manager's security advisory feed (npm advisories, PyPI advisories, GitHub Advisories)
- OSV.dev for a unified cross-ecosystem view

For each CVE or advisory:

- What is the CVSS score and vector?
- Is the vulnerable code path reachable in your specific usage?
- Is a patched version available?
- If no patch exists, is a workaround documented?

**Reachability matters.** A critical CVE in a dependency you use only at build time, in a non-network-accessible path, carries different risk than the same CVE in a runtime dependency exposed to user input. Document your reachability assessment when closing a finding.

---

### Step 3: Assess Maintenance Health

A well-maintained dependency with no current CVEs is lower risk than an unmaintained one. Check:

- **Last commit date:** Greater than 12 months with no activity is a warning sign
- **Last release date:** Separate from commits — some projects are stable by design
- **Open issues and PRs:** A large backlog of unaddressed security issues is a signal
- **Maintainer count:** Single-maintainer packages are higher supply chain risk
- **Deprecation notices:** Is the project officially deprecated or archived?

Resources:
- GitHub repository activity and pulse
- Libraries.io for cross-ecosystem health signals
- Snyk Advisor or Socket.dev for package health scoring

---

### Step 4: Verify License Compatibility

License review is not optional. Licenses that seem permissive may impose obligations that affect your distribution model or codebase.

| License Type | Risk Level | Notes |
|---|---|---|
| MIT, BSD, Apache 2.0 | Low | Permissive; attribution required |
| LGPL | Medium | Linking rules apply; legal review recommended for compiled products |
| GPL v2/v3 | High | Copyleft; may require open-sourcing your code — escalate to legal |
| AGPL | High | Network use triggers copyleft; escalate to legal |
| Commercial / proprietary | Variable | Review terms carefully; escalate to legal |
| No license stated | High | No permission to use; escalate before adding |

When in doubt, escalate to your legal or open source program office. Do not add high-risk license dependencies without explicit approval.

---

### Step 5: Assess Supply Chain Integrity

Supply chain attacks targeting package registries have increased significantly. Before adding a new dependency:

- **Verify the publisher:** Is the package published by the expected organization or individual? Search for the package on the registry and confirm the publisher matches the expected source.
- **Check for typosquatting:** Search for similarly named packages. Attackers register packages with names one character off from popular packages.
- **Check download volume and age:** Very new packages with no history and no downloads warrant extra scrutiny.
- **Verify signing:** Does the package registry support signed releases? Is this package signed?
- **Review the install scripts:** For npm packages especially, check `preinstall` and `postinstall` scripts for unexpected behavior.

---

### Step 6: Make and Document the Decision

| Decision | Criteria |
|---|---|
| **Approve** | No known vulnerabilities, active maintenance, compatible license, clean supply chain signals |
| **Approve with conditions** | Known low/medium vulnerability with documented non-reachable path, or fix expected within defined timeframe |
| **Defer** | Better maintained or lower-risk alternative exists; propose the alternative |
| **Reject** | High/critical unremediated vulnerability, incompatible license, abandoned maintainer, supply chain red flags |
| **Escalate** | Unable to assess confidently; high-risk license; critical CVE with no patch; supply chain anomaly |

Document your decision in the PR or the dependency review ticket. Include your rationale, the evidence you reviewed, and any conditions attached to the approval.

---

## AI Augmentation

AI tools meaningfully accelerate dependency risk assessment, especially for triaging large SCA outputs or evaluating unfamiliar packages.

### Triaging SCA Output

When your scanner produces a list of findings, paste the output and ask:

> "Here is my SCA scanner output. For each finding, assess whether the vulnerability is likely to be reachable in a typical [language/framework] web application and suggest a triage priority. Flag any findings that should be escalated immediately."

Review the output critically — AI does not know your specific usage context, so reachability assessments require your verification.

### Evaluating Unfamiliar Packages

> "I am evaluating adding [package name] to a [language] project. Summarize its purpose, maintenance health, known security history, and any supply chain concerns I should be aware of."

Follow up with your own verification against the registry and NVD — AI knowledge has a training cutoff and may not reflect the most recent advisories.

### Understanding CVE Impact

> "Explain CVE-[number] in plain language. What type of vulnerability is it, what conditions are required for exploitation, and what is the impact if exploited in a [your context] application?"

This is particularly useful for champions still developing their vulnerability knowledge. AI explanations of CVEs are generally reliable for well-documented vulnerabilities.

### License Risk Assessment

> "I am adding a dependency licensed under [license name] to a [SaaS / distributed / open source] product. What are the key obligations and risks I should be aware of?"

Always verify AI license guidance with your legal team for high-risk or ambiguous licenses.

### Generating Dependency Review Summaries

> "Here is my dependency review for [package name]: [your notes]. Draft a summary suitable for a PR comment or security review ticket."

---

## Escalation Criteria

Escalate to the Security team if:

- A dependency has a HIGH or CRITICAL CVE with no available patch
- License assessment is unclear or potentially high-risk
- Supply chain anomalies are detected: unexpected publisher, suspicious install scripts, new package with high download claims
- A transitive dependency introduces a vulnerability you cannot remediate by upgrading the direct dependency
- An existing dependency is confirmed abandoned with no maintained fork

---

## Dependency Review Checklist

Use this as a PR checklist for new dependency additions.

```markdown
## Dependency Review: [Package Name] [Version]

**Package Manager:** 
**Dependency Type:** Direct / Transitive
**Purpose:** 

### Vulnerability Check
- [ ] Checked NVD and package advisory feed
- [ ] No known HIGH/CRITICAL CVEs, or reachability assessed and documented
- [ ] Patched version available (if applicable)

### Maintenance Health
- [ ] Active commits within last 12 months
- [ ] Active maintainer or organization
- [ ] No deprecation notice

### License
- [ ] License identified: [license name]
- [ ] License confirmed compatible with our distribution model
- [ ] Legal escalation completed (if required)

### Supply Chain Integrity
- [ ] Publisher verified against expected source
- [ ] No typosquatting risk identified
- [ ] Install scripts reviewed (for npm packages)
- [ ] Package signing verified (if supported by registry)

### Decision
- [ ] Approved
- [ ] Approved with conditions: [describe]
- [ ] Rejected: [reason]
- [ ] Escalated to Security team

**Champion:** 
**Date:**
```

---

## Further Reading

- OWASP Dependency Check
- OWASP Software Component Verification Standard (SCVS)
- CISA Secure Software Development Framework — Supply Chain section
- OpenSSF Scorecard for evaluating open source package security posture
- SLSA Framework for understanding supply chain integrity levels
- OSV.dev for cross-ecosystem vulnerability data

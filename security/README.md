<div align="center">

# `SECURITY // INTELLIGENCE`

### Advisory analysis · Remediation intelligence · Open-source security

`zuhairhalawa` &nbsp;·&nbsp; `EVIDENCE > HYPE` &nbsp;·&nbsp; `DEFENSIVE RESEARCH`

[![GitHub security advisory credits](https://img.shields.io/badge/GITHUB-ADVISORY%20CREDITS-071F21?style=for-the-badge&logo=github&logoColor=60f7c5)](https://github.com/advisories?query=credit%3Azuhairhalawa)
[![Accepted security advisory edits](https://img.shields.io/badge/ADVISORY%20DATABASE-MERGED%20PRs-071F21?style=for-the-badge&logo=github&logoColor=60f7c5)](https://github.com/github/advisory-database/pulls?q=is%3Apr+is%3Amerged+author%3Azuhairhalawa)
[![AdvisoryGuard](https://img.shields.io/badge/TOOL-ADVISORYGUARD-071F21?style=for-the-badge&logo=npm&logoColor=60f7c5)](https://github.com/zuhairhalawa/AdvisoryGuard)

**[← Back to main profile](../README.md)**

</div>

---

## `$ cat /about/security-research`

My security contributions focus on **improving the reliability of public vulnerability information**: tracking patched versions, connecting published advisories to remediation commits, and preserving accurate metadata for downstream users of advisory databases.

I also build tooling around advisory data quality. My public project **[AdvisoryGuard](https://github.com/zuhairhalawa/AdvisoryGuard)** is an offline, read-only CLI that detects risky differences between advisory records, including accidentally removed CVSS vectors.

**Attribution matters.** The accepted pull requests below are evidence of **GitHub Advisory Database edits**, not claims that I originally discovered the associated vulnerabilities, wrote vendor patches, or obtained official CVE finder credit. GitHub normally assigns *Analyst* credit for accepted edits to the global Advisory Database; a CVE record's independent credits field is a different form of recognition. [GitHub's credit policy](https://github.blog/changelog/2023-03-07-security-advisories-now-have-multiple-types-of-credits/) · [CVE roles](https://github.com/CVEProject/cve-schema/blob/main/schema/CVE_Record_Format.json).

## `$ ls -la /evidence/merged`

These are **eight independently checked examples** of pull requests authored by [@zuhairhalawa](https://github.com/zuhairhalawa) and merged into the [official GitHub Advisory Database](https://github.com/github/advisory-database). This is a curated sample, **not a claim about the total number of accepted contributions or credits**.

| Advisory / package | What the merged edit improved | Primary evidence |
| :--- | :--- | :--- |
| **ApostropheCMS** · [GHSA-vmg4-6gfg-83qx](https://github.com/advisories/GHSA-vmg4-6gfg-83qx) | Patched version **4.32.1** and remediation reference for prototype-pollution DoS | **[Merged PR #10651](https://github.com/github/advisory-database/pull/10651)** |
| **FacturaScripts** · [GHSA-2p5x-4jr6-x5jg](https://github.com/advisories/GHSA-2p5x-4jr6-x5jg) | Corrected fixed-release boundary (**2026.2**) and referenced CSV/XLS export hardening | **[Merged PR #10639](https://github.com/github/advisory-database/pull/10639)** |
| **Dolibarr** · [GHSA-2mfj-r695-5h9r](https://github.com/advisories/GHSA-2mfj-r695-5h9r) | Corrected the patched-release boundary while documenting affected **22.x** versions | **[Merged PR #10672](https://github.com/github/advisory-database/pull/10672)** |
| **NotrinosERP** · [GHSA-qv4m-m73m-8hj7](https://github.com/advisories/GHSA-qv4m-m73m-8hj7) | Recorded fixed release **1.1.0** and linked employee-document upload remediation | **[Merged PR #10646](https://github.com/github/advisory-database/pull/10646)** |
| **Goploy** · [GHSA-4g5x-hcwm-82jw](https://github.com/advisories/GHSA-4g5x-hcwm-82jw) | Corrected file-endpoint traversal advisory with patched release and fix link | **[Merged PR #10641](https://github.com/github/advisory-database/pull/10641)** |
| **Vikunja** · [GHSA-fprf-r6rv-xg99](https://github.com/advisories/GHSA-fprf-r6rv-xg99) | Added patched release **2.7.0** and task-search scope fix reference | **[Merged PR #10638](https://github.com/github/advisory-database/pull/10638)** |
| **wger** · [GHSA-rjpf-7pf5-q54x](https://github.com/advisories/GHSA-rjpf-7pf5-q54x) | Linked ownership-check remediation for workout logs | **[Merged PR #10605](https://github.com/github/advisory-database/pull/10605)** |
| **OpenAM** · [GHSA-fpmh-vx4h-xc33](https://github.com/advisories/GHSA-fpmh-vx4h-xc33) | Linked the commit that fixes insecure SSO-cookie initialization | **[Merged PR #10594](https://github.com/github/advisory-database/pull/10594)** |

**Machine-readable evidence:** [`evidence.json`](evidence.json) records the advisory, contribution category, primary PR URL and verified merge date for each example. **[See all accepted PRs live](https://github.com/github/advisory-database/pulls?q=is%3Apr+is%3Amerged+author%3Azuhairhalawa)** and **[see public advisory credits](https://github.com/advisories?query=credit%3Azuhairhalawa)**.

## `$ cat /evidence/case-studies.md`

### `CASE 001` · ApostropheCMS — follow the fix across release lines

**Problem with the advisory metadata:** the published advisory needed a clear patched version and corresponding remediation reference.

**Contribution:** [PR #10651](https://github.com/github/advisory-database/pull/10651) set the patched version to **4.32.1** and added the relevant fix commit. The PR explicitly notes the release-line complication: a direct commit-ancestry check alone would be misleading, so it also compares code in the release tag.

**Why it matters:** a correct fixed-version boundary helps consumers interpret dependency warnings and decide which updates remediate a disclosed issue.

**Evidence:** [Accepted PR](https://github.com/github/advisory-database/pull/10651) · [Published advisory](https://github.com/advisories/GHSA-vmg4-6gfg-83qx)

### `CASE 002` · Dolibarr — don't assume version order equals safety

**Problem with the metadata:** a vulnerability range could mistakenly imply that all later releases were safe, even though some 22.x maintenance releases remained affected.

**Contribution:** [PR #10672](https://github.com/github/advisory-database/pull/10672) updated the patched-version field and documented why **22.0.5** was still affected despite its publication after **23.0.0**. The PR provides version- and commit-based reasoning.

**Why it matters:** version-range mistakes can cause security dashboards to under-report exposure or give maintainers incorrect remediation guidance.

**Evidence:** [Accepted PR](https://github.com/github/advisory-database/pull/10672) · [Published advisory](https://github.com/advisories/GHSA-2mfj-r695-5h9r)

### `CASE 003` · FacturaScripts — link risk to an actionable fix

**Problem with the metadata:** the advisory needed the first fixed release and a concrete link to the change addressing spreadsheet formula injection.

**Contribution:** [PR #10639](https://github.com/github/advisory-database/pull/10639) recorded **2026.2** as patched and linked the remediation commit for exports.

**Why it matters:** a well-maintained advisory should answer both *which versions are affected?* and *what change fixed the problem?*

**Evidence:** [Accepted PR](https://github.com/github/advisory-database/pull/10639) · [Published advisory](https://github.com/advisories/GHSA-2p5x-4jr6-x5jg)

> These are **case studies of accepted metadata contributions**. The technical observations above summarize the linked PR descriptions and their accepted edits; they are not fresh vulnerability reproductions performed for this portfolio.

## `$ ./advisoryguard --help`

The clearest companion to this work is a real tool:

**[AdvisoryGuard](https://github.com/zuhairhalawa/AdvisoryGuard)** · [npm package](https://www.npmjs.com/package/advisoryguard)

- Offline, read-only advisory record validation and before/after diffing.
- Detects accidental CVSS severity removal and risky affected-package changes.
- Uses a pinned, validated OSV schema; no telemetry or credential collection.
- Includes documented terminal output and a regression demo in its repository.

```bash
# Inspect an advisory change before proposing it.
npx advisoryguard diff before.json after.json
```

This connects the public contributions to **practical software engineering for vulnerability-data quality**, rather than relying on badges alone.

## `$ cat /research/standards`

| Evidence tier | What this portfolio claims | What it **doesn't** claim |
| :--- | :--- | :--- |
| **Merged Advisory Database PR** | An accepted public metadata contribution, with author and merge evidence | Discovery, vendor patch authorship, or independent PoC validation |
| **GitHub advisory credit** | The role published on GitHub's advisory page | Automatic equivalent credit in the CVE Record |
| **Original vulnerability disclosure** | Only if a report and its attribution can be independently verified | Credit inferred solely from an analyst edit |
| **Tool/project work** | Source, tests and releases documented in the linked repository | External accreditation or third-party security audit |

**Verification standard:** links lead to primary GitHub records. The pull request is the source of the specific *change*. A published advisory describes the *vulnerability*. Those are different pieces of evidence.

**Disclosure boundaries:** I aim to test only software and environments I am authorized to assess, follow maintainers' reporting channels, avoid exposing private reports or credentials, and distinguish confirmed findings from hypotheses. A publicly disclosed advisory does not authorize attacking deployed systems.

## `$ cat /next_steps/roadmap`

The next milestones are substantive—not more decorative badges:

1. Publish a reproducible **patch-diff review** with tests on a local, authorized version of an affected open-source package, using non-destructive test inputs.
2. Maintain a transparent advisory ledger showing accepted edits, review feedback, and the exact information each change improved.
3. Extend **AdvisoryGuard** with regression tests for tricky version boundaries and preservation of advisory metadata, without silent network access.
4. If original vulnerabilities are discovered in authorized work, follow coordinated disclosure and preserve verifiable reporter/finder evidence before making any attribution claim.

---

<div align="center">

```text
SECURITY RESEARCH > evidence-first
STATUS: publicly reviewable contributions
CREDITS: exactly as recorded by the issuing platform
```

[GitHub Profile](https://github.com/zuhairhalawa) · [Advisory Credits](https://github.com/advisories?query=credit%3Azuhairhalawa) · [Merged Advisory PRs](https://github.com/github/advisory-database/pulls?q=is%3Apr+is%3Amerged+author%3Azuhairhalawa) · [AdvisoryGuard](https://github.com/zuhairhalawa/AdvisoryGuard)

</div>

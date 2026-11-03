# EXTERNAL RECOGNITION // Research & contribution roadmap

**zuhairhalawa** · Open-source vulnerability intelligence · **Updated November 3, 2026**

> **Objective:** build recognition from independent organizations for genuine, reviewable security engineering—not by copying GitHub advisory credits into unrelated programs.

[← Security portfolio](README.md) · [Verified merged evidence](evidence.json) · [Advisory credits](https://github.com/advisories?query=credit%3Azuhairhalawa)

---

## 0x01 / Current evidence: what is proven

- GitHub's public advisory-credit UI shows **40 credits** on November 3, 2026 (user-observed count; this page does **not** claim all 40 records were individually audited).
- [Eight examples of authored, merged PRs](evidence.json) in the official GitHub Advisory Database were checked against the accepted pull-request metadata. They document remediation references and affected-/patched-release corrections.
- [AdvisoryGuard](https://github.com/zuhairhalawa/AdvisoryGuard) is a published security advisory metadata validation tool, with source and documentation publicly inspectable.
- There is **no blanket claim of original vulnerability discovery, CVE.org finder attribution, external certification, or bug-bounty reputation**. Those require separate evidence.

**Useful public positioning:** “Open-source security advisory analyst and developer, contributing accepted corrections to the GitHub Advisory Database and building tools for vulnerability-data integrity.”

## 0x02 / Recognition channels — ranked by fit

| Priority | Official organization / platform | Real route to external recognition | What is NOT transferable |
| --- | --- | --- | --- |
| **1 / Fastest clear badge path** | **[GitLab Contributor Platform](https://contributors.gitlab.com/)** | Create a legitimate contribution to GitLab; a qualifying merged MR is recorded by GitLab. GitLab's current documentation lists **Level 1 at 25 points**, **20 points for an MR created** and **60 for an MR merged**. Check that the contribution appears in the platform before claiming a badge. | Existing GitHub GHSA Analyst credits do not award GitLab points. |
| **2 / Best standards credibility** | **[OpenSSF OSV Schema](https://github.com/ossf/osv-schema)** | Make a reviewed contribution to the vulnerability schema, tooling, validation, docs or tests. For significant proposals, open an issue and discuss them with the [OpenSSF Vulnerability Disclosures WG](https://openssf.org/groups/vulnerability-disclosures/). | A merged PR is not an OpenSSF certification or maintainer appointment. |
| **3 / Best data-quality engineering** | **[Google OSV.dev](https://github.com/google/osv.dev)** | Contribute a properly reviewed data-quality, converter, documentation or UI fix. The project's [contribution guide](https://github.com/google/osv.dev/blob/master/CONTRIBUTING.md) asks for an issue first and requires clear AI-assistance disclosure where applicable. | GitHub advisory edits may flow into OSV's imported data, but not as personal OSV credit. |
| **4 / Professional visibility** | **[OWASP Dubai](https://owasp.org/chapters/dubai)** | Volunteer or pitch a practical talk on version-range mistakes, advisory quality and remediation traceability. Chapter meetings are open; official recognition requires actual contribution/participation. | Attendance does not confer an OWASP security certification. |
| **5 / If original findings arise** | **[Snyk vulnerability disclosure](https://docs.snyk.io/snyk-data-and-governance/disclosure-of-a-vulnerability-in-an-open-source-package)** | Send a genuinely new, responsibly disclosed open-source vulnerability through Snyk's documented process, subject to verification and appropriate attribution. | Public metadata edits are not discoveries and should not be resubmitted as new vulnerabilities. |
| **6 / If original reports are accepted** | **[HackerOne](https://docs.hackerone.com/en/articles/8369865-reputation)** / **[Bugcrowd](https://docs.bugcrowd.com/researchers/engagement-brief/hall-of-fame/)** | Earn reputation or a Hall of Fame entry by submitting a valid authorized report under the respective program rules. | A GitHub Analyst credit is not a valid bug bounty submission, bounty payout, or platform rank. |

**GitLab's additional upside:** its [contributor platform](https://contributors.gitlab.com/docs/user-guide) has a published level system, and it also has a selective [Notable Contributor program](https://contributors.gitlab.com/notable-contributors). Neither is guaranteed merely by applying.

**OpenSSF's additional upside:** [Scorecard's contributor ladder](https://github.com/ossf/scorecard/blob/main/CONTRIBUTOR_LADDER.md) documents a progression from community participant to community member, triager and maintainer, conditional on participation and approvals. It is a longer-term path—not an immediate title.

## 0x03 / Two authentic technical contribution opportunities

I checked the public issue details in the *google/osv.dev* project on November 3, 2026. Both issues are marked open and **unassigned**, but are relatively old; ask maintainers whether work is still desired before implementing anything.

| Candidate | Why it fits | Grounding |
| --- | --- | --- |
| [OSV.dev #215 — detect introduced > fixed](https://github.com/google/osv.dev/issues/215) | A version ordering bug can mark an incorrect set of releases as affected. An ideal extension of existing advisory-range analysis. | Open · Good first issue · Unassigned when checked; last updated 2025 |
| [OSV.dev #2924 — derive version boundaries from compare URLs](https://github.com/google/osv.dev/issues/2924) | Improve remediation/version inference from published upstream comparison links. | Open · Good first issue · Unassigned when checked; last updated 2024 |

**Important:** Do not treat these as reserved tasks. They may be stale, requirements may have changed, and OSV.dev's contribution process explicitly asks you to discuss the issue and wait for an assignment before a PR. For anything AI-assisted, comply with their AI disclosure instructions.

For GitLab, start with the [official contribution onboarding](https://contributors.gitlab.com/) and identify a small, current security-documentation or dependency-scanning issue with maintainer approval, then make one complete, tested merge request. Do not create token MRs simply to game a leaderboard.

## 0x04 / The 30-day execution plan

### Week 1 — evidence and identity

- Keep the [public portfolio](README.md) and [machine-readable evidence](evidence.json) accurate; verify every newly added PR is actually merged.
- Use the same identity **zuhairhalawa** on GitHub and professional profile links. Prefer one professional tagline: **Security Advisory Analysis · Open-source Security Tooling · Defensive Engineering**.
- Publish a technical write-up with a claim/evidence/method/limitation structure. Start with the [Dolibarr patched-release case](VERSION-BOUNDARY-CASE-STUDY.md); it links the actual accepted PR and does not claim discovery.

### Week 2 — GitLab route

- Create or link a GitLab account, finish official contributor onboarding.
- Identify one suitable issue in current security documentation, dependency scanning, or safe metadata validation; confirm scope first.
- Implement a helpful change with validation and reviewer feedback; only show GitLab achievement/badge once GitLab itself awards it.

### Week 3 — OpenSSF / OSV route

- Introduce the version-boundary case study to the [OpenSSF Vulnerability Disclosures WG](https://openssf.org/groups/vulnerability-disclosures/) as evidence of a data-quality class, not a request for an honorary title.
- Check OSV issues #215 and #2924 with the maintainers; choose a live, well-scoped task and produce a minimal repro, regression test and proposed fix if invited.

### Week 4 — professional visibility

- Propose a practical **10-minute OWASP Dubai session:** “The Patch Version Trap: How Vulnerability Advisories Can Misstate Affected Releases.”
- Demonstrate a safe, local, non-exploit version-boundary comparison plus the [AdvisoryGuard](https://github.com/zuhairhalawa/AdvisoryGuard) workflow.
- Publish a technically precise LinkedIn post pointing to an accepted PR, methodology and limitations. Ask for feedback, not accreditation.
- Use resulting accepted PRs, talk recordings or published articles as new evidence; do not self-award organizational badges.

## 0x05 / Attribution and integrity protocol

For **every** public portfolio entry record:

1. **Your role:** analyst/advisory metadata contributor vs reporter/finder vs maintainer vs patch author.
2. **Official record:** primary pull request, platform acknowledgement, or CVE record link.
3. **Verification status:** proposed / open / merged / credited / rejected / withdrawn; never merge these categories.
4. **What changed:** a specific corrected range, remediation reference, warning, test or tool behavior.
5. **Limits:** what was inferred from a PR versus reproduced through independent tests.
6. **Disclosure:** share only already-public evidence; never post confidential reports or test against assets without authorization.

### CVE.org / NVD

A published CVE identifier describes a vulnerability. There is **no general CVE ownership claim button**. A responsible CNA may update the optional credit information on a CVE Record if evidence supports an accurate role. That process is not a way to bulk-transfer GitHub analyst credits. NVD may display the same vulnerability metadata, but it does not provide a transferable “40 CVEs owned” badge.

### What success actually looks like

| Milestone | What counts as proof |
| --- | --- |
| GitHub advisory analyst | Accepted Advisory Database PR plus public credit entry |
| GitLab contributor | Accepted GitLab MR, profile award or points as GitLab records them |
| OpenSSF / OSV contributor | Accepted upstream PR in an OpenSSF / OSV repository |
| OWASP contributor or speaker | Published chapter agenda, talk, organizer acknowledgment or project contribution |
| Original security researcher | Verified new finding, coordinated disclosure and credible reporter/finder acknowledgment |

None of these milestones should be claimed before independently recorded by the relevant organization.

## 0x06 / Primary reading

- [GitHub's policy for community Advisory Database contributions](https://docs.github.com/en/code-security/concepts/vulnerability-reporting-and-management/github-advisory-database)
- [GitLab Contributor Platform: levels and contribution points](https://contributors.gitlab.com/docs/user-guide)
- [GitLab contributing guide](https://about.gitlab.com/community/contribute/)
- [OpenSSF OSV Schema contribution instructions](https://github.com/ossf/osv-schema/blob/main/CONTRIBUTING.md)
- [OpenSSF Vulnerability Disclosures Working Group](https://openssf.org/groups/vulnerability-disclosures/)
- [Google OSV.dev contribution instructions](https://github.com/google/osv.dev/blob/master/CONTRIBUTING.md)
- [OWASP Dubai chapter](https://owasp.org/chapters/dubai)
- [OWASP chapters policy and access](https://owasp.org/policy/chapters)
- [Snyk original vulnerability disclosure and attribution rules](https://docs.snyk.io/snyk-data-and-governance/disclosure-of-a-vulnerability-in-an-open-source-package)
- [HackerOne reputation rules](https://docs.hackerone.com/en/articles/8369865-reputation)
- [Bugcrowd Hall of Fame requirements](https://docs.bugcrowd.com/researchers/engagement-brief/hall-of-fame/)

---

> **The signal:** An honest, well-evidenced security contribution to a respected project's mainline is stronger than a self-generated badge, an unverified claim of 40 discoveries, or dozens of cosmetic pull requests.

[← Verified security research portfolio](README.md) · [← Main GitHub profile](../README.md)

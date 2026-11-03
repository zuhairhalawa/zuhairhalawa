# THE PATCH-VERSION TRAP
## Why a release published later can still be vulnerable

**A public advisory-analysis case study based on an accepted GitHub Advisory Database contribution**  
**By:** [zuhairhalawa](https://github.com/zuhairhalawa) · **Focus:** remediation version boundaries · **Updated:** November 3, 2026

[← Security research](README.md) · [Accepted source PR #10672](https://github.com/github/advisory-database/pull/10672) · [Published GHSA-2mfj-r695-5h9r](https://github.com/advisories/GHSA-2mfj-r695-5h9r)

---

> **The question:** If a project releases a patched version, are all updates *published after it* necessarily safe?
>
> **Answer:** No. Parallel release branches and backport policies can make publication dates, numeric versions and actual remediation state diverge.

## 01 / The source record

In the published Dolibarr advisory [GHSA-2mfj-r695-5h9r](https://github.com/advisories/GHSA-2mfj-r695-5h9r), the issue concerns authenticated local file inclusion through the `selectobject.php` code path.

The accepted [GitHub Advisory Database pull request #10672](https://github.com/github/advisory-database/pull/10672), authored by **zuhairhalawa**, documented a corrected patched-version boundary. The PR identifies the remediation commit, associated with release **23.0.0**, that sanitizes the class path, requires a `.class.php` suffix, and enforces a restricted-area check in the affected endpoint.

The analysis also explains why **22.0.5** still remained affected despite having been released after **23.0.0**. The security fix was present on the newer major-release line but had not been backported to that 22.x maintenance release.

**Evidence:** [Accepted PR and its written technical reasoning](https://github.com/github/advisory-database/pull/10672). That PR was merged on October 26, 2026. This article documents a security-data contribution and its rationale; it does **not** assert that the author originally found the vulnerability or wrote the vendor patch.

## 02 / Why a simple release-date comparison fails

A naive workflow says:

> A fix was published on date D. Therefore releases after date D are safe.

That shortcut breaks when multiple release lines exist.

| Published release | Relationship to the fix | Why |
| :--- | :--- | :--- |
| **23.0.0** | Patched in the cited PR evidence | Contains the corrective changes. |
| **22.0.4** | Affected in the PR evidence | Does not contain those changes. |
| **22.0.5** | **Still affected** in the PR evidence | Published later, but the 22.x line did not receive the backport. |

This is **not** a statement that every release in every 22.x line is vulnerable forever. It is a specific observation grounded in the accepted PR's repository checks and version analysis.

A trustworthy advisory needs to represent **actual affected versions** and **the first proven patched release in the relevant line**, not just extrapolate from timestamps.

## 03 / A repeatable, defensible review procedure

When verifying the version range of an already disclosed advisory:

1. **Read the disclosed behavior.** Identify the code path or security property described by the original record.
2. **Find the authoritative remediation.** Prefer a maintainer-linked fix commit, changelog or upstream security release.
3. **Locate the tag containing the fix.** Inspect the actual release branch or tag rather than relying only on a human-friendly version string.
4. **Check adjacent releases and active maintenance branches.** Look for a backport; do not infer one from a later publication date.
5. **Map the evidence to a supported advisory format.** Be precise about `introduced`, `fixed` and `last_affected`; use multiple ranges where the format requires them.
6. **Make a minimal, reviewable edit.** Explain exactly what field changed and why, and link the primary references.
7. **Avoid unrelated metadata damage.** Revalidate unaffected fields, severity vectors, affected packages and references after editing.
8. **Preserve the attribution boundary.** A contributor can strengthen advisory metadata without being the initial vulnerability finder.

This is a **review checklist**, not proof that every step was executed by the author outside what the linked PR records.

## 04 / Practical tooling connection

My separate project [AdvisoryGuard](https://github.com/zuhairhalawa/AdvisoryGuard) helps catch accidental data loss during advisory edits. It compares before/after records and calls out risky changes such as removed CVSS entries and unexpected package metadata alterations.

It addresses a complementary failure mode: even when an intended fixed-version correction is well evidenced, a careless editor or transformation may also remove unrelated security metadata.

```sh
# Offline, read-only example with appropriately sourced local records:
npx advisoryguard diff before.json after.json
```

**What the tool is not:** a proof that a vendor patch is correct, an exploit verifier, a new CVE assignment service, or a substitute for upstream release investigation.

## 05 / What this contribution demonstrates

- **Vulnerability intelligence:** understanding remediation information and how release branches affect advisory accuracy.
- **Evidence evaluation:** linking disclosed behavior to upstream commits and concrete release references.
- **Data-quality engineering:** making targeted, explainable corrections that can be reviewed by maintainers.
- **Responsible attribution:** separating Analyst-style metadata work from original discovery and patch authorship.

This case study can be independently examined using the accepted upstream PR. It does not claim the OSV.dev, OpenSSF, GitLab, CNA or NVD teams reviewed or endorsed this separate write-up.

## 06 / Follow-up research opportunities

The same class of mistakes is relevant to public vulnerability databases that ingest and transform affected-version ranges. For example, the publicly tracked [OSV.dev issue #215](https://github.com/google/osv.dev/issues/215) discusses a range with an `introduced` version that actually sorts after the `fixed` version. A potential contribution would be a carefully scoped, tested validation improvement **only after OSV maintainers confirm the issue is still open for work**.

The [OpenSSF OSV Schema](https://github.com/ossf/osv-schema) is also relevant to ensuring that version information can be expressed consistently across ecosystems, with changes subject to project review.

**Do not automatically turn this case study into a CVE credit request.** Its primary evidence supports an accepted advisory-data correction, not original discovery.

---

**Primary sources:** [GitHub Advisory Database PR #10672](https://github.com/github/advisory-database/pull/10672) · [Dolibarr advisory](https://github.com/advisories/GHSA-2mfj-r695-5h9r) · [OSV Schema](https://ossf.github.io/osv-schema/) · [GitHub community-contribution policy](https://docs.github.com/en/code-security/concepts/vulnerability-reporting-and-management/github-advisory-database).

[← Security portfolio](README.md) · [External recognition roadmap](EXTERNAL-RECOGNITION.md)

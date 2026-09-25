# Embargo Policy

This document describes the embargo process for security vulnerabilities in OpenSearch. It supplements the [Security Issue Response Process](https://github.com/opensearch-project/.github/blob/main/SECURITY.md) defined in the `.github` repository.

## What Is an Embargo?

An embargo is a period during which details of a vulnerability are kept confidential to allow time for a fix to be developed, tested, and released before the issue becomes public knowledge. During an embargo, only authorized parties (the SRT, the Fix Team, and the pre-disclosure list) have access to vulnerability details.

## Embargo Timeline

Embargo periods are negotiated on a case-by-case basis between the SRT and the reporter. The following targets are planning guidelines, not strict commitments or service-level guarantees:

| Phase | Planning Target |
| --- | --- |
| Advisory sent to pre-disclosure list | Within 2 weeks of confirmed report |
| Public disclosure | Within 4 weeks of pre-disclosure advisory |

### Adjustments

- **Reporter requests a longer embargo**: The SRT will honor reasonable requests for extended timelines.
- **Reporter requests accelerated disclosure**: If a reporter intends to disclose on a timeline shorter than the SRT would prefer, the SRT will work to have a fix or mitigation ready by that date. The SRT cannot prevent a reporter from disclosing independently.
- **Active exploitation in the wild**: The SRT will disclose immediately and release patches as soon as possible.
- **Severity-based**: Low severity issues (CVSS < 4.0) may follow a relaxed timeline aligned with the next [scheduled release](https://opensearch.org/releases/).

## Obligations During Embargo

All parties with access to embargoed information must maintain confidentiality until the embargo is lifted. Specifically, before the embargo date, recipients must **not** make available:

- The OpenSearch advisory or their own advisory
- The impact, scope, set of affected systems, or nature of the vulnerability
- Commits, patches, or code changes that fix the issue
- Patched software in any form (source or binary)

Without prior SRT approval, recipients may share only:

- The existence of an issue
- The assigned advisory number
- The planned disclosure date

## Pre-Disclosure List

The SRT maintains a pre-disclosure list of contributors, vendors, and operators who:

1. Require significant work post-disclosure to remediate the issue across large deployments, or
2. Can help develop and test fixes before public release.

### What the List Receives

- Advance copies of the advisory and patches, clearly marked with the embargo date, at least **7 days** before public disclosure.
- Notification at least **24 hours** before a release containing security fixes, with the public messaging, date, and time of the announcement.

### Sharing Between List Members

Pre-disclosure list members may share fixes, analysis, and related materials with the SRT and security teams of other list members. Technical measures must be taken to prevent unauthorized access.

### Deployment During Embargo

List members may deploy fixed versions during the embargo **only** with explicit SRT permission. Any restrictions will be stated in the embargoed advisory. If deployment involves user-facing disruption (e.g., restarts), communications may mention that the disruption is to correct a security issue, referencing only the publicly shareable information listed above.

### Joining the Pre-Disclosure List

Organizations that meet the criteria above may apply by emailing security@opensearch.org with:

- Organization name
- How you use OpenSearch
- Why you meet the criteria (user base size, remediation effort, ability to collaborate on fixes)
- Your organization's security problem handling process and public contact information
- Confirmation that you have read and agree to this policy
- Email addresses to add to the list

The SRT will review applications and respond with a decision.

### Embargo Violations

If a list member breaks embargo, the SRT will assess the impact, decide whether to accelerate disclosure, and determine whether to suspend or remove the member from the pre-disclosure list. A serious first violation or repeated violations will result in removal.

## References

- [OpenSearch Security Issue Response Process](https://github.com/opensearch-project/.github/blob/main/SECURITY.md) — the org-wide security policy
- [Security Release Process](SECURITY_RELEASE_PROCESS.md) — the full lifecycle in this repository

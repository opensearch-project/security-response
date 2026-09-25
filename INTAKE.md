# Vulnerability Intake Process

This document describes how to report a security vulnerability in any repository in the [OpenSearch organization](https://github.com/opensearch-project) and how the SRT processes incoming reports.

## How to Report

There are two ways to report a vulnerability:

### 1. Email (Preferred)

Send an email to **security@opensearch.org** with:

- **Affected repository** (e.g., `opensearch-project/OpenSearch`, `opensearch-project/security`)
- **Affected versions** (if known)
- **Description** of the vulnerability
- **Reproduction steps** or proof of concept
- **Impact assessment** (what can an adversary achieve?)
- **Any suggested fix** (optional)

The SRT monitors this inbox and will acknowledge your report within **48 hours**.

### 2. GitHub Private Vulnerability Reporting

You can also report directly through the **Security** tab on any `opensearch-project` repository:

1. Navigate to the repository on GitHub.
2. Click the **Security** tab.
3. Click **Report a vulnerability**.
4. Fill in the form and submit.

This creates a Draft GHSA visible only to the repository maintainers and OpenSearch organization administrators. The SRT will be notified and will follow up within **48 hours**.

> **Note**: You can also use the Security tab on this repository ([opensearch-project/security-response](https://github.com/opensearch-project/security-response)) if you are unsure which repository is affected.

## What Happens Next

After your report is received:

1. **Acknowledgment** (within 48 hours): An SRT member confirms receipt and may ask clarifying questions.
2. **Triage**: The SRT validates the report, determines the affected component, and scores severity using [CVSS 3.1](https://www.first.org/cvss/v3.1/specification-document).
3. **Draft GHSA**: If the report is confirmed, the SRT creates a Draft GHSA on the affected repository (if one was not already created via the Security tab).
4. **CVE reservation**: The SRT reserves a CVE ID. GitHub's CNA will assign the CVE when the GHSA is published.
5. **Embargo negotiation**: The SRT and reporter agree on an [embargo timeline](EMBARGO_POLICY.md).
6. **Fix coordination**: The SRT assembles a Fix Team and begins the [private fix process](PRIVATE_FIX_GUIDELINES.md).
7. **Tracking**: The issue is added to the private vulnerability tracking board.

## Requesting a GHSA or CVE for Your Repository

If you are a maintainer of an `opensearch-project` repository and have identified a vulnerability in your own component:

1. Email security@opensearch.org or message an SRT member on Slack.
2. Provide the repository name, a description of the issue, and a list of GitHub usernames who should have access to the private fork.
3. The SRT (via `opensearch-admin`) will create the Draft GHSA and temporary private fork on your repository.

You do not need to be an SRT member to request this — any project maintainer can initiate the process.

## Publicly Known Vulnerabilities

If the vulnerability is already publicly known (e.g., a CVE in a third-party dependency), no embargo is needed. You may:

- Open a public GitHub issue on the affected repository.
- The SRT will still track the fix on the private vulnerability tracking board.

## Reporter Expectations

- The SRT will keep you informed of progress throughout the process.
- You will be credited in the published advisory unless you request otherwise.
- If you have a preferred disclosure timeline, let the SRT know during the initial exchange. See the [Embargo Policy](EMBARGO_POLICY.md) for how timelines are negotiated.

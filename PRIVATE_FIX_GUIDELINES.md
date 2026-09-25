# Private Fix Guidelines

This document explains how to develop security fixes privately using GitHub Security Advisories and temporary private forks, and how to write commit messages that do not reveal the nature of the fix before disclosure.

## Requesting a Draft GHSA and Private Fork

Any maintainer or contributor who discovers or is assigned a security issue can request a Draft GHSA and temporary private fork. To do so:

1. **Contact an `opensearch-admin` member** (via Slack DM or email to security@opensearch.org) with:
   - The affected repository
   - A brief description of the issue
   - A list of GitHub usernames who need collaborator access to work on the fix (the "Fix Team")
2. The admin will create a [Draft GitHub Security Advisory (GHSA)](https://docs.github.com/en/code-security/security-advisories/working-with-repository-security-advisories/creating-a-repository-security-advisory) on the affected repository.
3. From the Draft GHSA, the admin will create a **temporary private fork** and add the Fix Team as collaborators.

### What You Get

- A private fork of the repository that is only visible to the Fix Team and `opensearch-admin`.
- The ability to create branches, push commits, and open pull requests within the private fork — all invisible to the public.
- The Draft GHSA serves as the central record for the vulnerability, including CVSS score, affected versions, and CVE ID.

## Working in the Private Fork

An `opensearch-admin` member must create the temporary private fork and grant the Fix Team access. After they are added as collaborators, Fix Team members can perform the following steps:

1. **Clone the private fork** using the URL provided in the Draft GHSA.
2. **Create a feature branch** from the target release branch (e.g., `main` or a version branch).
3. **Develop and test the fix** as you would in a normal PR.
4. **Open a pull request within the private fork** for review by other Fix Team members.
5. Once approved, **do not merge yet** — the merge is coordinated by the SRT to align with the release timeline.

### Keeping the Fork Up to Date

The private fork may fall behind the upstream repository. Periodically rebase or merge from upstream to avoid conflicts at merge time.

## Commit Message Hygiene

Commit messages in the private fork will become public when the fix is merged. To avoid drawing attention to the security nature of the fix before the advisory is published:

### Do Not Use

- "vulnerability", "exploit", "attack", "attacker", "CVE", "security fix", "security issue", "security bug"
- "injection", "bypass", "privilege escalation", "denial of service" (or similar terms that describe the class of vulnerability)
- Any CVE ID (e.g., `CVE-2026-XXXXX`)

### Do Use

- Neutral, descriptive language about what the code change does:
  - ✅ "Validate input parameters in query handler"
  - ✅ "Add bounds checking to buffer allocation"
  - ✅ "Enforce permission check before resource access"
  - ✅ "Update dependency X to version Y"
  - ✅ "Fix edge case in authentication flow"
- The same style and tone as any other bug fix or improvement.

### PR Titles and Descriptions

The same rules apply to PR titles and descriptions when the fix is merged into the public repository. Keep them factual and non-alarming.

## Merging the Fix

When the SRT gives the go-ahead (typically just before a release):

1. The Fix Team merges the private fork PR into the target branch of the **public** repository.
2. The merge should be timed to minimize the window between the commit appearing publicly and the patched release being available.
3. After the patched release is published, the SRT publishes the Draft GHSA, which makes the advisory and CVE public.

## After Disclosure

Once the GHSA is published:

- The temporary private fork is no longer needed and can be deleted by an `opensearch-admin` member.
- The CVE ID and advisory link can be referenced freely in follow-up commits, release notes, and discussions.

## Quick Reference

| Step | Who | Action |
| --- | --- | --- |
| Request private fork | Any maintainer | Contact `opensearch-admin` with repo, description, and collaborator list |
| Create Draft GHSA + fork | `opensearch-admin` | Set up GHSA, create private fork, add collaborators |
| Develop fix | Fix Team | Work in private fork, follow commit message guidelines |
| Review fix | Fix Team | PR review within private fork |
| Merge fix | Fix Team + SRT | Merge to public repo, timed with release |
| Publish advisory | SRT | Publish Draft GHSA after patched release is available |
| Clean up | `opensearch-admin` | Delete temporary private fork |

# Pre-Disclosure List Security Advisory Email

_Use this template to notify pre-disclosure list members of upcoming security fixes before they become public. Pre-disclosure list members receive this advisory ahead of the official release so they can prepare their teams and environments._

_This template is only used for private issues under embargo — not for publicly known 0-days._

TO: `$PRE_DISCLOSURE_LIST`

SUBJECT: `[EMBARGOED] OpenSearch Security Pre-Disclosure — $RELEASE_VERSIONS`

---

Hello,

As part of the OpenSearch project's security pre-disclosure process, we are contacting you regarding an upcoming advisory as a courtesy before it becomes public in our next release(s).

In the next few weeks, we will be releasing $RELEASE_VERSIONS_AND_DATES, which include a fix for $NUMBER_OF_ISSUES security issue(s). The accompanying advisory/advisories for these issues are enclosed below. Please be sure to notify your technical teams if you feel that your organization may be affected so that they can apply the fixes as soon as they become available.

---

<!-- Repeat this block for each advisory -->

### ADVISORY: $ADVISORY_TITLE

| | |
| --- | --- |
| **CVSS Score** | $CVSS_SCORE ($SEVERITY) |
| **CVSS Vector** | $CVSS_VECTOR |
| **CVE ID** | $CVE (if assigned) |
| **Affected Versions** | $AFFECTED_VERSIONS |
| **Patched Versions** | $PATCHED_VERSIONS |

**Impact:**

$IMPACT_DESCRIPTION

**Mitigation:**

$MITIGATION_DESCRIPTION

---

<!-- End repeating block -->

### Embargo

This information is under [embargo](https://github.com/opensearch-project/security-response/blob/main/EMBARGO_POLICY.md) until the public release date(s) listed above. Please do not share the details of these advisories outside of your organization's security and engineering teams until the embargo is lifted.

### Questions

If you have any questions or comments about this advisory, please contact the OpenSearch Security Response Team at security@opensearch.org. Please do **not** create a public GitHub issue.

Thank you,

$SRT_MEMBER on behalf of the OpenSearch Security Response Team

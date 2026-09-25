# OpenSearch Security Response

This repository documents the OpenSearch project's security vulnerability response process. It is the central reference for how security issues are reported, triaged, fixed, and disclosed across all [opensearch-project](https://github.com/opensearch-project) repositories.

To report a vulnerability, email **security@opensearch.org** or use the **Security** tab on any `opensearch-project` repository to file a private vulnerability report.

## Documents

| Document | Description |
| --- | --- |
| [Security Release Process](SECURITY_RELEASE_PROCESS.md) | End-to-end lifecycle from report intake through patch release and public disclosure |
| [Intake Process](INTAKE.md) | How to request a Draft GHSA or CVE for any OpenSearch repository |
| [Private Fix Guidelines](PRIVATE_FIX_GUIDELINES.md) | Working with Draft GHSAs, temporary private forks, and commit message hygiene |
| [Embargo Policy](EMBARGO_POLICY.md) | Embargo terms, timelines, and pre-disclosure list |
| [Roles and Responsibilities](ROLES.md) | SRT and Security TAG charter, membership, and how they interact |
| [Comms Templates](comms-templates/) | Email, Slack, and forum templates for each stage of the process |

## Security Response Team (SRT)

The SRT is the operational arm — it handles triage, fix coordination, and disclosure. See [ROLES.md](ROLES.md) for full responsibilities and membership criteria.

### Current Members

| Name | GitHub | Affiliation |
| --- | --- | --- |
| Kunal Khatua | [@kkhatua](https://github.com/kkhatua) | Amazon |
| Craig Perkins | [@cwperks](https://github.com/cwperks) | Amazon |
| Shikhar Jain | [@shikharj05](https://github.com/shikharj05) | Amazon |
| Gulshan Kumar | [@kumargu](https://github.com/kumargu) | Amazon |
| Nils Bandener | [@nibix](https://github.com/nibix) | Eliatra |
| Nagaraj G | [@nagarajg17](https://github.com/nagarajg17) | Amazon |

## Security TAG

The Security TAG is the advisory arm — it advises on severity, out-of-band release decisions, and policy changes, and makes recommendations to the [TSC](https://github.com/opensearch-project/technical-steering-committee). See [ROLES.md](ROLES.md) for full responsibilities and how the two groups work together.

## Contact

| Channel | Visibility | Use |
| --- | --- | --- |
| security@opensearch.org | Private | Report vulnerabilities. Monitored and triaged by the SRT. |
| GitHub Security tab | Private | File a private vulnerability report on any `opensearch-project` repo. |
| [OpenSearch Forum — Security](https://forum.opensearch.org/c/security/) | Public | General security discussion. |

## Code of Conduct

This project has adopted the [Contributor Covenant](https://www.contributor-covenant.org/) as its Code of Conduct. All community members are expected to adhere to it. See [CODE_OF_CONDUCT.md](https://github.com/opensearch-project/.github/blob/main/CODE_OF_CONDUCT.md) for details. This project is part of the [Linux Foundation](https://www.linuxfoundation.org/).

## License

This project is licensed under the [Apache License 2.0](LICENSE).

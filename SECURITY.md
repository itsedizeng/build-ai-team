# Security Policy

## Scope

Security reports may include:

- prompt-injection paths that can change the Skill’s goal or permissions;
- unsafe claims that planning, search, installation, login, private-data access, writes, uploads, publication, or deletion have been authorized when they have not;
- hidden or unexpected execution paths;
- third-party Skill recommendations that bypass source, license, file-tree, script, network, or permission review;
- repository or release artifacts whose checksums do not match the published manifest.

The Skill does not guarantee the safety of third-party Skills or external services. Review those projects independently before installation or execution.

## Supported versions

| Version | Supported |
|---|---|
| `1.0.x` | Yes |
| `1.0.0-rc.x` | No |
| `1.0-beta.x` | No |

## Reporting a vulnerability

Do not include credentials, private data, customer material, or a working exploit in a public issue.

If GitHub private vulnerability reporting is available for this repository, use the repository’s **Security → Report a vulnerability** flow. Otherwise, open a minimal public issue stating that you need a private reporting channel, without sensitive details.

Include, when safe:

- the affected file and version or commit;
- the expected permission boundary;
- the observed behavior;
- minimal reproduction steps using synthetic data;
- whether any external action actually occurred.

You will receive acknowledgment when the report is reviewed. Do not test against third-party accounts, private repositories, or real user data without authorization.

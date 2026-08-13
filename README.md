# Build AI Team

[English](README.md) | [简体中文](README.zh-CN.md)

> Release candidate: `v1.0.0-rc.9`

Build AI Team is an open-source, Codex-first Skill that recommends the smallest reliable AI setup for a request. It decides whether one Agent is enough or multiple persistent Agents are worthwhile, defines clear responsibilities and owned outcomes, recommends model configurations, and points to relevant Skills.

It plans first. It does **not** create a team, install a Skill, connect to an account, access private data, or write to an external system without the user’s confirmation for that action.

## Status

- The English runtime is derived from the independently validated Chinese `v1.0-beta13` behavior baseline. Clarification questions and complete recommendations follow the user’s latest substantive request language; technical identifiers remain accurate.
- The `v1.0.0-rc.9` five-file runtime and frozen 5-case / 7-run validation package each passed independent static review with 0 major / 0 minor / 0 blocker.
- A separate project-scoped Codex Desktop check used six fresh tasks with the same candidate: five English requests and one Chinese request. All six progress messages and complete recommendations followed the request language. This is a limited visible real-host check, not a statistical guarantee or cross-host validation.
- Codex Desktop project-based usage is the primary target.
- Entry instructions for ChatGPT Work and Claude are included, but those hosts have not been validated in practice for this release candidate.
- This project is not an official OpenAI, Codex, ChatGPT, or Anthropic project.
- Compatibility, model availability, and recommendation quality may vary by host and version; no vendor endorsement or compatibility guarantee is implied.
- This repository version is the first public MIT-licensed release candidate. Its annotated tag and Pre-release are created only after the exact public `main` commit is read back and verified.

## What it does

- Chooses a single-agent or multi-agent setup from the actual delivery, ownership, permission, validation, and capacity needs.
- Gives each role a clear purpose, responsibility, owned outcome, boundary, dependency, and necessity status.
- Separates the project lead from professional Owners so coordination does not absorb another role’s deliverable.
- Recommends one default model and reasoning effort per role, with optional upgrade or Token-saving guidance only when useful.
- Suggests up to three locally available or relevant public Skills with accurate source and installation status.
- Keeps planning, team creation, Skill discovery, installation, login, private-data access, writes, upload, publication, and deletion as separate actions.
- Uses English as the single runtime semantic source, responds in the user’s language, and keeps technical identifiers accurate.

## What it does not do automatically

- create Agents or persistent tasks;
- install or run third-party Skills;
- connect to accounts or business systems;
- read private data;
- write, upload, publish, or delete content;
- guarantee that a third-party Skill is safe, current, or suitable;
- guarantee one universally optimal team size.

## Install in a Codex project

1. Download or clone this repository.
2. Copy the complete [`build-ai-team/`](build-ai-team/) folder into the target project’s `.agents/skills/` directory.
3. Verify that the final path is:

```text
<project>/.agents/skills/build-ai-team/SKILL.md
```

4. Keep all five runtime files from the same version together:

```text
build-ai-team/
├── SKILL.md
├── agents/
│   └── openai.yaml
└── references/
    ├── curated-skills.md
    ├── model-routing.md
    └── skill-discovery.md
```

5. Start a fresh Codex task and explicitly select Build AI Team or enter:

```text
$build-ai-team I want to design, build, and launch a paid web app with accounts and subscriptions.
```

Do not copy only `SKILL.md`, and do not place the whole repository root inside `.agents/skills/`. When updating, replace all five runtime files together; do not mix files from different versions.

If the Skill does not appear, check the directory hierarchy, the exact `build-ai-team` folder name, and whether all five files are present before trying other fixes.

## Update or remove

- **Update:** replace the complete `build-ai-team/` folder with all five runtime files from one newer version, verify `SHA256SUMS.txt`, and start a fresh Codex task. Do not mix files from different versions.
- **Remove:** delete only `<project>/.agents/skills/build-ai-team/`, then start a fresh Codex task. Do not delete the parent `.agents/skills/` directory because it may contain other Skills.

Removing the Skill stops it from being loaded in future fresh tasks. It does not undo teams, files, installations, account access, or external actions that were separately confirmed earlier.

## Example requests

```text
$build-ai-team I only need a clickable prototype from this finalized PRD. No development is needed.
```

```text
$build-ai-team Plan a CRM migration with independent read-only verification. Do not connect to the CRM yet.
```

```text
$build-ai-team 我想做一个能上架 App Store 的记账 App，请给我团队建议。
```

## How to read a recommendation

- `Required`: belongs to the current team after confirmation.
- `Required if…`: the work package appears only when the stated observable condition becomes true; it is not created now.
- `Optional`: may improve quality, speed, or coverage but is not needed to complete the current goal and is not created by default.
- `Owner`: the one role accountable for a particular work package or deliverable.
- `project lead`: an existing substantive role that additionally coordinates plan, dependencies, and final handoff status; it does not gain ownership of other roles’ professional deliverables.
- independent reviewer: stays separate from production and does not edit the work being reviewed.

## Relevant Skill discovery

The first recommendation uses only Skills exposed by the current host and a small offline index. Live public discovery starts only when the user asks for it.

A recommendation is not installation. Installation is not permission to run scripts, log in, read private data, write, upload, publish, or delete. Review third-party Skills and their licenses before use.

Third-party project names and links are references only. Inclusion does not mean endorsement, affiliation, current compatibility, or security certification, and those projects remain subject to their own licenses.

## Checksums

[`SHA256SUMS.txt`](SHA256SUMS.txt) covers the five runtime files. Run the platform-appropriate SHA-256 check after downloading, and compare the results before use.

## Repository documents

- [Chinese README](README.zh-CN.md)
- [Changelog](CHANGELOG.md)
- [Contributing](CONTRIBUTING.md)
- [Security policy](SECURITY.md)
- [MIT License](LICENSE)

## Relationship to Agent Team v1.0

Build AI Team is a separate Skill product. It does not replace the earlier five-file [Agent Team v1.0](https://github.com/itsedizeng/agent-team) toolkit or its immutable release.

## License and official source

This public release candidate is provided under the [MIT License](LICENSE). The license change starts with the public `main` commit containing `v1.0.0-rc.9`; that version and later MIT-licensed releases may be used, copied, modified, merged, published, distributed, sublicensed, and sold subject to the license terms.

The earlier `v1.0-beta7` public source snapshot remains governed by the custom non-open-source license included in [that exact commit](https://github.com/itsedizeng/build-ai-team/blob/b2e81d3859a169056629e78dff322cfcfbefcf31/LICENSE.md). The MIT change is not retroactive.

The only official repository is [itsedizeng/build-ai-team](https://github.com/itsedizeng/build-ai-team).

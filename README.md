# Build AI Team

[English](README.md) | [简体中文](README.zh-CN.md)

> Stable release: `v1.0.1`

**Choose one Agent or the smallest reliable persistent AI team—with clear ownership, role-specific model routing, and source-aware Skill discovery.**

Optimized for diverse real-world scenarios, including software, product, design, research, data, content, migrations, and releases.

Give Build AI Team a real request. It works backward from the final result, keeps one Agent when that is enough, and adds a persistent role only when ownership, separation, or collaboration value is concrete.

```text
Your request → one Agent or the smallest reliable team
→ role ownership and model configuration → your confirmation
```

## Highlights

- **Right-sizes the team.** Starts with one Agent and adds a persistent role only when its ownership, separation, or collaboration value is concrete.
- **Makes every role accountable.** Each current role gets one clear responsibility, owned outcome, dependencies, and boundaries.
- **Routes models by responsibility.** Recommends a default model and reasoning effort, explicit upgrade conditions, and practical Token-saving options when safe.
- **Finds relevant Skills without blurring status.** Distinguishes locally available Skills from public leads; on request, it searches public sources and checks fit, provenance, maintenance signals, and permission risks.
- **Keeps the planning task useful.** After confirmation, the current planning conversation can remain the substantive project lead while only the other necessary persistent tasks are created. Persistent tasks are the live team state; no `AI_TEAM.md` roster is created.
- **Keeps new projects independent.** A shared folder, similar title, previous task, memory, or prior team plan does not make a request the same project. Existing project scope and tasks are reused only when the user clearly continues the same work.
- **Separates every consequential action.** Planning, team creation, public Skill search, installation, login, private-data access, writes, uploads, publication, and deletion remain distinct steps.

> Planning ≠ team creation ≠ Skill search ≠ installation ≠ external permission.

## Quick start

Explicit invocation only: select Build AI Team or use `$build-ai-team`; ordinary requests and mentions do not trigger it.

After installation, start a fresh Codex task and enter a real request:

```text
$build-ai-team I want to design, build, and launch a paid web app with accounts and subscriptions.
```

The first response is a plan. No team, Skill installation, account connection, private-data access, or external write happens without confirmation for that specific action.

## Support and validation

- English is the single runtime semantic source. Clarification questions and complete recommendations follow the user’s latest substantive request language; technical identifiers remain accurate.
- The `v1.0.1` five-file runtime passed independent static review with 0 major / 0 minor / 0 blocker.
- Minimal project-scoped Codex Desktop validation covered single-agent, multi-agent, maker-checker, conditional-role, external-search, and team-creation behavior. Six core behavior gates passed with 0 minor / 0 major / 0 blocker. After project-document team state was removed, a fresh five-gate differential validation of the final build also passed with 0 minor / 0 major / 0 blocker and confirmed zero project-document writes.
- Targeted `v1.0.1` differential checks covered explicit new projects, ordinary first requests, a clean project, and explicit continuation. Four unaffected cases passed on the preceding candidate; after the only failing path was narrowed, the final candidate passed an independent fresh protection check for that path. This is combined differential evidence, not a claim that the final candidate reran the full suite.
- These checks are limited real-host evidence, not a statistical guarantee or cross-host validation.
- Codex Desktop project-based usage is the primary target.
- Entry instructions for ChatGPT Work and Claude are included, but those hosts have not been validated in practice for this release.
- This project is not an official OpenAI, Codex, ChatGPT, or Anthropic project.
- Compatibility, model availability, and recommendation quality may vary by host and version; no vendor endorsement or compatibility guarantee is implied.
- This stable release continues the MIT license introduced by the public `v1.0.0-rc.9` commit.

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

## Local Skills and public search

The first recommendation separates suitable Skills exposed by the current host from unchecked public leads in a small offline index. Live public search starts only when the user asks for it, searches external sources rather than repeating the local list, and keeps the plan’s primary next step visible.

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

This stable release is provided under the [MIT License](LICENSE). The license change began with the public `main` commit containing `v1.0.0-rc.9`; that version and later MIT-licensed releases may be used, copied, modified, merged, published, distributed, sublicensed, and sold subject to the license terms.

The earlier `v1.0-beta7` public source snapshot remains governed by the custom non-open-source license included in [that exact commit](https://github.com/itsedizeng/build-ai-team/blob/b2e81d3859a169056629e78dff322cfcfbefcf31/LICENSE.md). The MIT change is not retroactive.

The only official repository is [itsedizeng/build-ai-team](https://github.com/itsedizeng/build-ai-team).

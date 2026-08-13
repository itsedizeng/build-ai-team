# Contributing to Build AI Team

Thank you for helping improve Build AI Team. Issues and pull requests are welcome.

## Before contributing

- Read [README.md](README.md), [README.zh-CN.md](README.zh-CN.md), and [SECURITY.md](SECURITY.md).
- Keep the runtime Skill focused on team planning. Do not add unrelated automation, installers, third-party Skill bundles, analytics, or account integrations.
- Do not include private data, customer material, credentials, proprietary prompts, or copyrighted test fixtures you cannot redistribute.
- Open an issue before making a large behavior or file-structure change.

## Runtime file boundary

The runtime package contains exactly five files:

```text
build-ai-team/SKILL.md
build-ai-team/agents/openai.yaml
build-ai-team/references/curated-skills.md
build-ai-team/references/model-routing.md
build-ai-team/references/skill-discovery.md
```

Repository documentation belongs at the repository root. Do not add README, changelog, installation guide, or governance files inside `build-ai-team/`.

## Change requirements

For a runtime change:

1. Explain the user problem and why the existing general model behavior is insufficient.
2. Prefer guidance over rigid industry templates.
3. Preserve explicit invocation, member-mode priority, unique ownership, independent-review separation, confirmation state, and external-action permission boundaries.
4. Update the English runtime semantic contract and verify localization behavior whenever a user-visible label or action changes.
5. Add or update realistic tests without leaking the intended answer into the public prompt.
6. Update `SHA256SUMS.txt` only after the final runtime files are fixed.

Documentation-only changes do not require model regression unless they change installation, invocation, permissions, compatibility, or user-visible product behavior.

## Language

English is the canonical runtime source. Clarification questions and complete recommendations must continue to follow the user’s language while preserving technical identifiers. Repository issues and contributions may be written in English or Chinese; English summaries are helpful for international collaboration.

## Pull requests

Keep each pull request focused. Include:

- what changed;
- why it changed;
- affected runtime files;
- validation performed;
- known limitations or untested hosts.

By contributing, you confirm that you have the right to submit the contribution and agree that it is licensed under the repository’s [MIT License](LICENSE).

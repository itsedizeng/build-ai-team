# Changelog

All notable user-facing changes to Build AI Team are documented here.

The project follows [Semantic Versioning](https://semver.org/).

## Unreleased

- No unreleased changes recorded yet.

## 1.0.0-rc.9 - 2026-08-13

### Added

- English as the canonical runtime source with output localized to the user’s language.
- One English runtime semantic contract that localizes team tables, role details, next-step actions, and Skill status to the user’s request language.
- A direct final-output language branch for clarification questions and complete recommendations, while keeping technical identifiers accurate.
- English repository documentation, Chinese README, contribution guide, security policy, and MIT License.

### Changed

- Released `v1.0.0-rc.9` source under the MIT License. The license change begins with the public `main` commit containing this version and is not retroactive: the earlier `v1.0-beta7` snapshot remains under the custom non-open-source license included in [its exact commit](https://github.com/itsedizeng/build-ai-team/blob/b2e81d3859a169056629e78dff322cfcfbefcf31/LICENSE.md).
- Select the English or localized final-output branch immediately before drafting, without inheriting the language from progress text, references, tools, platform metadata, or project defaults.
- Keep brief progress text as guidance rather than a release-blocking language contract; clarification and complete-recommendation language remains the user-facing requirement.
- Clarified `project lead`, professional `Owner`, `Required`, `Required if…`, and `Optional` role semantics for international users.
- Kept model changes actionable with complete model names and reasoning efforts.
- Kept Skill discovery read-only by default and separate from installation or execution.

### Validation status

- The runtime and frozen 5-case / 7-run validation package passed independent static review with 0 major / 0 minor / 0 blocker.
- A separate project-scoped Codex Desktop visible check completed six fresh tasks with the same candidate: five English requests and one Chinese request. All six progress messages and complete recommendations followed the request language. This is limited real-host evidence, not a statistical guarantee or cross-host validation.

## 1.0-beta7 - 2026-08-11

- Published the first public beta source snapshot.
- Included the five-file Chinese runtime Skill, repository README, custom non-open-source license, and SHA-256 manifest.
- Did not create a Tag or Release.

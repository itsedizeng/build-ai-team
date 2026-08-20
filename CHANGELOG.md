# Changelog

All notable user-facing changes to Build AI Team are documented here.

The project follows [Semantic Versioning](https://semver.org/).

## Unreleased

## 1.1.0 - 2026-08-20

### Changed

- Allow Codex to match Build AI Team automatically for substantive requests whose structure clearly depends on team planning, professional ownership, permission separation, independent validation, or parallel work.
- Keep `$build-ai-team` as the reliable explicit fallback because automatic Skill selection still depends on host matching.
- Keep simple bounded direct tasks, ordinary discussion or mention, explicit negation, and `TOOLKIT_MODE=member` work outside the team-planning workflow.
- Route matching requests to the narrowest of four modes: full setup, existing-team change, model advice, or Skill advice.
- For a confirmed same-project team, return only an `add`, `merge`, `replace`, or `keep` delta and require precise confirmation before any persistent-task change.
- Use only host-exposed metadata for local Skill advice; read public-search guidance and browse only after an explicit public-search request.
- For every recommended public Skill, show a compact maintenance status and its read, write, and external-action boundary; mark unknown evidence as `unknown` rather than inferring safety.
- Preserve the existing plan-first confirmation gate: automatic selection does not create tasks, install Skills, access private data, or perform external actions.
- For a confirmed replacement, require the confirmation action to list the safe sequence: keep affected tasks, create and verify the replacement, update and confirm affected assignments, re-check states, and archive the old task last without deletion.

### Validation status

- The five-file runtime passed independent static review with 0 major / 0 minor / 0 blocker.
- The frozen nine-case / nine-context / ten-response implicit four-mode package passed independent static review with 0 major / 0 minor / 0 blocker.
- The baseline model batch completed 9/9 technical runs and 10/10 responses. Its original frozen content result remains historical; a later control-boundary review separated host-only observations and test-scope overreach from candidate behavior, while preserving one real public-Skill output ambiguity and one single-run model-formatting observation.
- After changing only `skill-discovery.md`, a fresh two-case / three-context / five-response differential batch passed 3/3 technical runs and independent content review with 5 pass / 0 minor / 0 major / 0 blocker.
- A later narrow `SKILL.md` change was independently checked with a fresh saved-project two-turn dynamic replacement test: 1 pass / 0 minor / 0 major / 0 blocker. It verified creation and acknowledgement of the replacement, acknowledgement of the affected current assignment, a state re-check, and archival of the old task last without deletion.
- This is combined differential evidence, not a claim that the final candidate reran the complete nine-case set. Existing `v1.0.1` evidence applies only to unchanged behavior.

## 1.0.1 - 2026-08-15

### Changed

- Refocused the README opening on user outcomes: the smallest reliable persistent team, role-specific model routing, source-aware Skill discovery, explicit invocation, and separated permission steps. Runtime behavior is unchanged.
- Clarified that the Skill is optimized for diverse project scenarios across software, product, design, research, data, content, migrations, and releases. Runtime behavior is unchanged.
- Treat an initial recommendation as a standalone request unless the user explicitly continues or reuses the same confirmed project.
- Prevent shared directories, similar titles, previous tasks, memory, or prior team plans from silently changing the current scope, team, ownership, user execution responsibilities, permissions, or dependencies.
- Keep optional capabilities found only in unverified history as unconfirmed branches rather than current responsibilities, dependencies, or scope assumptions.
- Reuse a persistent task only after its existing assignment is verified to match the same confirmed project goal and scope.

### Validation status

- The five-file runtime passed independent static review with 0 major / 0 minor / 0 blocker.
- Targeted differential checks covered explicit new projects, an ordinary first request, a clean project, and explicit continuation. Four unaffected cases passed on the preceding candidate; after the only failing path was narrowed, the final candidate passed an independent fresh protection check for that path.
- This is combined differential evidence, not a claim that the final candidate reran the complete test suite.

## 1.0.0 - 2026-08-13

### Added

- Stable single-agent and multi-agent planning with explicit ownership, dependencies, collaboration, model recommendations, and permission boundaries.
- Separate `Suitable Local Skills`, offline public leads, and user-requested external public Skill search with provenance, maintenance-signal, and permission-risk review.
- A compact collaboration map for multi-agent recommendations.

### Changed

- Reuse the planning conversation as the substantive project-lead role when applicable, create only the other current required persistent tasks, and use role-only task titles.
- Treat actual persistent tasks as the live team state. Team creation no longer creates or modifies `AI_TEAM.md`, a roster, a plan, or another project document.
- Keep future add-member suggestions as confirmed deltas against the actual persistent tasks and latest confirmed plan; do not reconstruct a roster from project documents.
- Keep Token-saving guidance limited to concrete lower-cost model and reasoning-effort configurations. Do not put scripts, automation, commands, or process advice in that field.
- Keep external Skill search separate from the local list and preserve the plan’s primary next-step action after search.
- Localize generic professional and capability terms while preserving exact technical identifiers.

### Validation status

- The five-file runtime passed independent static review with 0 major / 0 minor / 0 blocker.
- Minimal project-scoped Codex Desktop validation covered six core behavior gates with 0 minor / 0 major / 0 blocker.
- After project-document team state was removed, a fresh differential validation of the final build passed five behavior gates with 0 minor / 0 major / 0 blocker and confirmed zero project-document writes.
- These checks are limited real-host evidence, not a statistical guarantee or cross-host validation.

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

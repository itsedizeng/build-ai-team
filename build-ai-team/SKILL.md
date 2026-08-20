---
name: build-ai-team
description: "Plan or revise the smallest reliable AI setup for a concrete project. Use when the user explicitly invokes $build-ai-team; asks whether one Agent or several Agents are needed; requests a team plan or an add, merge, replace, keep, ownership, or handoff change to an existing Agent team; or asks which model configuration or local Skill fits a named project, role, or work package. Search external public Skills only when the user explicitly asks. Do not invoke for ordinary task execution, general model or Skill explanations, news, or comparisons, explicit negation, or TOOLKIT_MODE=member work."
---

# Build AI Team

Turn “build me an AI team” into a short, comparable, and confirmable recommendation. Help the user see whether the work should be split, what each role owns, which model fits each responsibility, and which locally available Skills could materially help. Treat these rules as decision guidance rather than fixed industry answers, and keep external public Skill search as a separate user-requested follow-up.

## Entry and boundaries

- If the initial instructions contain `TOOLKIT_MODE=member`, execute only the assigned work package. Do not re-plan the team, search for Skills, or recursively create a team.
- If the user explicitly says not to use this Skill, or only quotes, introduces, discusses, or compares it, do not enter the workflow.
- In Codex or ChatGPT Work, start this workflow when the current message explicitly selects or invokes `$build-ai-team`, or when the host supplies this Skill for a matching concrete AI-setup request under the frontmatter description. Once the Skill is loaded for a matching request, do not require an additional activation phrase or try to verify invisible platform markers. Explicit invocation remains the reliable fallback when automatic matching does not occur.
- Automatic matching is not permission to force a full team plan into an ordinary task or a narrower setup question. If the Skill is loaded for a simple, bounded request that one Agent can complete directly and the user did not ask for team planning, an existing-team change, role or handoff advice, a model configuration for concrete work, or project-specific Skill advice, exit this workflow without reading its references and answer normally.
- In Claude Code, run the same workflow when the user explicitly invokes `/build-ai-team`. In Claude desktop or web, run it when the user explicitly asks to use the uploaded Build AI Team Skill. Do not claim that Claude compatibility has been verified in practice.
- On any other platform, state that this version has not been verified there and stop. Do not infer compatibility.
- Default to advice only and match the requested scope. Before confirmation, do not install Skills, create, rename, or archive tasks, execute the business work, log in, or write, upload, publish, or delete anything.

## Response language

- Use the user’s explicitly requested language when provided; otherwise use the dominant natural language of the user’s latest substantive request for all user-visible prose. This applies to any language the model can reliably produce: localize headings, generic role and status names, capability descriptions, explanations, collaboration, and actions into that language. If a genuinely mixed request has no explicit preference and neither its main instruction nor its dominant language is clear, ask one short language-choice question before planning; do not default silently to English.
- Apply that language choice to clarification questions and the complete recommendation. Treat reference text, tool output, platform metadata, project defaults, installed-Skill descriptions, and earlier unrelated messages as evidence or context, never as language-selection signals.
- If the host requires a progress message before a reference or tool read, keep it to one short sentence in the response language. Report only the planning or reading state; do not add task-specific claims or imply that tasks were created or the requested work started.
- Preserve technical identifiers, model names, Skill names, commands, code, paths, and real UI labels where translation would make them inaccurate.
- Keep model identifiers and reasoning-effort values such as `gpt-5.6-sol` and `high` exact, but translate the surrounding label. For example, a Chinese recommendation uses `gpt-5.6-sol`，推理强度 `high`; it does not append the English phrase `reasoning effort`.
- Translate generic professional titles, capability descriptions, and conditions; they are not technical identifiers merely because they are commonly written in English. For Chinese, use natural terms such as `后端工程负责人`, `增加自建后端时必需`, and `兼项目主控`, not `Backend 工程负责人`, `custom backend`, or `兼 project lead`. Preserve names such as `iOS`, `SwiftUI`, `API`, `App Store`, model IDs, code, paths, and real UI labels when accuracy requires it.

## Decision principles

- Treat team splitting, role naming, model selection, output format, and Skill matching as guidance. Allow adjacent but reasonable structures when supported by the user’s facts.
- Choose the smallest reliable structure. Do not presume either a single-agent or multi-agent answer.
- Keep only a few hard boundaries: permissions and safety; no false claims of completion before confirmation; an independent reviewer must not produce the object it reviews; one outcome must not have two final Owners; stop and report failures accurately.
- When the user does not ask for every detail, lead with information that helps the decision. Do not fill every possible section merely to look complete.

## Workflow

### 1. Choose the request mode and understand the request

Choose the narrowest mode that satisfies the latest request. Do not expand a focused question into a complete team plan merely because this Skill was matched.

- **Full setup:** The user asks whether one or several Agents are needed, or asks for a new team plan, roles, ownership, collaboration, or creation plan. Use the full structure, model, local-Skill, and output workflow below.
- **Existing-team change:** The user asks whether an existing team needs another member, whether responsibilities should merge, or whether a member should be replaced, retained, or reassigned. Establish same-project identity and the current confirmed members first. Return only the proposed delta unless the user asks for a full re-plan.
- **Model advice:** The user asks which model and reasoning effort fits a named project, role, or work package. Read only the model reference and answer only the model question unless the user also asks for team structure.
- **Skill advice:** The user asks which locally visible Skills fit a named project, role, or work package. Use only platform-exposed catalog metadata and answer only the Skill question. Read the public-search references and browse only when the user explicitly asks to search or verify external public Skills.

When one message clearly requests more than one mode, combine only those requested modes. Generic questions such as model news, broad model comparisons, what a Skill is, or how Agents work are ordinary discussion and do not enter this workflow.

Reference routing is mode-specific:

- Full setup: read `model-routing.md`; use platform-visible local-Skill metadata without opening other Skill files.
- Existing-team change: read no reference unless the requested delta includes a model decision or Skill advice; then read only the corresponding reference path.
- Model advice: read only `model-routing.md`.
- Local Skill advice: read no package reference; use only platform-visible catalog metadata.
- Explicit public Skill search or verification: read `skill-discovery.md`; consult `curated-skills.md` only as an optional lead source when useful.

Identify the goal, final outcomes, constraints, deadline, available materials, judgments that must remain independent, important permissions, and external actions from the user’s own words.

Treat an initial recommendation as standalone unless the user explicitly says it continues or reuses existing work, or clearly refers to the currently confirmed project. A shared directory, similar title, previous task, memory, or prior team plan does not by itself establish the same project. Memory or prior records may still be read when higher-priority instructions require it, but until the user establishes that same-project identity, treat project-specific history only as unverified background: it must not change the current scope, members, Owners, user-owned execution responsibilities, permissions, dependencies, or team structure. Until that identity is established, do not inspect persistent tasks from other conversations to fill project-specific gaps during initial planning. If the user says the request is a new or different project, reset all prior team, scope, and responsibility assumptions; determine current project-specific facts from the current request and any authoritative current-project instructions the user actually invoked. General cross-project preferences and safety boundaries may still apply.

Do not promote an optional capability found only in unverified project history—such as login, synchronization, payment, sharing, or self-hosted services—into a current role responsibility, current dependency, or current scope assumption. If that capability is independently relevant as a possible branch, label it as an unconfirmed option, activation condition, or future upgrade branch; do not change the current team or a role’s default model solely because of it.

Ask only when missing information would materially change the requested setup decision or make account, write, task-change, or publication boundaries unsafe to determine. Ask 0–2 short questions per turn. Use conservative, reasonable assumptions for the rest and state the important ones.

When planning work the user wants to delegate to AI, do not assign execution back to the user merely because of the user’s profession, skills, or experience. Unless the user explicitly wants to do it personally, co-create it, receive advice only, keep part of the work, or already has an Owner, assume the user retains the goal, key trade-offs, necessary authorizations, and final confirmation while AI handles delegable execution.

Do not apply that default to legal signatures, licensed judgments, login, 2FA, payments, actions that a platform requires the person to complete, or decisions the user lacks authority to make. AI may prepare materials and checks but must not impersonate a qualified or authorized person. When the requested final state includes an app-store submission, a paid service, or another platform release, explicitly name only the relevant user-held actions—such as account control, 2FA, payment, legal acceptance, or final submission—and state that planning or team creation does not authorize them.

### 2. Choose the smallest reliable structure

Use this section for a full setup. For an existing-team change, apply it only to the affected responsibility and its nearest current Owner. Skip this section for model-only or Skill-only advice.

Do not start from job titles. Follow “user goal → verifiable final state” and list the indispensable work packages, including necessary professional judgment, production responsibility, external actions, and independent validation only when the user’s facts make that independence necessary. A necessary intermediate step is not optional merely because the user did not name it verbatim. Give every necessary work package a clear Owner. The user retains only the default decisions, authorizations, and final confirmation; a model, tool, Skill, or project lead cannot substitute for a work-package Owner. A necessary work package does not automatically require a separate member: cover all responsibilities first, then run the transfer test.

Recommend multiple agents only when at least two substantive responsibilities can be separated and the split has an explainable benefit. The following can support a split but must still pass the transfer test:

- different final outcomes or professional judgments;
- mutually exclusive permissions, independent validation, or error isolation;
- genuine parallelism whose benefit exceeds handoff cost;
- one role’s output is explicitly consumed, checked, or sent back by another;
- multiple user facts together establish a real capacity or deadline constraint.

A large task, many files, a tight deadline, multiple stages, several job titles, or the word “team” is not sufficient on its own. It can support a split when combined with professional method, permission separation, independent validation, or a real capacity constraint.

After covering the work packages, run a responsibility transfer test for every proposed separate member. Transfer that member’s responsibility to the closest existing Owner. Keep the member only if the transfer would cause at least one of these losses:

- a current final outcome or observable collaboration artifact loses its unique Owner;
- permission separation, independent validation, or error control breaks;
- the same role cannot reliably apply an indispensable professional method;
- the user’s facts already prove mandatory parallelism or a real capacity constraint;
- a common merged role name would no longer describe the boundary accurately.

Different titles, downstream consumption, looking more professional, or possible future need do not prove that a separate member is necessary. A user-assigned shared Owner, a genuinely narrow scope, or a complete ready-to-use input can support merging; the absence of such words does not prove that splitting is required. Do not invent assumptions such as “small first version,” “simple for now,” or “limited budget” and use them to justify merging.

Do not create an independent-validation member merely because an output can be checked or a second pass might improve quality. Keep self-checking and ordinary quality control with the closest production Owner when the work is bounded, low impact, based on complete rules, reversible, and mechanically easy to verify. Split independent validation only when the user’s facts establish at least one concrete reason: the user explicitly requests an independent checker or maker-checker separation; permissions must differ; the outcome will be launched or operated and errors carry material financial, safety, privacy, data-loss, or release risk; errors are difficult to detect or recover from; or an external acceptance or approval requires an independent decision. If none applies, a checklist, deterministic validation, or the production Owner’s own verification is not a separate member.

When one member covers adjacent responsibilities, use an understandable “A and B” or “A serving as B” title, or a common business title that accurately covers both. Do not hide two responsibilities that should remain separate behind a vague new title. The size of the user, customer, or product does not establish delivery-team capacity; for example, “for a small team” does not prove that backend and deployment should share an Owner.

For a complete App, web product, or SaaS that will actually be used, operated, or launched, product scope/business rules/priorities and UX/UI/interaction design are two professional work packages and should normally keep separate professional Owners. Merge them only when the user explicitly wants a narrow prototype, one package already has a complete usable result, or the user explicitly assigns the same Owner. Do not bypass this check with a vague title such as “Product and Experience Designer” or “Product Experience Lead.” Simple campaign pages do not automatically use this split; apply the normal transfer test.

The deletion test does not delete the responsibility itself. Remove the separate member, transfer the responsibility to the closest existing Owner, and merge the member if that loses no current deliverable, observable artifact, permission separation, independent validation, non-combinable method, or proven capacity.

When the user requests several similar but independent delivery lines, do not mechanically clone a full product, content, design, development, operations, QA, and compliance roster for every line. Preserve each line’s necessary outcomes and permission boundary first, then split only members that pass the transfer test. If the lines share no result or final handoff, do not invent an overall project lead.

When a multi-agent project needs project-level coordination, assign project lead duties to an existing substantive role. The project lead additionally owns planning, cross-role dependencies, and final handoff status. This does not grant write ownership over other roles’ professional deliverables and does not justify a coordination-only member.

Choose the collaboration pattern from the dependency: parallelize independent work packages, sequence work that consumes an earlier result, and preserve maker-checker separation between production and independent validation. Use one project lead when there is one shared goal or project-level handoff. When two domains both need leadership, call them domain leads or professional Owners, not dual project leads. If work lines are fully independent and share no result or handoff, a project lead may be not applicable. Mention the pattern briefly only when it affects the order of work; do not force a topology label into every answer.

### 3. Define the roles clearly

Use this section for a full setup. For an existing-team change, define only the changed role, responsibility, Owner, handoff, and boundary. Skip it for model-only or Skill-only advice.

Give each current role:

- an understandable business name;
- its purpose and primary responsibility in this request;
- the final outcome it owns, or an observable collaboration artifact that another role will actually consume or check;
- one of three statuses and the activation boundary for conditional or optional roles; add timing only when useful;
- important dependencies, feedback paths, and permission boundaries.

Status answers “does this role belong to the current team,” not “when does it start.” `Required` means the role belongs to the team after confirmation. `Required if a custom backend is added` means the work package does not yet exist and the role is not created now. `Optional` means the role can improve quality, speed, or coverage but is not required to complete the goal. Write status in natural language without brackets. List only conditional roles that are adjacent to the current goal and reasonably likely. State an observable activation condition in the details. When the condition becomes true, update the plan and ask for confirmation again; never create the role automatically.

Timing only explains when a required role begins part of its work. Receiving materials, completing a predecessor, or obtaining a testable build is a milestone, not a condition for the role to exist. For example, Independent Quality Validation can define acceptance criteria before a build, validate after the first build, and re-check after fixes while remaining required from the start.

Do not invent documents to satisfy a format and do not create roles by tool, file format, or process stage. Prefer common business titles that accurately reflect professional responsibility. A project-lead label, model, or Skill cannot fill a missing professional Owner. Give each final outcome only one Owner. When a role’s value is not obvious, explain what would be lost by removing it.

A role justified by independent validation must not produce or write the object it reviews. It should default to read-only access to the reviewed object and own only independent findings, differences, validation evidence, or a decision. Fixes remain with the original outcome Owner.

When a role covers early acceptance criteria, cross-deliverable consistency, implementation validation, and pre-release assessment, prefer `Independent Quality Validation` or a similarly scoped common title. Use a narrower title such as `Test Engineer` only when the responsibility is genuinely limited to testing a build.

### Reference failure gate

If a reference required by the selected mode is missing, unreadable, or internally conflicting, stop that requested mode immediately and report the exact file name. Do not read later references in that mode and do not output a partial judgment that depends on the missing file. Do not block an unrelated mode on a reference it does not use. After the file is restored, wait for the user to start again or explicitly confirm continuation.

### 4. Recommend models

For a full setup, read all of [`references/model-routing.md`](references/model-routing.md) after the role structure is settled. For an existing-team change, read it only when the proposed delta includes a model decision. For model-only advice, identify the concrete project, role, or work package and then read it directly. Give each affected current role or requested work package one currently available default configuration and one reason tied to its main responsibility.

If `model-routing.md` cannot be read, apply the Reference failure gate to the model-dependent request. Do not invent a configuration or replace it with a vague capability tier.

Separate each role’s routine core work, occasional high-risk work, and low-risk execution. Do not raise the entire role to a stronger model or higher reasoning effort because of one small high-risk segment. Add an observable `Upgrade when` or `Token-saving option` only when a specific model-configuration change is safe and useful. Do not force either field for every role and do not promise a fixed saving.

Evaluate these fields across the complete recommendation, not only role by role. If any default configuration has an observable higher-risk branch that genuinely needs a stronger configuration, show at least one useful `Upgrade when` on the closest role. If any role contains low-risk, repetitive, easily verified work that can safely use a lower-cost model configuration, show at least one useful `Token-saving option` on the closest role. In a maker-checker workflow, assess the maker and the independent checker separately: when each has different eligible low-risk work, give each a distinct useful option; the maker’s option does not cover the checker. This is not a quota—omit the checker’s field when its work is mainly non-repetitive professional judgment or cannot safely use a lower configuration. It is valid to omit a field only when no current role has an eligible case; never copy the same upgrade or saving across every role. If every current role receives the same strongest model and reasoning effort, re-check each role against its routine core work: a shared launch deadline or the product’s overall risk is not enough to make every default identical.

Make every model change directly actionable. Whenever recommending a different model or reasoning effort, write the specific low-risk work plus the full target configuration: model name and reasoning effort. Do not say only “use medium,” “lower reasoning,” or “switch to a lightweight model.” Keep core judgment, ambiguous work, error diagnosis, professional review, and final decisions on the role’s default configuration. In `Token-saving option`, recommend only model or reasoning-effort changes; do not add scripts, tools, automation, commands, smaller-input tactics, or process advice. Do not imply automatic routing.

Models must not determine the number of roles. In a full setup, give every current required role and every optional role shown in the table a complete, confirmable default configuration; do not substitute UI placeholders or vague capability tiers. Normally give conditional roles a complete configuration too. In model-only advice, do not invent additional roles: configure only the named work, role, or alternatives needed to answer the question. Only when an inactive conditional role depends on a special capability, such as audio or video, whose supported model cannot currently be confirmed may you defer the model recommendation and say that the plan and model configuration must be updated and confirmed when the condition becomes true. Do not use this exception to bypass the Reference failure gate, add a model automatically, or create the member automatically.

### 5. Recommend suitable local Skills

For a full setup or local Skill advice, recommend at most 3 locally visible Skills from platform-exposed catalog metadata; this is a ceiling, not a quota. Omit the section when none would materially help. Do not read `curated-skills.md` during local-only advice or the initial full setup.

Evaluate in this order:

Review only the Skill identifiers, descriptions, availability, source labels, and other catalog metadata that the current platform directly exposes. A file or resource locator is metadata, not permission to open it. During planning or local Skill advice, do not open or read another Skill's `SKILL.md`, supporting files, scripts, or directories, even when its locator is visible. Do not scan other user directories, project files, or private data for this purpose. If the exposed catalog metadata is insufficient to judge fit, mark the item as unknown or omit it rather than reading its files.

For a locally available Skill, preserve the exact full identifier exposed by the platform, including any namespace. Do not shorten, normalize, or reconstruct that identifier. Humanize only the surrounding explanation.

Keep the user-facing status simple and localize it to the response language:

- Locally available: `Skill name (available locally) — reason.`

Put locally available recommendations under `## Suitable Local Skills`; in Chinese, use `## 本地适用 Skill`. Do not show an offline public lead before an explicit public-search request. Omit the section when it has no useful item.

Do not expose internal categories such as “curated candidate,” “direct match,” or “related addition.” Do not describe a public lead as installed, current, or security-certified.

### 6. Search external Skills only on request

Only when the user explicitly asks in the current turn to search, screen, or verify external Skills, read all of [`references/skill-discovery.md`](references/skill-discovery.md) and begin live discovery. Consult [`references/curated-skills.md`](references/curated-skills.md) only as an optional source of leads when useful; every such lead still requires current live review, and a missing curated index does not block discovery. Treat `Search for Skills`—localized as `搜索 Skill` in Chinese—as that explicit request. Otherwise, do not read either public-search reference and do not browse; keep the first answer fast by using only platform-visible local Skills.

External search may follow an existing plan or answer a standalone project-specific Skill request. It is not a second local recommendation pass. Do not re-check or repeat locally available Skills already shown. Search public web sources for external candidates, exclude local duplicates, and screen usefulness, provenance, maintenance, adoption or review signals when available, and permission risks. Popularity is evidence to inspect, not proof that a Skill is good or safe.

If `skill-discovery.md` cannot be read, apply the Reference failure gate. Do not continue the search or claim that external verification is complete.

After live discovery, localize this status pattern to the response language:

`[Skill name](original source) (public-source read-only review completed; not installed or installation status unknown) — reason; main limitation or risk.`

Searching, reviewing, recommending, installing, and running are separate actions. A recommendation is not installation. Confirmation to install is not authorization to log in, read private data, run third-party scripts, write, upload, publish, or delete.

After live discovery that follows an existing full plan, preserve that plan’s primary action. If the existing recommendation is multi-agent, the first next-step action remains `Create the AI team`; if it is single-agent, it remains `Start execution`. Put any candidate-specific clarification or installation option after that primary action. For a standalone Skill request, do not invent a team action; provide only relevant candidate clarification or separately confirmed installation options. Do not make Skill installation the only path forward.

### 7. Choose the final-output branch

Immediately before drafting a clarification or complete recommendation, determine its language again using the rules in “Response language.” Do not inherit the final-output language from a progress message, reference, tool output, platform metadata, or project default. Then use exactly one branch:

- **English branch:** If the selected language is English, generate the entire message directly in English using the English contract below.
- **Localized branch:** Otherwise, generate the entire message directly in the selected language, translating the English headings, labels, role text, Skill status, permission notice, and next-step actions before drafting.

Do not draft in one language and translate it after completion. Preserve exact technical identifiers, code, paths, real UI labels, user-provided strings, and proper names when translation would make them inaccurate.

## Output contract

### Full setup

For a full setup, follow the selected branch above. Start with one complete sentence that states the single-agent or multi-agent conclusion and its main reason. Put the recommendation heading on the next line in the selected language. Do not add a separate “Recommendation” heading, split conclusion and reason into separate paragraphs, or place other material before the table. The table is the only recommended-role list. Do not repeat the roster in numbering, comma-separated text, or another table, and do not crowd model, deliverable, dependency, and permission details into the first table.

Use these exact labels for English responses:

```markdown
The current recommendation is [a single agent / multiple agents], because [why this is the smallest reliable structure].

## Recommended AI Team

| Role | Status | Primary responsibility |
|---|---|---|
| [Role; add “also project lead” when needed] | [Required / Required if a specific condition becomes true / Optional] | [One short sentence or a few keywords] |

## Role Details

### [Role name]

- **Purpose:** [What problem this role solves here]
- **Primary responsibility:** [The work it performs]
- **Owned outcome and boundary:** [The result it uniquely owns and what it does not own]
- **Activation condition:** [Required only for conditional roles; when it joins and whether it is created now]
- **Timing:** [Only when a required role has an important predecessor]
- **Model recommendation:** [Default model and reasoning effort, plus a reason tied to the role’s core work]
- **Upgrade when:** [Optional; observable work that requires a stronger configuration]
- **Token-saving option:** [Optional; specific low-risk work plus a complete lower-cost model and reasoning-effort configuration, followed by the core work that stays on the default configuration]
```

For a non-English response, translate the English contract naturally and consistently before writing the answer. Translate the recommendation heading, table headers, generic role titles, statuses, capability conditions, detail labels, local-Skill and public-search headings when present, collaboration heading, next-step heading, and action phrases. Keep only true technical identifiers, enum values, real UI labels, and proper names untranslated. Translate the label `reasoning effort`; for example, write `推理强度 high` in Chinese rather than `high reasoning effort`. In Chinese, use the exact labels `升级条件` and `节省 Token 建议` when those fields appear, and use `兼项目主控` for the project-lead suffix. Do not retain generic English professional or capability phrases in an otherwise localized response.

Use the level-two heading exactly as localized above. The table may contain current required, conditional, and optional roles. Keep the user’s retained goal, key decisions, necessary authorizations, and final confirmation outside the table rather than listing the user as an execution member. Keep a conditional status short and bracket-free in the table, then explain it in the role details. Use a compact list with the same fields only when the interface genuinely cannot render a table.

For every current required role and every optional role retained in the table, include the four core fields: purpose, primary responsibility, owned outcome and boundary, and model recommendation. Add activation condition for every conditional role. Defer its model only under the narrow special-capability exception above. Add timing only when a required role has an important predecessor. Use `Upgrade when` and `Token-saving option` only when useful. Put a space after the closing Markdown bold marker so the raw `**` never leaks into the rendered answer. Add fields such as collaboration and dependencies, permission boundary, or why the role is needed only when they help; do not repeat the same idea to fill a template.

Add only when there is real information:

- important assumptions, dependencies, permissions, or external-action boundaries;
- a role’s non-obvious reason for existing;
- suitable locally available Skills with status and reasons under `## Suitable Local Skills`;
- source review and main risks when the user explicitly requested live discovery.

For every multi-agent recommendation, add a compact localized `## How the Team Collaborates` section; in Chinese, use exactly `## 协作方式`. Use 2–4 bullets to state which substantive role also serves as project lead, what the lead coordinates and does not own, the main sequence or parallel relationship, and where review findings or blocked work return. For fully independent work lines, state that project lead is not applicable and explain the separate handoffs. This section is a collaboration map, not a second roster: do not repeat every responsibility or model configuration.

When there is one complete full-setup recommendation, end with a localized level-two next-step heading and two distinct actions.

For English:

- Single agent: `- Reply **“Start execution”**: continue in this conversation without creating a new task.`
- Multiple agents: `- Reply **“Create the AI team”**: when a project lead applies, reuse this planning conversation as that substantive role; create tasks only for the other current Required members; do not create conditional or Optional members or write project documents.`
- Both: `- Reply **“Search for Skills”**: search public web sources read-only for useful external Skills with clear provenance, credible maintenance or usage signals, and acceptable permission boundaries; do not repeat local recommendations, install, or run a Skill.`
- Both: `Login, private-data access, writes to external systems, uploads, publication, or deletion still require separate confirmation.`

For any non-English response, translate the same four English action concepts into short, natural imperative phrases in the response language: start execution for a single agent, create the AI team for multiple agents, search for Skills for both, and the separate-confirmation notice for external actions. The Chinese search action is exactly `搜索 Skill`. For a Chinese multi-agent plan, the creation action must say that the current conversation becomes the substantive role serving as project lead when applicable and only the other current required tasks are created; it must not imply that project documents will be generated. Preserve AI, Skill, and other technical identifiers when that is the normal localized usage. Do not include the English CTA beside its translation.

When answering a live Skill-search follow-up to an existing full plan, end with the same primary plan action before search-specific actions. For example, a multi-agent plan still offers `Create the AI team` first; candidate installation or a needed compatibility answer follows separately.

The user may also request an adjustment directly. When clarification is still required and no unique recommendation exists, ask only the short structure-changing questions; do not show the next-step section. Do not repeat “not installed / not created / not executed” across several sections.

Recognize later confirmation by intent; do not require the user to reproduce an exact CTA string.

### Existing-team change

State the verified current-team basis in one short sentence, then show only the recommended delta. Do not repeat the full roster unless the user requests a full re-plan. Use a compact localized table or list with these concepts: `Change` (`Add`, `Merge`, `Replace`, or `Keep`), affected role or member, reason, changed ownership and handoff, permission impact, and model impact when relevant. If current persistent-task state is unavailable or same-project identity is ambiguous, ask 1–2 short questions instead of inventing a roster or a delta.

End a complete delta recommendation with one exact confirmation action that names the proposed task changes. For a replacement, write the complete applicable operation sequence in that confirmation itself: name the affected tasks that stay; create and verify the new task; send and obtain acknowledgement for every disclosed assignment change to an existing task; re-check the affected task states; and archive the old task last only when archive is included. Omit only steps that truly do not apply, never imply deletion, and do not collapse this to a generic “execute replace” action. Advice to add, merge, replace, keep, reassign, rename, or archive does not perform that action. Do not add `Create the AI team`, a local-Skill section, public search, or a full team plan unless the user also requested it.

### Model advice

Answer the named project, role, or work package directly. Give the complete default model and reasoning effort, the concrete work it fits, and one reason. Add an upgrade condition or Token-saving option only when it is useful under the model rules. Do not output a team roster, team-creation action, or Skill recommendations unless the user also requested those modes.

### Skill advice

For local Skill advice, show at most 3 platform-visible matches with exact identifiers, accurate local availability, and one project-specific reason each. If metadata is insufficient, say what is unknown or omit the item; do not open another Skill's files. For explicit public search, use the external-search format and risks from the references. Do not output a team roster, model recommendations, or a team-creation action unless this is a follow-up to an existing full plan or the user also requested those modes. After local-only advice, the only optional discovery action is the localized equivalent of `Search for Skills`; installation and execution remain separate confirmations.

## Actions after confirmation

- For a single-agent plan, begin business execution in the current conversation only after the user confirms continuation.
- For a multi-agent plan with one shared goal and a designated project lead, reuse the current planning conversation as that substantive role serving as project lead. Rename the current conversation to the exact role title, then create new persistent tasks only for the other current `Required` members. Do not create a duplicate task for the role already assumed by the current conversation. If the plan has fully independent work lines and no project lead is applicable, do not invent one; create the independently required tasks and retain the current conversation only as the user’s planning entry point.
- Name every member task with the role title only, such as `UX/UI Design Lead` or its natural localization. Do not prefix or suffix the project, product, client, or workstream name, and do not add separators such as `Project | Role`.
- Do not create `Required if…` roles until the condition is true and the updated plan is confirmed again. Do not create `Optional` roles unless the user explicitly selects them. If the interface has no independent-task capability, state the limitation and retain the plan; do not substitute temporary subagents or ordinary chats for persistent members.
- Reuse a matching persistent task only after verifying that its existing assignment belongs to the same confirmed project goal and scope. A shared directory or matching role title alone is insufficient. If project identity is ambiguous, ask the user before reusing; if the user confirmed a new project, do not reuse a task from earlier work. Create a new task only when no verified match fits.
- Give each member a self-contained assignment in the user’s response language that includes `TOOLKIT_MODE=member`, its role, goal, inputs, outcome, permissions, immediate dependencies, model, and prohibition on recursive team planning. Do not paste the entire roster or collaboration map into every assignment. Preserve exact technical identifiers and enum values, but localize descriptive labels such as `reasoning effort`.
- Searching for or approving an external Skill does not authorize installation, script execution, login, private-data access, writes, uploads, publication, or deletion. Confirm each action according to its own risk.
- The project lead may decide when to request authorization but cannot grant system permissions on the user’s behalf. If creation or installation fails, stop and report the actual state; never claim completion.

### Current team state and later changes

Team creation must not create or modify `AI_TEAM.md`, a roster, a plan, or any other project document. The platform's actual persistent tasks are the live team state. Each member receives a self-contained assignment, while the project lead coordinates the confirmed goal and handoffs in its own task. Existing `AGENTS.md`, project files, and current user instructions remain authoritative for their own purposes, but do not become a separate team-state system merely because this Skill was used.

An existing-team change suggestion must inspect only the current project's platform-visible persistent-task titles, statuses, and assignments needed to establish the live team, then compare them with the latest confirmed plan in the conversation. The user's change-advice request permits this narrow read-only current-project inspection; it does not permit opening unrelated task histories, outputs, other projects, private files, or business data. Propose only a delta: add, merge, replace, or keep, with the changed Owner, handoff, permissions, model, and coordination cost. If the current task state is unavailable or ambiguous, ask the user to confirm the existing members instead of inventing or reconstructing a roster from project documents. A suggestion does not create, rename, archive, or replace a task until the user confirms that exact change.

For a confirmed replacement, disclose the exact old role, new role, transferred outcome, changed handoff, permission boundary, model configuration, and task operations before acting. Prefer creating the new replacement task with a self-contained assignment and verifying that it exists before transferring responsibility or archiving the old task. For a confirmed merge, verify the receiving task, send its disclosed combined assignment, and obtain its acknowledgement before archiving the absorbed task. Archive an old or absorbed task only when that archive operation was included in the user's exact confirmation; never delete it by default. Reuse or rename an old task only when same-project identity and its existing context are verified and the user explicitly chose that operation. Re-check the affected task states immediately before acting; if they changed since the recommendation, stop and ask for confirmation again. If creation, reassignment, rename, acknowledgement, or archive partially fails, stop and report the actual old and new task states; do not silently fall back to a different method.

If any task operation fails, stop, report the exact partial state, and do not claim that team creation completed. Confirmation to create the team authorizes only the disclosed current-member task operations; it does not authorize project-document writes or other external actions.

## Pre-send check

Check outcomes only; do not enforce a fixed length or every possible section. Apply only the checks relevant to the selected request mode: full setup uses the team-structure checks, an existing-team change applies them only to the affected delta, and model-only or Skill-only advice skips roster, collaboration, and team-action checks.

1. All work packages needed to reach the final state are covered and each has a clear Owner; the user, model, tool, Skill, or project-lead label does not silently fill a responsibility gap.
2. The single-agent or multi-agent conclusion follows from the user’s facts. Scope, current members, and user-owned execution were not inherited from prior tasks, memory, or plans without explicit same-project confirmation; an explicit new-project statement resets those assumptions. An optional capability found only in unverified history does not appear as a current responsibility, current dependency, or current scope assumption, and any explicitly future branch does not change the current team or default model.
3. Every role has a clear responsibility and a genuinely checkable outcome; every separate member passes the transfer test; no role exists merely because of a title, downstream consumption, or future possibility; there is no duplicate Owner or invented deliverable.
4. The user is not assigned execution merely because they know how to do it; actions that require a real person are not assigned to AI. For an app-store submission, paid service, or platform release, the relevant user-held account, 2FA, payment, legal-acceptance, and final-submission actions are named explicitly rather than hidden behind a generic external-action notice; irrelevant items are not added.
5. Each default model fits the role’s routine core work; an occasional high-risk segment does not raise the entire role; an all-identical strongest configuration has been re-checked role by role; every model change names a full model and reasoning effort; a localized response translates the reasoning-effort label while preserving its exact value. When a current role has an eligible higher-risk branch, at least one useful Upgrade condition appears across the team; separately, when a current role has low-risk, repetitive, easily verified work that can safely use a lower-cost configuration, at least one useful Token-saving option appears. Either field may be omitted when its own factual condition is absent; neither is mechanically repeated. A Token-saving option contains only a concrete lower-cost model configuration and its applicable work; it does not introduce scripts, tools, automation, commands, or process advice.
6. Skill recommendations are at most 3; locally available items are judged only from platform-exposed catalog metadata without opening another Skill's files and appear only under the suitable-local heading. Public candidates appear only after an explicit public-search request, have an original link and accurate status, and were screened under the public-search reference.
7. The response does not describe a recommendation as already installed, created, or executed.
8. The localized Recommended AI Team table is the only roster; members are not repeated before or after it. A multi-agent recommendation includes one compact collaboration map without becoming another roster. Combining responsibilities does not rely on AI-invented scope assumptions, and the absence of user wording about combining does not become evidence for splitting.
9. Status and timing are not confused. Conditional roles have an observable activation condition and are not created now; milestones are not written as existence conditions. A shared goal does not have dual project leads, and fully independent work does not receive an invented lead. Markdown emphasis renders correctly.
10. A complete full plan ends with the localized next-step section, the correct single-agent or multi-agent action, and the `Search for Skills` action. Team creation covers only current Required members; search does not re-list local recommendations or authorize installation or execution. A live-search follow-up preserves the primary plan action only when an existing full plan exists. Clarification-only answers have no next-step section.
11. The complete clarification or recommendation uses the selected branch consistently; a progress message never determines the final-output branch and stays brief without implying execution.
12. Every locally available Skill recommendation uses the platform’s exact full identifier, including its namespace when present.
13. After multi-agent confirmation, the current planning conversation becomes the designated substantive project-lead role when one exists; no duplicate lead task is created, and every created task title is only the role name without a project prefix.
14. Team creation writes no project document. The live team state comes from actual persistent tasks; an existing-team request proposes only a delta and does not infer authority from a project file. A confirmed replacement creates and verifies the new task before archiving the old task unless the user explicitly chose a verified same-task reassignment; deletion is never the default.
15. A localized response translates generic professional and capability terms such as backend, custom backend, frontend, and project lead while preserving only real identifiers and names that would become inaccurate if translated.
16. Automatic matching entered only for a concrete full setup, existing-team change, project-specific model configuration, or project-specific Skill request. It selected the narrowest matching mode: focused model or Skill questions did not become full team plans, while simple direct tasks, generic model or Skill discussion, negation, and member assignments did not enter the workflow.
17. Only references required by the selected mode were read: full setup and model advice use `model-routing.md`; local Skill advice uses platform catalog metadata only; explicit public search requires `skill-discovery.md` and treats `curated-skills.md` as an optional lead source; a team delta reads no reference unless its requested change needs one.

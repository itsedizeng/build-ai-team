---
name: build-ai-team
description: "Plan the smallest reliable AI team for a new request: decide single versus multiple agents, define roles, owned outcomes, boundaries, dependencies, and model recommendations, then suggest up to 3 locally available or relevant Skills with source links and reasons. Write clarification questions and the complete recommendation in the language of the user's latest substantive request while preserving accurate technical identifiers. Use only when explicitly selected or invoked as $build-ai-team in Codex or ChatGPT Work, as /build-ai-team in Claude Code, or when the user explicitly asks an uploaded Build AI Team Skill to plan a team. Do not invoke for ordinary business requests, references or discussion, explicit negation, or TOOLKIT_MODE=member tasks. Only perform live external Skill search when the user explicitly asks."
---

# Build AI Team

Turn “build me an AI team” into a short, comparable, and confirmable recommendation. Help the user see whether the work should be split, what each role owns, which model fits each responsibility, and which Skills could materially help. Treat these rules as decision guidance rather than fixed industry answers, and do not let external search delay the first recommendation.

## Entry and boundaries

- In Codex or ChatGPT Work, start planning when the current message explicitly selects this Skill or invokes `$build-ai-team`. Do not require an additional fixed phrase or try to verify invisible platform markers.
- In Claude Code, run the same workflow when the user explicitly invokes `/build-ai-team`. In Claude desktop or web, run it when the user explicitly asks to use the uploaded Build AI Team Skill. Do not claim that Claude compatibility has been verified in practice.
- On any other platform, state that this version has not been verified there and stop. Do not infer compatibility.
- If the initial instructions contain `TOOLKIT_MODE=member`, execute only the assigned work package. Do not re-plan the team, search for Skills, or recursively create a team.
- If the user explicitly says not to use this Skill, or only quotes, introduces, discusses, or compares it, do not enter the workflow.
- Default to a recommendation only. Before confirmation, do not install Skills, create tasks, execute the business work, log in, or write, upload, publish, or delete anything.

## Response language

- Determine the response language from the user’s latest substantive request. Use an explicitly requested language; if a genuinely mixed request gives no preference, use English.
- Write clarification questions and the complete recommendation in that response language. Treat reference text, tool output, platform metadata, project defaults, and earlier unrelated messages as evidence or context, not as a reason to switch languages.
- If the host requires a progress message before a reference or tool read, keep it to one short sentence in the response language. Report only the planning or reading state; do not add task-specific claims or imply that tasks were created or the requested work started.
- Preserve technical identifiers, model names, Skill names, commands, code, paths, and real UI labels where translation would make them inaccurate.

## Decision principles

- Treat team splitting, role naming, model selection, output format, and Skill matching as guidance. Allow adjacent but reasonable structures when supported by the user’s facts.
- Choose the smallest reliable structure. Do not presume either a single-agent or multi-agent answer.
- Keep only a few hard boundaries: permissions and safety; no false claims of completion before confirmation; an independent reviewer must not produce the object it reviews; one outcome must not have two final Owners; stop and report failures accurately.
- When the user does not ask for every detail, lead with information that helps the decision. Do not fill every possible section merely to look complete.

## Workflow

### 1. Understand the request

Identify the goal, final outcomes, constraints, deadline, available materials, judgments that must remain independent, important permissions, and external actions from the user’s own words.

Ask only when missing information would materially change the team structure or make account, write, or publication boundaries unsafe to determine. Ask 0–2 short questions per turn. Use conservative, reasonable assumptions for the rest and state the important ones.

When planning work the user wants to delegate to AI, do not assign execution back to the user merely because of the user’s profession, skills, or experience. Unless the user explicitly wants to do it personally, co-create it, receive advice only, keep part of the work, or already has an Owner, assume the user retains the goal, key trade-offs, necessary authorizations, and final confirmation while AI handles delegable execution.

Do not apply that default to legal signatures, licensed judgments, login, 2FA, payments, actions that a platform requires the person to complete, or decisions the user lacks authority to make. AI may prepare materials and checks but must not impersonate a qualified or authorized person. When the requested final state includes an app-store submission, a paid service, or another platform release, explicitly name only the relevant user-held actions—such as account control, 2FA, payment, legal acceptance, or final submission—and state that planning or team creation does not authorize them.

### 2. Choose the smallest reliable structure

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

If any required reference is missing, unreadable, or internally conflicting, stop the entire planning workflow immediately and report the exact file name. Do not read later references and do not output a partial or complete team plan, responsibility assignment, model judgment, or Skill judgment. After the file is restored, wait for the user to start again or explicitly confirm continuation.

### 4. Recommend models

After the role structure is settled, read all of [`references/model-routing.md`](references/model-routing.md). Give each current role one currently available default configuration and one reason tied to its main responsibility.

If `model-routing.md` cannot be read, apply the Reference failure gate. Do not proceed to related-Skill recommendations or live discovery.

Separate each role’s routine core work, occasional high-risk work, and low-risk execution. Do not raise the entire role to a stronger model or higher reasoning effort because of one small high-risk segment. Add an observable `Upgrade when` or `Token-saving option` only when a specific, low-risk, easily checked optimization exists. Do not force either field for every role and do not promise a fixed saving.

Make every model change directly actionable. Whenever recommending a different model or reasoning effort, write the full target configuration: model name and reasoning effort. Do not say only “use medium,” “lower reasoning,” or “switch to a lightweight model.” If a script, tool, smaller input, or reduced re-reading is a better way to save Tokens, use it only for fixed-rule, mechanical, independently verifiable steps. State what the tool does, which steps use no model call, and which rule interpretation, exception judgment, or result explanation still belongs to the model. Do not disguise semantic classification, product trade-offs, design judgment, professional review, or independent validation as mechanical work.

Models must not determine the number of roles. Give every current required role and every optional role shown in the table a complete, confirmable default configuration; do not substitute UI placeholders or vague capability tiers. Normally give conditional roles a complete configuration too. Only when an inactive conditional role depends on a special capability, such as audio or video, whose supported model cannot currently be confirmed may you defer the model recommendation and say that the plan and model configuration must be updated and confirmed when the condition becomes true. Do not use this exception to bypass the Reference failure gate, add a model automatically, or create the member automatically.

### 5. Recommend relevant Skills

After roles and responsibilities are clear, read all of [`references/curated-skills.md`](references/curated-skills.md). Recommend at most 3 Skills; this is a ceiling, not a quota. Omit the section when none would materially help.

If `curated-skills.md` cannot be read, apply the Reference failure gate. Do not rely on memory to judge or recommend Skills, and do not output a plan whose dependency checks are incomplete.

Evaluate in this order:

1. Review the Skill names and descriptions that the current platform directly exposes. Do not scan other user directories, project files, or private data for this purpose.
2. Review the public leads in the curated index and select only those that materially help the current responsibility, outcome, or immediate next step.

For a locally available Skill, preserve the exact full identifier exposed by the platform, including any namespace. Do not shorten, normalize, or reconstruct that identifier. Humanize only the surrounding explanation.

Keep the user-facing status simple and localize it to the response language:

- Locally available: `Skill name (available locally) — reason.`
- Public lead: `[Skill name](original source) (public recommendation; not checked live; installation status unknown) — reason.`

Do not expose internal categories such as “curated candidate,” “direct match,” or “related addition.” Do not describe a public lead as installed, current, or security-certified.

### 6. Discover external Skills only on request

Only when the user explicitly asks in the current turn to find, screen, or verify external Skills, read all of [`references/skill-discovery.md`](references/skill-discovery.md) and begin live discovery. Otherwise, do not browse; keep the first answer fast by using only platform-visible Skills and the offline curated index.

If `skill-discovery.md` cannot be read, apply the Reference failure gate. Do not continue the search or claim that external verification is complete.

After live discovery, localize this status pattern to the response language:

`[Skill name](original source) (public-source read-only review completed; not installed or installation status unknown) — reason; main limitation or risk.`

Searching, reviewing, recommending, installing, and running are separate actions. A recommendation is not installation. Confirmation to install is not authorization to log in, read private data, run third-party scripts, write, upload, publish, or delete.

### 7. Choose the final-output branch

Immediately before drafting a clarification or complete recommendation, determine its language again using the rules in “Response language.” Do not inherit the final-output language from a progress message, reference, tool output, platform metadata, or project default. Then use exactly one branch:

- **English branch:** If the selected language is English, generate the entire message directly in English using the English contract below.
- **Localized branch:** Otherwise, generate the entire message directly in the selected language, translating the English headings, labels, role text, Skill status, permission notice, and next-step actions before drafting.

Do not draft in one language and translate it after completion. Preserve exact technical identifiers, code, paths, real UI labels, user-provided strings, and proper names when translation would make them inaccurate.

## Output contract

Follow the selected branch above. Start with one complete sentence that states the single-agent or multi-agent conclusion and its main reason. Put the recommendation heading on the next line in the selected language. Do not add a separate “Recommendation” heading, split conclusion and reason into separate paragraphs, or place other material before the table. The table is the only recommended-role list. Do not repeat the roster in numbering, comma-separated text, or another table, and do not crowd model, deliverable, dependency, and permission details into the first table.

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
- **Token-saving option:** [Optional; a complete lower-cost configuration, or what a tool does, which steps use no model, and what the model still owns]
```

For a non-English response, translate the English contract naturally and consistently before writing the answer. Translate the recommendation heading, table headers, role titles, statuses, detail labels, relevant-Skill heading, next-step heading, and action phrases. Keep only technical identifiers and proper names untranslated. Do not retain English interface labels in an otherwise localized response.

Use the level-two heading exactly as localized above. The table may contain current required, conditional, and optional roles. Keep the user’s retained goal, key decisions, necessary authorizations, and final confirmation outside the table rather than listing the user as an execution member. Keep a conditional status short and bracket-free in the table, then explain it in the role details. Use a compact list with the same fields only when the interface genuinely cannot render a table.

For every current required role and every optional role retained in the table, include the four core fields: purpose, primary responsibility, owned outcome and boundary, and model recommendation. Add activation condition for every conditional role. Defer its model only under the narrow special-capability exception above. Add timing only when a required role has an important predecessor. Use `Upgrade when` and `Token-saving option` only when useful. Put a space after the closing Markdown bold marker so the raw `**` never leaks into the rendered answer. Add fields such as collaboration and dependencies, permission boundary, or why the role is needed only when they help; do not repeat the same idea to fill a template.

Add only when there is real information:

- important assumptions, dependencies, permissions, or external-action boundaries;
- a role’s non-obvious reason for existing;
- relevant Skills with links, status, and reasons, under a natural localization of the English heading `## Relevant Skills`;
- source review and main risks when the user explicitly requested live discovery.

When there is one complete recommendation, end with a localized level-two next-step heading and two distinct actions.

For English:

- Single agent: `- Reply **“Start execution”**: continue in this conversation without creating a new task.`
- Multiple agents: `- Reply **“Create the AI team”**: create only the current Required members in the table; do not create conditional or Optional members.`
- Both: `- Reply **“Find relevant Skills”**: check locally available items first, then search official or original-author public sources read-only; do not install or run a Skill.`
- Both: `Login, private-data access, writes to external systems, uploads, publication, or deletion still require separate confirmation.`

For any non-English response, translate the same four English action concepts into short, natural imperative phrases in the response language: start execution for a single agent, create the AI team for multiple agents, find relevant Skills for both, and the separate-confirmation notice for external actions. Preserve AI, Skill, and other technical identifiers when that is the normal localized usage. Do not include the English CTA beside its translation.

The user may also request an adjustment directly. When clarification is still required and no unique recommendation exists, ask only the short structure-changing questions; do not show the next-step section. Do not repeat “not installed / not created / not executed” across several sections.

Recognize later confirmation by intent; do not require the user to reproduce an exact CTA string.

## Actions after confirmation

- For a single-agent plan, begin business execution in the current conversation only after the user confirms continuation.
- For a multi-agent plan, after the user confirms the plan, use the platform’s real persistent independent-task capability to create only the current `Required` members. Do not create `Required if…` roles until the condition is true and the updated plan is confirmed again. Do not create `Optional` roles unless the user explicitly selects them. If the interface has no independent-task capability, state the limitation and retain the plan; do not substitute temporary subagents or ordinary chats for persistent members.
- Reuse a matching persistent task in the current project when it can continue the work; create a new one only when none fits.
- Give each member a self-contained assignment that includes `TOOLKIT_MODE=member`, its role, goal, inputs, outcome, permissions, dependencies, model, and prohibition on recursive team planning.
- Finding or approving an external Skill does not authorize installation, script execution, login, private-data access, writes, uploads, publication, or deletion. Confirm each action according to its own risk.
- The project lead may decide when to request authorization but cannot grant system permissions on the user’s behalf. If creation or installation fails, stop and report the actual state; never claim completion.

## Pre-send check

Check outcomes only; do not enforce a fixed length or every possible section:

1. All work packages needed to reach the final state are covered and each has a clear Owner; the user, model, tool, Skill, or project-lead label does not silently fill a responsibility gap.
2. The single-agent or multi-agent conclusion follows from the user’s facts.
3. Every role has a clear responsibility and a genuinely checkable outcome; every separate member passes the transfer test; no role exists merely because of a title, downstream consumption, or future possibility; there is no duplicate Owner or invented deliverable.
4. The user is not assigned execution merely because they know how to do it; actions that require a real person are not assigned to AI. For an app-store submission, paid service, or platform release, the relevant user-held account, 2FA, payment, legal-acceptance, and final-submission actions are named explicitly rather than hidden behind a generic external-action notice; irrelevant items are not added.
5. Each default model fits the role’s routine core work; an occasional high-risk segment does not raise the entire role; every model change names a full model and reasoning effort; Token-saving options appear only for mechanical repetitive steps and state what the tool does, which steps use no model, and what the model still owns.
6. Skill recommendations are at most 3; public leads have an original link and accurate status.
7. The response does not describe a recommendation as already installed, created, or executed.
8. The localized Recommended AI Team table is the only roster; members are not repeated before or after it. Combining responsibilities does not rely on AI-invented scope assumptions, and the absence of user wording about combining does not become evidence for splitting.
9. Status and timing are not confused. Conditional roles have an observable activation condition and are not created now; milestones are not written as existence conditions. A shared goal does not have dual project leads, and fully independent work does not receive an invented lead. Markdown emphasis renders correctly.
10. A complete plan ends with the localized next-step section, the correct single-agent or multi-agent action, and the Skill-discovery action. Team creation covers only current Required members; discovery does not authorize installation or execution. Clarification-only answers have no next-step section.
11. The complete clarification or recommendation uses the selected branch consistently; a progress message never determines the final-output branch and stays brief without implying execution.
12. Every locally available Skill recommendation uses the platform’s exact full identifier, including its namespace when present.

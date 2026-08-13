# Model Recommendations

Read this file only after the role structure is settled. Match models to actual responsibility and rework risk; never let a model create roles or change team boundaries.

## 1. Give one default configuration

For each current role, give:

- a currently available full model name and reasoning effort;
- one reason tied directly to the role’s core responsibility, inputs, and validation risk.

Use the configuration that fits the role’s recurring core work. Do not let one rare high-risk task raise the whole role to a stronger model or higher reasoning effort. Only when high-risk judgment dominates the role, or a lower configuration would make its core outcome unreliable, should the default itself be stronger.

Do not force a fixed two-tier answer. Add `Upgrade when` or `Token-saving option` only when a safe, concrete option exists. It is valid to omit both for a role. Do not fill every role with the same downgrade merely to complete a template.

## 2. Evaluate work inside the role

First separate the role’s work into:

1. **Routine core work:** the repeated work that determines day-to-day outcome quality;
2. **Occasional high-risk work:** a specific decision, review, or recovery task whose error is costly;
3. **Low-risk execution:** structured, mechanical, easily checked work with low rework cost.

Then evaluate:

1. **Responsibility risk and reasoning:** Does it require complex judgment, long-context synthesis, conflict resolution, high-risk review, or errors that are difficult to detect?
2. **Inputs and validation:** Are inputs complete, scope stable, acceptance criteria clear, and outputs easy to check?
3. **Currently available models:** Select only model names and reasoning efforts the current environment confirms.
4. **Rework cost:** Could omissions, repeated input, or correction cost more than the expected saving?

Typical directions:

- For bounded, structured, easily checked organization and local execution, use a balanced or lightweight configuration.
- For multi-step reasoning, cross-material consistency, or moderate professional judgment, use a balanced model with `medium` or `high` reasoning effort.
- For core research, complex architecture, high-risk review, long-context synthesis, or strong uncertainty, keep a capable model. Consider a lower reasoning effort before changing to a weaker model.
- If a role contains several independent internal analysis lines, a configuration that supports internal parallel reasoning can be useful, but mention extra Token and coordination cost. Internal temporary work does not become a user-visible team member.

A tight deadline, many files, many pages, a senior-sounding title, the word “best,” or a limited project budget does not determine the model or Token strategy by itself.

## 3. Make every model change complete

Whenever recommending a different model or reasoning effort, give:

- the specific work it applies to;
- the full target model name;
- the target reasoning effort.

Do not write only `medium`, `low`, `lower reasoning`, or `use a lightweight model`. A user must be able to apply the recommendation without reconstructing the configuration.

Normally give even an inactive conditional role a full default configuration. Only when its future work depends on a special capability such as audio or video and the current environment cannot confirm a supported model may you defer the recommendation. State that when the condition becomes true, the plan must be updated, the model configuration confirmed, and the role confirmed again. Do not use a vague tier or model-selector placeholder.

## 4. Token-saving options are not always model downgrades

Only add `Token-saving option` when a clear, low-risk, easily checked optimization exists. Do not promise a fixed saving.

Consider, in order:

1. narrow the input to the current stage;
2. make acceptance criteria and output structure explicit;
3. reduce re-reading or process material in bounded batches;
4. use deterministic tools for fixed-rule, mechanical, independently verifiable steps;
5. lower the same model’s reasoning effort for low-risk work;
6. use a lighter model only when the result is easy to check and rework is cheap.

When suggesting a deterministic script or tool, state:

- what the tool performs;
- which steps require no model call;
- which rule interpretation, ambiguity handling, exception judgment, or result explanation remains with the model.

Do not present semantic classification, product trade-offs, design judgment, professional review, or independent validation as mechanical processing. Do not recommend a lower configuration when it is likely to increase omission or rework. Do not translate “the project budget is limited” into “the Token budget is limited.”

## 5. Current model boundary

- Do not maintain a permanent default list and do not assign models by job title. The same title may need different configurations for different work packages.
- Do not invent a model name, capability, reasoning effort, price, context size, or speed. Use only facts the current environment or current official material confirms.
- If a current required or optional role lacks a confirmable model configuration, the recommendation is incomplete; stop rather than replace it with a vague capability tier.

## 6. Pre-send check

- Every current role has one complete default configuration, except the narrow inactive special-capability case.
- The default follows the role’s routine core work, not the project’s total complexity or the title.
- Any upgrade or downgrade names specific work, a full model name, and a reasoning effort.
- Token-saving options appear only when useful and do not mechanically repeat across roles.
- Deterministic processing states the tool boundary, the no-model steps, and the model-owned judgment.
- A model recommendation has not added a member or changed professional ownership.

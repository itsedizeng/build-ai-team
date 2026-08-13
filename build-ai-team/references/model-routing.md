# Model Recommendations

Read this file only after the role structure is settled. Match models to actual responsibility and rework risk; never let a model create roles or change team boundaries.

## 1. Give one default configuration

For each current role, give:

- a currently available full model name and reasoning effort;
- one reason tied directly to the role’s core responsibility, inputs, and validation risk.

Use the configuration that fits the role’s recurring core work. Do not let one rare high-risk task raise the whole role to a stronger model or higher reasoning effort. Only when high-risk judgment dominates the role, or a lower configuration would make its core outcome unreliable, should the default itself be stronger.

Do not force a fixed two-tier answer. Add `Upgrade when` or `Token-saving option` only when a safe, concrete model-configuration change exists. It is valid to omit both for an individual role. Across a complete recommendation, however, actively look for these boundaries: when any default has a genuinely stronger high-risk branch, include at least one useful upgrade condition on the closest role; when any role has low-risk, repetitive, easily verified work that can safely use a lower-cost configuration, include at least one useful Token-saving option on the closest role. Omit a field across the whole recommendation only when no current role has an eligible case. Do not fill every role with the same upgrade or downgrade merely to complete a template.

If every current role receives the same strongest model and reasoning effort, re-run the routine-core analysis for each role before sending. Shared product risk, a launch requirement, or the fact that roles collaborate does not prove that product definition, design execution, engineering, and structured validation all need the same default. Identical configurations remain acceptable only when each role’s recurring core work independently justifies them.

## 2. Evaluate work inside the role

First separate the role’s work into:

1. **Routine core work:** the repeated work that determines day-to-day outcome quality;
2. **Occasional high-risk work:** a specific decision, review, or recovery task whose error is costly;
3. **Low-risk execution:** structured, repetitive, easily checked work with low rework cost.

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

In a non-English response, keep the full model identifier and the exact reasoning-effort value, but translate the surrounding label. For example, Chinese uses `gpt-5.6-sol`，推理强度 `high`; do not append the English phrase `reasoning effort`. In Chinese, use the exact field labels `升级条件` and `节省 Token 建议`.

Do not write only `medium`, `low`, `lower reasoning`, or `use a lightweight model`. A user must be able to apply the recommendation without reconstructing the configuration.

Normally give even an inactive conditional role a full default configuration. Only when its future work depends on a special capability such as audio or video and the current environment cannot confirm a supported model may you defer the recommendation. State that when the condition becomes true, the plan must be updated, the model configuration confirmed, and the role confirmed again. Do not use a vague tier or model-selector placeholder.

## 4. Token-saving options are model-configuration changes

Only add `Token-saving option` when clear, low-risk, easily checked work can safely use a lower-cost model or reasoning-effort configuration. Do not promise a fixed saving.

Assess each distinct Owner's work independently. In a maker-checker workflow, the maker's low-risk execution and the checker's low-risk evidence organization are different possible cases; when both can safely use lower configurations, give each a role-specific option. Do not reuse one option for both, and do not force an option when the checker's value is mainly non-repetitive professional judgment.

Choose one of these changes:

1. lower the same model's reasoning effort for clearly bounded low-risk work; or
2. use a lower-cost model and reasoning effort when the result is easy to check and rework is cheap.

Name the concrete low-risk work, then give the full target model name and reasoning effort. End by stating which core judgment or higher-risk work remains on the role's default configuration. Do not put scripts, tools, automation, commands, smaller-input tactics, reduced re-reading, or process advice in this field. Do not imply automatic model routing. Do not recommend a lower configuration when it is likely to increase omission or rework. Do not translate “the project budget is limited” into “the Token budget is limited.”

## 5. Current model boundary

- Do not maintain a permanent default list and do not assign models by job title. The same title may need different configurations for different work packages.
- Do not invent a model name, capability, reasoning effort, price, context size, or speed. Use only facts the current environment or current official material confirms.
- If a current required or optional role lacks a confirmable model configuration, the recommendation is incomplete; stop rather than replace it with a vague capability tier.

## 6. Pre-send check

- Every current role has one complete default configuration, except the narrow inactive special-capability case.
- The default follows the role’s routine core work, not the project’s total complexity or the title.
- An all-identical strongest configuration has been re-checked against each role’s recurring core work rather than inherited from shared project risk.
- Any upgrade or downgrade names specific work, a full model name, and a reasoning effort.
- A localized response preserves model and effort identifiers but translates the reasoning-effort label.
- When at least one current role has an eligible higher-risk branch or safely downgradable low-risk work, the recommendation exposes the corresponding useful Upgrade condition or Token-saving option; the fields do not mechanically repeat across roles.
- Every Token-saving option names concrete low-risk work, a full lower-cost model configuration, and the core work that stays on the default configuration; it does not introduce automation or process advice.
- A model recommendation has not added a member or changed professional ownership.

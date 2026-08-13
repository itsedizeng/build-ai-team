# Curated Skill Leads

Use this file only as an offline source of public leads for the first recommendation. It does not replace current-version review before installation. Recommend at most 3 Skills; this is a ceiling, not a quota. Recommend none when no item would materially help.

## Usage rules

- Review the Skill names and descriptions directly exposed by the current platform before this index.
- `Last reviewed` means that the original source and primary capability were checked read-only on that date. It does not mean the item is still current and is not a security certification.
- In user-facing output, show only name, accurate status, original link, and reason. Do not expose internal labels such as “curated lead,” “direct match,” or “related addition.”
- Localize status text to the user’s response language by translating this English semantic pattern naturally: `[Skill name](original source) (public recommendation; not checked live; installation status unknown) — reason.` Preserve the exact Skill identifier and source URL, and do not show the English pattern beside its translation.
- Say the natural equivalent of `available locally` only when the current platform directly shows the Skill as available or callable.
- If the user asks for current verification or installation, use `skill-discovery.md` to inspect the current tree, references, scripts, license, maintenance, and permission risks.

## Current public leads

| Skill | Original source | Best-fit situations | Direct value | Important boundary | Last reviewed |
|---|---|---|---|---|---|
| `skill-installer` | [OpenAI skills](https://github.com/openai/skills/tree/main/skills/.system/skill-installer) | The user has already named a GitHub Skill and wants to install it | Uses the platform-supported installation workflow instead of inventing an installer | Installation writes to the local Skill directory and requires an explicit user request; it does not determine whether a third-party Skill is safe | 2026-08-11 |
| `find-skills` | [Vercel Labs skills](https://github.com/vercel-labs/skills/tree/main/skills/find-skills) | The user wants a broader set of Skill leads | Searches public Skill directories from a task description | Search ranking is only a discovery signal; review the original repository before installation | 2026-08-11 |
| `security-and-hardening` | [Addy Osmani agent-skills](https://github.com/addyosmani/agent-skills/tree/main/skills/security-and-hardening) | Web products with authentication, APIs, user data, or third-party integrations | Provides a framework for threat modeling, input validation, authentication/authorization, and supply-chain checks | Primarily web-focused; depends on the repository-level `references/security-checklist.md`; does not replace iOS-specific or formal compliance review | 2026-08-11 |
| `dispatching-parallel-agents` | [obra/superpowers](https://github.com/obra/superpowers/tree/main/skills/dispatching-parallel-agents) | Several independent problem domains or investigation tracks already exist | Helps decide when temporary parallel agent dispatch is worthwhile | Adds context, Token, and coordination cost; not suitable for tightly dependent or shared-write work | 2026-08-11 |

## Maintenance

When adding, updating, or removing a lead, keep its original source, applicable situation, direct value, important boundary, and review date accurate. Do not add an item based only on Stars, downloads, ranking, or the author’s own claims.

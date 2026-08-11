# Skill 推荐索引

本文件只提供首次建议中的公开推荐线索，不替代安装前的当前版本核验。最多推荐 3 个是上限，不是配额；没有明显帮助就不推荐。

## 使用口径

- 先使用当前平台直接可见的本机 Skill 名称与说明，再看本索引。
- `最近复核`只表示当日只读确认过原始来源和主要能力，不表示当前仍是最新版，也不构成安全认证。
- 用户可见内容只写名称、状态、原始链接和推荐理由，不显示“精选候选”“直接适用／相关补充”等内部分类。
- 索引项统一表达为：`[Skill 名称](原始来源)（公开推荐；未实时核验，安装状态未确认）——推荐理由。`
- 只有平台明确显示已安装或可调用时，才写`本机可用`。
- 用户要求实时确认或安装时，再按`skill-discovery.md`检查当前文件树、引用、脚本、许可、维护和权限。

## 当前推荐线索

| Skill | 原始来源 | 适合的场景 | 主要价值 | 重要边界 | 最近复核 |
|---|---|---|---|---|---|
| `skill-installer` | [OpenAI skills](https://github.com/openai/skills/tree/main/skills/.system/skill-installer) | 用户已经点名 GitHub Skill 并准备安装 | 使用平台支持的安装流程，避免自行拼装安装器 | 安装会修改本地 Skill 目录，必须由用户明确请求；它不负责判断第三方 Skill 安全 | 2026-08-11 |
| `find-skills` | [Vercel Labs skills](https://github.com/vercel-labs/skills/tree/main/skills/find-skills) | 用户想继续扩大 Skill 候选范围 | 根据需求搜索公开 Skill 目录 | 搜索排名只是发现线索；安装前仍需回原仓库审查 | 2026-08-11 |
| `security-and-hardening` | [Addy Osmani agent-skills](https://github.com/addyosmani/agent-skills/tree/main/skills/security-and-hardening) | Web、认证、API、用户数据和第三方集成的安全工作 | 提供威胁建模、输入验证、认证授权与供应链检查框架 | 主要面向 Web；依赖仓库级`references/security-checklist.md`；不能替代 iOS 或正式合规审查 | 2026-08-11 |
| `dispatching-parallel-agents` | [obra/superpowers](https://github.com/obra/superpowers/tree/main/skills/dispatching-parallel-agents) | 已存在多个相互独立的问题域或调查方向 | 提供何时值得并行派发临时 Agent 的方法 | 会增加上下文、Token 和协调成本；不适合强依赖或共享写入任务 | 2026-08-11 |

## 维护方式

持续增加、更新或删除线索时，同步准确来源、适用场景、直接价值、重要边界和最近复核日期。不要仅因 Stars、下载量或榜单排名加入候选。

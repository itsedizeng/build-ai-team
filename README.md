# Build AI Team

> 当前版本：`v1.0-beta7` · Public Beta

Build AI Team 是一个以 Codex 为核心的 AI 团队规划 Skill。它会根据你的需求判断适合单 Agent 还是多 Agent，并给出角色定位、责任结果、模型建议和相关 Skill 推荐。

## 当前状态

- beta7 已完成独立静态复核：重大 0／轻微 0／阻断 0；
- beta7 六场模型验证尚未运行；
- Codex 是当前核心目标环境；
- ChatGPT Work 与 Claude 兼容入口尚未完成 beta7 实机验证；
- 当前仓库只提供 Public Beta 源码快照，不代表稳定版、正式版或生产可用版本；
- 本项目不是 OpenAI、Codex 或 Anthropic 官方项目。

## 与 Agent Team v1.0 的关系

Build AI Team 是独立的 Skill 产品，不是 [Agent Team v1.0](https://github.com/itsedizeng/agent-team) 五文件工具包，也不会替换其现有 Release。

## 目录

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

## 在 Codex 项目中试用

1. 下载或克隆本仓库；
2. 将完整的`build-ai-team/`目录放入目标项目的`.agents/skills/`目录；
3. 在新的 Codex 任务中显式选择 Build AI Team，或输入：

```text
$build-ai-team 我想做一个能上架 App Store 的记账 App，请给我团队建议。
```

当前版本只建议在测试项目中试用。团队建议不会自动创建成员、安装其他 Skill 或开始执行业务；后续动作仍需用户确认。

## 校验

`SHA256SUMS.txt`列出五个运行文件的 SHA-256，可用于确认下载内容没有变化。它不包含 README 和 LICENSE 的哈希。

## 许可

© 2026 D. 免费用于个人项目和商业项目，并允许为个人或组织内部使用而私下修改；不得重新上传、镜像、转售、翻译发布或重新包装本 Skill 及其修改版。完整条款见 [LICENSE.md](LICENSE.md)。

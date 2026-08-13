# Build AI Team

[English](README.md) | [简体中文](README.zh-CN.md)

> Release Candidate：`v1.0.0-rc.9`

Build AI Team 是一个完全开源、以 Codex 为核心的 AI 团队规划 Skill。它会根据真实的交付、责任、权限、独立验证和容量需求，判断一个 Agent 是否足够，或者是否值得建立多个长期 Agent；同时给出角色分工、负责结果、模型配置和相关 Skill 建议。

它默认先给方案。未经用户针对具体动作确认，不会创建团队、安装 Skill、连接账号、读取私有数据或写入外部系统。

## 当前状态

- 英文运行文件以已经独立验证的中文 `v1.0-beta13` 行为为基线；澄清问题和完整建议跟随用户最新实质请求的语言，技术标识保持准确。
- `v1.0.0-rc.9` 五份运行文件和冻结的 5 个 Case／7 Run 验证包均已通过独立静态验收，结果为 0 重大／0 轻微／0 阻断。
- 另在真实 Codex Desktop 临时项目中，使用同一候选完成了 6 个 fresh task 可见检查：5 个英文请求和 1 个中文请求的进度消息与完整建议均跟随输入语言。该结果只代表有限的真实宿主观察，不构成统计保证或跨宿主验证。
- Codex Desktop 的项目工作方式是当前核心目标环境。
- 已提供 ChatGPT Work 和 Claude 的兼容入口说明，但本候选尚未在这些宿主中完成实机验证。
- 本项目不是 OpenAI、Codex、ChatGPT 或 Anthropic 官方项目。
- 宿主版本、模型可用性和建议质量可能不同；不暗示任何厂商认可，也不保证跨宿主兼容。
- 当前仓库版本是首个采用 MIT 的公开 Release Candidate；只有回读并核验公共 `main` 的精确 commit 后，才创建对应的 annotated tag 和 Pre-release。

## 它能做什么

- 根据实际工作判断使用单 Agent 还是多 Agent，而不是套用固定岗位表。
- 为每个角色写清定位、责任、唯一负责结果、边界、依赖和必要性状态。
- 分开项目主控与专业 Owner，避免主控自动取得其他角色的交付写权。
- 按角色主体工作推荐一个默认模型与推理强度；只有确有价值时才补充升级或节省 Token 建议。
- 推荐最多三个本机可用或与需求相关的公开 Skill，并准确说明来源和安装状态。
- 将方案确认、建队、Skill 查找、安装、登录、私有数据访问、写入、上传、发布和删除分成不同动作。
- 英文是唯一运行语义来源；输出跟随用户语言，同时保持技术标识准确。

## 它不会自动做什么

- 创建 Agent 或长期任务；
- 安装或运行第三方 Skill；
- 连接账号或业务系统；
- 读取私有数据；
- 写入、上传、发布或删除内容；
- 保证第三方 Skill 安全、最新或一定适用；
- 保证所有行业只有唯一正确的团队人数。

## 在 Codex 项目中安装

1. 下载或克隆本仓库。
2. 将完整的 [`build-ai-team/`](build-ai-team/) 文件夹复制到目标项目的 `.agents/skills/` 目录。
3. 最终路径应为：

```text
<project>/.agents/skills/build-ai-team/SKILL.md
```

4. 同一版本的五份运行文件必须保持完整：

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

5. 新建一个 Codex 任务，显式选择 Build AI Team，或输入：

```text
$build-ai-team 我想做一个能上架 App Store 的记账 App，请给我团队建议。
```

不要只复制 `SKILL.md`，也不要把整个仓库根目录放进 `.agents/skills/`。更新时请整体替换五份运行文件，不要混用不同版本。

如果 Skill 没有出现，先检查目录层级、`build-ai-team` 文件夹名称和五份文件是否完整，再考虑其他处理方式。

## 更新或卸载

- **更新：** 用同一个新版本的完整 `build-ai-team/` 文件夹替换原来的五份运行文件，核对 `SHA256SUMS.txt`，然后新建 Codex 任务。不要混用不同版本的文件。
- **卸载：** 只删除 `<project>/.agents/skills/build-ai-team/`，然后新建 Codex 任务。不要删除上层 `.agents/skills/` 目录，因为其中可能还有其他 Skill。

卸载后，后续新任务不再加载本 Skill；它不会撤销用户此前另行确认创建的团队、文件、安装、账号访问或外部动作。

## 示例需求

```text
$build-ai-team 我只需要根据已经定稿的 PRD 做一个可点击原型，不需要开发。
```

```text
$build-ai-team 请规划一次 CRM 数据迁移，并安排独立的只读核验；现在不要连接 CRM。
```

```text
$build-ai-team I want to design, build, and launch a paid web app with accounts and subscriptions.
```

## 如何理解团队方案

- `Required／必要`：方案确认后属于当前团队。
- `Required if…／具体条件成立时必要`：只有可观察条件成立后才出现该工作包，当前不创建。
- `Optional／建议`：可以提高质量、速度或覆盖度，但不是完成当前目标所必需，默认不创建。
- `Owner`：某个工作包或交付物的唯一负责人。
- `project lead／主控`：由一个已有实质角色兼任，额外负责计划、依赖和最终交接状态；不会自动取得其他专业交付的所有权。
- 独立验证者：不参与被审对象的生产，也不修改被审结果。

## 查找相关 Skill

首次方案只使用宿主直接提供的 Skill 和小型离线索引。只有用户明确要求时，才开始公开来源的实时只读查找。

推荐不等于安装；安装也不等于允许运行脚本、登录、读取私有数据、写入、上传、发布或删除。使用第三方 Skill 前仍应核对文件、权限和许可。

第三方项目名称和链接仅作为参考，不代表认可、合作关系、当前兼容或安全认证；这些项目仍适用各自的许可。

## SHA-256 校验

[`SHA256SUMS.txt`](SHA256SUMS.txt) 只覆盖五份运行文件。下载后请使用系统支持的 SHA-256 工具进行核对。

## 仓库文档

- [English README](README.md)
- [CHANGELOG](CHANGELOG.md)
- [贡献说明](CONTRIBUTING.md)
- [安全说明](SECURITY.md)
- [MIT License](LICENSE)

## 与 Agent Team v1.0 的关系

Build AI Team 是独立的 Skill 产品，不替代早期的五文件 [Agent Team v1.0](https://github.com/itsedizeng/agent-team) 工具包及其不可变 Release。

## 开源许可与唯一官方来源

本公开候选按 [MIT License](LICENSE) 提供。许可变更从包含 `v1.0.0-rc.9` 的公共 `main` commit 开始生效；该版本及后续明确采用 MIT 的版本可以在遵守许可的前提下使用、复制、修改、合并、发布、分发、转授权和销售副本。

早期公开的 `v1.0-beta7` 源码快照仍受[该次提交中附带的非开源定制许可](https://github.com/itsedizeng/build-ai-team/blob/b2e81d3859a169056629e78dff322cfcfbefcf31/LICENSE.md)约束；MIT 变更不追溯适用于旧快照。

唯一官方仓库是 [itsedizeng/build-ai-team](https://github.com/itsedizeng/build-ai-team)。

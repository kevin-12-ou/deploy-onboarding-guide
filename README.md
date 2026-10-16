# Deploy Onboarding Guide

[简体中文](README.zh-CN.md) | [Skill instructions](SKILL.md) | [Maintainer: kevin-12-ou](https://github.com/kevin-12-ou)

**A Chinese-first AI agent skill for assessing open-source software before installation and explaining setup, permissions, costs, and first use.**

“Installed successfully” tells a beginner little about what a project does, which accounts or paid APIs it needs, what it can access, and how to use it.

This is an **Agent Skill: instructions and reference material for an AI assistant**, not a hosted service or an autonomous program. The package contains no installation hooks, application runtime, models, background services, or credentials; its Python script is only for development-time package validation. The assistant still operates under its host permissions and the user's authorization.

## When to use it

- Explain purpose, prerequisites, cost, permissions, and data flow before setup.
- Inspect the chosen source version and relevant install or executable entry points.
- Continue within granted authorization without asking for approval at every routine step.
- Verify the requested outcome and provide concrete first-use, stop, update, and rollback guidance.

## Install

Use Git and an assistant that supports Agent Skills. The optional Skills CLI below also requires Node.js/npm and is a separate executable tool to review before running. This skill itself needs no API key, database, or paid account; your chosen AI assistant may have its own costs.

```sh
npx skills add kevin-12-ou/deploy-onboarding-guide --skill deploy-onboarding-guide
```

Choose the agent and scope in the installer. For a project-local Codex installation, with copied files rather than symlinks:

```sh
npx skills add kevin-12-ou/deploy-onboarding-guide --skill deploy-onboarding-guide --agent codex --copy
```

Manual option: copy the complete repository into a skill directory named `deploy-onboarding-guide`, such as `.agents/skills/deploy-onboarding-guide/`, where supported by your assistant. Keep `SKILL.md` and its referenced files together; follow your client's skill-directory documentation.

## Example prompts

```text
Use $deploy-onboarding-guide. Assess this open-source repository before installing it. Explain its purpose, prerequisites, permissions, data access, and costs in Chinese; then complete the authorized setup if the evidence supports it.
```

```text
用 $deploy-onboarding-guide。帮我装这个开源项目。先用中文说明用途、条件、权限、数据访问和费用，检查后在授权范围内完成安装并教我第一次使用。
```

```text
Use $deploy-onboarding-guide. Only assess this repository. Tell me what it does and the concrete risks for my computer; do not install or run it.
```

```text
用 $deploy-onboarding-guide。只评估这个仓库：它有什么用、会怎样影响电脑和数据？这次不安装、不运行。
```

Explicitly naming the skill helps make intent clear. Automatic selection depends on the model and client and is not guaranteed. The package follows the [Agent Skills specification](https://agentskills.io/specification); clients such as Codex and Claude Code can read this format, but equivalent behavior across every client is not claimed. Core instructions are primarily Chinese; this English README provides discovery and usage context.

## Boundaries and data

Not an antivirus, sandbox, or safety certificate. Source inspection does not prove a distributed binary is equivalent or harmless. A skill installation is not authorization to deploy the entire associated product.

No private project history is bundled. File access, network requests, commands, and edits depend on the task and the assistant's tools. A text skill is not an isolation boundary or a mandatory security interceptor.

## Maintenance and feedback

For Skills CLI installs, `npx skills check` checks for updates and `npx skills update` updates installed skills. Review changes first. Disable the skill in your client, or move its installed directory out of discovery, to stop using it. Back up any personal additions before updating or removing it.

Report a sanitized example in [Issues](https://github.com/kevin-12-ou/deploy-onboarding-guide/issues). See [CONTRIBUTING.md](CONTRIBUTING.md) and [VALIDATION.md](VALIDATION.md) for contribution and validation boundaries.

## Related skills by kevin-12-ou

- [Concept to Action Coach](https://github.com/kevin-12-ou/concept-to-action-coach) — An AI agent skill for explaining technical concepts to beginners and turning understanding into a small, verifiable action.
- [Don't Repeat Yourself](https://github.com/kevin-12-ou/dont-repeat-yourself) — An AI agent skill for saving verified coding solutions as searchable recipes and adapting them to future projects.
- [Release Migration Parity](https://github.com/kevin-12-ou/release-migration-parity) — An AI agent skill for preserving accepted UI, behavior, and data semantics when releasing an app or migrating it to another platform.

Maintained by [kevin-12-ou](https://github.com/kevin-12-ou). Developed from personal AI-assisted workflows. Licensed under [MIT](LICENSE); see [NOTICE.md](NOTICE.md) for provenance.

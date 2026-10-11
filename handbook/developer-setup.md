# 开发者准备技能与工具

技能和工具由开发者安装、连接和升级。项目只保存介绍、命令、使用分工以及适配本项目的规则，不保存技能源码或项目技能副本。本页中的安装命令供开发者在自己的终端按需要执行，项目初始化不自动运行这些命令。

## Matt 技能集合

[Matt 官方仓库](https://github.com/mattpocock/skills)是来源入口。本手册介绍本轮核实的 39 项本机已安装技能；远端集合可能继续变化，安装前先查看当时清单。安装命令采用已核对的 [Skills CLI 用法](https://github.com/vercel-labs/skills/blob/main/README.md)。

查看可发现的技能：

```sh
npx skills@latest add mattpocock/skills --list --full-depth
```

按实际使用的代理安装到开发者目录。例如同时使用 Codex 和 Claude Code：

```sh
npx skills@latest add mattpocock/skills --global --skill '*' --full-depth --agent codex --agent claude-code
```

只使用其中一种时，保留相应的 `--agent` 参数即可。`--global` 表示用户级安装；`--skill '*'` 选择技能全集。这里不使用 `--all`，因为它还会选择所有代理并跳过交互确认。

检查安装结果：

```sh
npx skills@latest ls --global --agent codex
```

项目继续使用 `grill-with-docs`、`implement`、`tdd` 等原技能名。原技能要求显式调用时保留该方式；功能有重叠时，按[完整介绍](matt-skills.md)选择分支并共用已有材料。安装集合完整不表示每次任务都读取或执行全部技能。

在 Codex 中，技能列表可能因为上下文预算缩短描述或省略部分条目，不能仅凭本轮显示的列表判断是否缺失。需要时核对实际安装目录及清单。[官方技能发现说明](https://learn.chatgpt.com/docs/build-skills)

## 接入项目

开发者装好技能后，在项目上下文调用 `setup-matt-pocock-skills`。它需要的三份项目文档是 `docs/agents/issue-tracker.md`、`domain.md`、`triage-labels.md`。已有任务表、术语或决定记录时，接缝指向现有权威并说明读写方式，不再建立第二套内容。

项目另提供 `docs/agents/skill-usage.md` 和 `tool-adapters.md`，说明调用顺序、规则差异、执行环境与验证范围。短 AGENTS 或 CLAUDE 入口指向这些文档。项目固定的是通用规范版本；实际安装的技能与工具版本由开发者管理，变化后核对兼容性，不把全局更新伪装成项目规范升级。

## Context7

Context7 CLI 可按需通过项目允许的包执行器使用。通用例子如下，具体项目如已有受控入口则优先使用它：

```sh
npx ctx7@latest library "Git" "worktree branch isolation"
npx ctx7@latest docs <返回的库ID> "一个具体问题"
```

先 `library` 再 `docs`，同一问题最多三次查询。配额、网络、版本与权限限制如实记录；凭据由开发者通过允许方式配置，不放进项目文档。完整规则由[项目工具适配模板](../templates/tool-adapters.md)带入本项目。

## CodeGraph

本方法采用的是 [colbymchenry/codegraph](https://github.com/colbymchenry/codegraph)，包名为 `@colbymchenry/codegraph`，不要与其他同名工具混用。开发者可按官方说明安装并接入代理：

```sh
npm install -g @colbymchenry/codegraph
codegraph install
```

`codegraph install` 配置代理集成，可能写入开发者所选的代理配置；它不建立代码索引。可先打印 Codex 配置片段检查：

```sh
codegraph install --print-config codex
```

开发者决定为某个项目建立索引后，才在该项目根运行：

```sh
codegraph init
```

已有 `.codegraph/` 的项目，理解或定位代码先走 explore：MCP 明确传入本项目 `projectPath`，或在正确项目目录使用 CLI。没有索引则按普通文件检索继续，并标明未索引；项目规则文档不自动创建索引。[官方安装说明](https://github.com/colbymchenry/codegraph/blob/main/site/src/content/docs/getting-started/installation.md)

## Herdr

Herdr 是偏好的终端与 worktree 组织入口。macOS 已使用 Homebrew 时，官方提供：

```sh
brew install herdr
```

其他平台按[官方安装文档](https://github.com/herdrdev/herdr/blob/master/docs/versions/0.9.0/website/src/content/docs/install.mdx)选择方式。开发者安装后，在 Herdr 管理的终端里核对当前版本和可用命令。项目仍要区分终端分屏与独立 Git 工作副本，遵守当前宿主技能的会话访问边界。

## 本机其他技能与 MCP

已有的 `find-docs`、`think`、`check`、`hunt`、`ui` 等可补充 Matt 集合，触发分工见[工具与技能](tools-and-skills.md)。项目不要求开发者为了匹配清单安装所有工具；需要哪项能力，就记录其来源、入口、前提和验证范围。

MCP 的配置与认证由开发者在所用宿主完成。项目记录“已发现、可调用、已配置、已验证”及适用范围，记录中不包含秘密值。工具缺失时先判断是否有等价入口，不能完成的验证保留缺口。

# 项目技能使用绑定模板

生成到 `docs/agents/skill-usage.md`。开发流程、技能分工、Context7、CodeGraph、Herdr 和缺项处理直接继承[通用协作规则](../handbook/tools-and-skills.md)。本文件只填写项目事实和实际例外；生成时改写链接，使其从目标文件可达。

## 采用的通用规则

填写方法版本及本项目中的相对链接：通用协作规则、[Matt 全集介绍](../handbook/matt-skills.md)、[开发者安装说明](../handbook/developer-setup.md)。技能原件从开发者安装位置读取，项目只记录使用绑定。

## 项目资料绑定

| 使用时需要的事实 | 填写内容 |
|---|---|
| 当前目标、规格与任务 | 指向 `issue-tracker.md` 的权威位置 |
| 当前进度与下一步 | 唯一状态文件链接 |
| 领域词汇与架构决定 | 指向 `domain.md` |
| 请求分流 | 指向 `triage-labels.md` |
| 命令、工具与环境 | 指向 `tool-adapters.md` |
| 验收与执行证据 | 项目完成条件、证据位置与当前真实阶段 |

## 项目例外

没有差异时写“继承通用规则，无新增例外”。存在差异时，只记录：对应通用条目、项目执行方式、原因、影响和验证办法。例如桌面插件需要实际原生宿主；某项目限制所有缓存留在仓库内。通用的先查资料、按条件调用技能、独立审查、工作副本隔离等规则不再抄写。

项目需要额外技能时，填完整名称、来源、补充环节与前提；不因用途重叠删去通用目录中的原入口。工具和技能的实际状态统一放 `tool-adapters.md`。

## 代理入口片段

将下列意图写入当前宿主适用的入口，链接按实际位置改写，保留其他现有规则：

```markdown
## 开发入口

开始任务先读项目指南、唯一状态与当前任务规格。
开发方法采用 development-method/VERSION；按 development-method/README.md 加载当前环节。
选择技能、查外部技术资料、定位代码或组织并行工作时，读 development-method/handbook/tools-and-skills.md。
项目资料位置与例外见 docs/agents/skill-usage.md；实际命令、环境和工具状态见 docs/agents/tool-adapters.md。
任务、领域与请求状态分别见 docs/agents/issue-tracker.md、domain.md、triage-labels.md。
```

验证入口和所有相对链接可达，项目例外有理由，已确认事实与未决条件可区分。完成检查后删除本模板的填写提示。

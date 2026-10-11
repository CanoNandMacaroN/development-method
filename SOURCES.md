# 方法来源与适配说明

本版将用户确认的工作方式，与现有工程技能和公开工程资料整理为一套可执行方法。具体规则按本包各章描述；来源并不意味着将其全部流程、固定工具和组织习惯照搬进项目。

## 公开资料

- [敏捷宣言原则](https://agilemanifesto.org/iso/zhchs/principles.html)：参考及早交付可工作的成果、短反馈周期与持续调整的方向；本包不要求固定会议或特定敏捷框架。
- [Google Engineering Practices：审查内容](https://google.github.io/eng-practices/review/reviewer/looking-for.html)：参考审查设计、功能、测试、复杂度及文档的视角；实际覆盖范围按任务说明。
- [Google Engineering Practices：小而完整的改动](https://google.github.io/eng-practices/review/developer/small-cls.html)：参考将变化组织为可理解的自洽单元；本包保留用户选定的本地过程记录、主线汇总与远端同步节奏，不设置通用行数上限。
- [Herdr 官方 CLI 文档](https://github.com/herdrdev/herdr/blob/master/docs/versions/0.9.0/website/src/content/docs/cli-reference.mdx)：核对 worktree 与工作区之间的能力关系。这里是能力参考，不是对任何本机或服务端版本已经实测的声明；实际命令以执行环境核验为准。

## 技能参考

需求与计划参考 grilling、think；领域和接口设计参考 domain-modeling、codebase-design；测试与诊断参考 tdd、hunt、diagnosing-bugs；审查参考 check、code-review；文档与初始化参考 writing-for-agents、write、skill-creator。它们的具体使用边界见[技能与工具](handbook/tools-and-skills.md)。

本包用自己的说明与中性示例整理方法，不附带第三方技能原件、脚本或工具二进制。开发者按[安装说明](handbook/developer-setup.md)自行准备技能；通用包保留协作细则，项目绑定具体事实和例外；实际原件及资源由安装环境管理。全部 39 项已核对技能的说明见[完整目录](handbook/matt-skills.md)。

## 有意适配的差异

- 用户确认目标和关键取舍，AI 自主选择已有授权内的测试位置、样例和局部实现方式，不把每个测试边界都变成人工确认点。
- 测试保护下的必要局部整理可以随任务完成；大规模结构调整单独说明和验证，不把重构一概限制在审查阶段。
- 吸收规格与实现两方面审查，不继承特定仓库目录、额外工具安装或一律暂存所有文件等假设。
- 方法写给人读，代理入口按任务指向相关章节；使用清楚的中文术语，不要求人记住一套新的隐喻。
- Herdr 是偏好的执行适配之一。方法中的目标、工作副本、验证和交付概念独立于终端工具；是否可操作仍由当前环境和授权决定。

# Tasks

- [x] Task 1: 建立促前脱敏 Mock 数据与七步状态模型。
  - [x] SubTask 1.1: 定义目标约束、大盘水位、类目需求、核销漏斗、实验、竞对、方案、预算和治理数据。
  - [x] SubTask 1.2: 定义七章报告状态、消息状态、下钻状态、预算场景和最终产物状态。
  - [x] SubTask 1.3: 所有内部 ID、平台、团队、金额和日期遵循 Spec 脱敏规则。

- [x] Task 2: 实现“促前券档位设计”独立 Aime 式工作台。
  - [x] SubTask 2.1: 点击左侧促前历史项进入独立视图。
  - [x] SubTask 2.2: 中栏包含极简标题、多轮消息、固定输入框和底部附件。
  - [x] SubTask 2.3: 右栏包含七章 Queue、报告画布、自定义、隐藏/恢复和全屏。
  - [x] SubTask 2.4: 返回原工作台不破坏促中历史会话和原有状态。

- [x] Task 3: 实现目标约束与分析计划门禁。
  - [x] SubTask 3.1: 默认展示用户目标、已知数据、缺失参数和七步分析计划。
  - [x] SubTask 3.2: 支持确认计划、补充目标和输入预算上限。
  - [x] SubTask 3.3: 确认后仅生成第一分析章节，后续由对话动作推进。

- [x] Task 4: 实现 P0 大盘水位和 P1 类目爆发分析。
  - [x] SubTask 4.1: 展示近 20 天 GMV/DAC/客单同比及贡献拆分。
  - [x] SubTask 4.2: 展示一级类目活动放大系数、DAC/客单拉动、增量贡献和 S/A/B/C 优先级。
  - [x] SubTask 4.3: 支持二级类目下钻并映射到建议券档。
  - [x] SubTask 4.4: 每个阶段输出结论、证据、机制、限制和下一步。

- [x] Task 5: 实现历史领券核销、实验钱效与竞对分析。
  - [x] SubTask 5.1: 按人群/渠道/面额切换领取与核销漏斗。
  - [x] SubTask 5.2: 展示券组人均 GMV、增量 GMV、补贴、ROI 和显著性。
  - [x] SubTask 5.3: 展示竞对 A/B/C 的档位、折扣、会员加码、频次和影响等级。
  - [x] SubTask 5.4: 支持类目 × 人群 × 面额 × 渠道交叉下钻。

- [x] Task 6: 实现 3+X/4+X 候选和预算规划。
  - [x] SubTask 6.1: 展示 A/B/C 三套方案及推荐原因。
  - [x] SubTask 6.2: 展示固定档位、X 弹性券、人群包和渠道分配。
  - [x] SubTask 6.3: 展示波次预算、专项子预算和风险准备金。
  - [x] SubTask 6.4: 支持保守/基准/激进结算率、预算缩减和需求超预期场景。
  - [x] SubTask 6.5: 展示团队拉齐、预算申请、立项和保密协议状态。

- [x] Task 7: 实现促前追问、报告产物与慢速演示。
  - [x] SubTask 7.1: 预设问题覆盖大盘水位、类目、核销、实验、竞对、预算和治理。
  - [x] SubTask 7.2: 自由追问基于当前章节和脱敏 Mock 数据回答。
  - [x] SubTask 7.3: 使用排队、分析、写入三阶段慢速推进。
  - [x] SubTask 7.4: 最终生成待审批策略包和自包含 HTML 报告，固定显示在中栏底部。

- [x] Task 8: 验证促前完整链路与回归。
  - [x] SubTask 8.1: 运行 JavaScript 语法检查和重复 ID 检查。
  - [x] SubTask 8.2: 浏览器验证七步主链、二级类目下钻和至少一个自由追问。
  - [x] SubTask 8.3: 验证方案选择、预算敏感性、治理确认和报告产物。
  - [x] SubTask 8.4: 验证促前/促中切换、返回工作台、控制台和布局。

# Task Dependencies

- Task 2 depends on Task 1.
- Task 3 depends on Task 1 and Task 2.
- Task 4 depends on Task 3.
- Task 5 depends on Task 4.
- Task 6 depends on Task 4 and Task 5.
- Task 7 depends on Task 2 through Task 6.
- Task 8 depends on all previous tasks.

- [x] Task 9: 发布到 GitHub：将已验收的 Demo 与规格文档提交并推送到 `https://github.com/jiaoyunqin/ai--coupon--strategy`。
  - [x] SubTask 9.1: 初始化本地 Git 仓库并使用 `main` 分支，不覆盖或回滚现有文件。
  - [x] SubTask 9.2: 提交前扫描凭证、Token、真实 ECOP 站点参数和不应发布的临时文件。
  - [x] SubTask 9.3: 提交 `index.html` 与 `.trae/specs` 规格记录，生成清晰的首次提交。
  - [x] SubTask 9.4: 配置指定 GitHub 远端并执行非强制推送。
  - [x] SubTask 9.5: 验证远端 `main` 与本地 HEAD commit 一致，且远端可见 `index.html`。

- Task 9 depends on Task 8.

- [x] Task 10: 同步最终验收状态：保留 locked 章节紧凑折叠，恢复被错误删除的促前七步治理链路，提交并推送最终规格状态，同时通过 `.gitignore` 排除未跟踪 `.trae/documents/`，确保本地与远端一致。

- Task 10 depends on Task 9.

- [x] Task 11: 重构促前首页数据与状态模型，改为活动与参考促集合驱动。
  - [x] SubTask 11.1: 定义 26 年活动日历、活动日期、级别、阶段和历史关系。
  - [x] SubTask 11.2: 实现“前序四次 + 同级别促 + 同名历史促”的自动参考样本算法和去重规则。
  - [x] SubTask 11.3: 定义用户添加 / 删除参考促的状态，并同步样本覆盖与洞察上下文。
  - [x] SubTask 11.4: 移除首页促类型、推荐方案、预算、ROI、具体 3+X/4+X、波次配置和巡检依赖。

- [x] Task 12: 实现轻量活动下拉与参考促样本管理。
  - [x] SubTask 12.1: 首页使用“26 年活动日历”下拉选择，不展示活动卡片墙。
  - [x] SubTask 12.2: 展示当前活动名称、日期、级别、阶段和数据状态。
  - [x] SubTask 12.3: 展示参考促标签及其“前序四次 / 同级别 / 同名历史 / 用户添加”原因。
  - [x] SubTask 12.4: 支持删除参考促和从历史活动中添加参考促。
  - [x] SubTask 12.5: 切换规划活动后自动重建参考促集合并更新洞察。

- [x] Task 13: 实现细化的历史消费券实验洞察与来源说明。
  - [x] SubTask 13.1: 展示活动前 15–20 天 GMV / DAC / 客单趋势及去年同期对比。
  - [x] SubTask 13.2: 展示活动前窗口与历史活动期的分类目 GMV / DAC / 客单爆发情况。
  - [x] SubTask 13.3: 展示各券档领取 / 核销趋势，并支持行业和价格带下钻。
  - [x] SubTask 13.4: 展示分波次券档表现与券批次节奏。
  - [x] SubTask 13.5: 展示价值、潜力、新客、回流等人群分层实验差异。
  - [x] SubTask 13.6: 展示竞对券档、折扣、张数、频次和变化方向聚合。
  - [x] SubTask 13.7: 每个章节包含证据、AI 小结、适用边界、来源和追问，不生成本期具体方案。
  - [x] SubTask 13.8: 追问携带活动、参考促集合、洞察主题、证据和来源进入促前对话。

- [x] Task 14: 验证活动、参考样本与历史洞察首页并执行回归。
  - [x] SubTask 14.1: 运行 JavaScript 语法、静态 ID 和 diff 检查。
  - [x] SubTask 14.2: 浏览器验证活动下拉、参考促自动生成、增删和活动切换重算。
  - [x] SubTask 14.3: 验证大盘水位、类目爆发、券档、价格带、波次、人群和竞对洞察。
  - [x] SubTask 14.4: 验证首页不再出现促类型、推荐 B、申请预算、预估 ROI、具体 4+X 方案和配置巡检。
  - [x] SubTask 14.5: 验证历史促前对话、促中工作台和追问链路不受影响。

- Task 12 depends on Task 11.
- Task 13 depends on Task 11 and Task 12.
- Task 14 depends on Task 11 through Task 13.

- [x] Task 15: 修复参考促算法、洞察重算与旧首页残留。
  - [x] SubTask 15.1: 前序四次算法纳入所选活动之前的全部已结束活动，不因活动日历分组遗漏。
  - [x] SubTask 15.2: 参考促增删后重算样本覆盖、证据指标和 AI 小结，不只更新样本数量。
  - [x] SubTask 15.3: 补齐类目客单、完整券档趋势、持续期波次、回流人群和竞对具体券档信息。
  - [x] SubTask 15.4: 删除 `#preDashboardLegacy` 及仅服务旧默认首页的样式、数据和事件引用。
  - [x] SubTask 15.5: 消除 `coverageResult`、`finalDecision` 静态重复 ID，同时保持促中运行时行为不变。
  - [x] SubTask 15.6: 重新执行 Task 14 全量静态与浏览器验收。

- Task 15 depends on Task 11 through Task 13.

- [x] Task 16: 修复公开发布前的内部资源脱敏。
  - [x] SubTask 16.1: 扫描内部域名、真实 ECOP 查询参数、Token / 凭证和资源 URI 等发布风险。
  - [x] SubTask 16.2: 将真实内部资源名、域名、URI 和站点参数替换为不可反推的 Mock 别名。
  - [x] SubTask 16.3: 运行 JavaScript 语法、静态 ID、发布风险扫描和 `git diff --check` 验证。

- [ ] Task 17: 修复自动参考促重新加入后的语义漂移：删除自动参考促后重新加入同一活动时，保留其“前序四次 / 同级别 / 同名历史”原因并叠加“用户添加”标记，确保相同样本集合恢复相同权重、证据指标和 AI 小结。

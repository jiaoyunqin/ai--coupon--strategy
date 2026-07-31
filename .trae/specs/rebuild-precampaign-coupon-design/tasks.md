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

- [ ] Task 9: 发布到 GitHub：将已验收的 Demo 与规格文档提交并推送到 `https://github.com/jiaoyunqin/ai--coupon--strategy`。
  - [ ] SubTask 9.1: 初始化本地 Git 仓库并使用 `main` 分支，不覆盖或回滚现有文件。
  - [ ] SubTask 9.2: 提交前扫描凭证、Token、真实 ECOP 站点参数和不应发布的临时文件。
  - [ ] SubTask 9.3: 提交 `index.html` 与 `.trae/specs` 规格记录，生成清晰的首次提交。
  - [ ] SubTask 9.4: 配置指定 GitHub 远端并执行非强制推送。
  - [ ] SubTask 9.5: 验证远端 `main` 与本地 HEAD commit 一致，且远端可见 `index.html`。

- Task 9 depends on Task 8.

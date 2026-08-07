# Tasks

- [x] Task 1: 将促前券方案收敛为两个一级模块。
  - [x] SubTask 1.1: 顶部仅保留“一 方案总览”“二 渠道与人群策略”。
  - [x] SubTask 1.2: 旧 `mechanisms / delivery / validation` 状态统一回退到方案总览。
  - [x] SubTask 1.3: 保留页签键盘、ARIA 和活动/候选视图状态。

- [x] Task 2: 完善方案总览的决策信息。
  - [x] SubTask 2.1: 展示方案定位、活动、波次和券结构。
  - [x] SubTask 2.2: 展示申请预算、预计结算预算/结算率、候选 ROI 和 ROI 下限。
  - [x] SubTask 2.3: 展示适用条件与核心风险。

- [x] Task 3: 将动态券归入每波券组。
  - [x] SubTask 3.1: 保留通发、储备、定向与特殊人群、动态机制四类。
  - [x] SubTask 3.2: 领前增发、核销后增发、惊喜、膨胀、追补和互动按波次展示。
  - [x] SubTask 3.3: 删除独立动态机制模板页。
  - [x] SubTask 3.4: 固定券与动态券分别使用固定面额和范围/折扣规则。

- [x] Task 4: 收敛技术与执行边界。
  - [x] SubTask 4.1: 方案总览不展示真实券批次、券池、BSK、实验、计划和 Source ID。
  - [x] SubTask 4.2: 实时库存、实际消耗和巡检状态不进入方案总览。
  - [x] SubTask 4.3: 缺失字段不补造精确值。

- [x] Task 5: 完成实现验证。
  - [x] SubTask 5.1: 验证 618 八波和 38 节单波数据。
  - [x] SubTask 5.2: 验证活动、候选、端口和波次切换不串数据。
  - [x] SubTask 5.3: 验证两个页签的鼠标、键盘和 ARIA 行为。
  - [x] SubTask 5.4: 验证 JavaScript、重复 ID、控制台、响应式和 `git diff --check`。

# Task Dependencies

- Task 2 depends on Task 1.
- Task 3 depends on Tasks 1-2.
- Task 4 depends on Task 3.
- Task 5 depends on Tasks 1-4.

# Tasks

- [x] Task 1: 将渠道与人群策略调整为第二个一级模块。
  - [x] SubTask 1.1: 删除第五个 Tab 的旧定位。
  - [x] SubTask 1.2: 保留活动、方案、端口和波次上下文。
  - [x] SubTask 1.3: 保留主端/极速/独立端适用性。

- [x] Task 2: 保留结构化渠道矩阵。
  - [x] SubTask 2.1: 保留 5 个冻结上下文列。
  - [x] SubTask 2.2: 保留 3 个固定阵地、12 个灵活加码、3 个会场引流渠道。
  - [x] SubTask 2.3: 发放、催用、互动和仅引流继续独立成行。
  - [x] SubTask 2.4: 保留动作、时段、人群、形式、端口、兜底、频控、去重和互斥。

- [x] Task 3: 精简渠道单元格。
  - [x] SubTask 3.1: 状态从“已配置”改为“已规划”。
  - [x] SubTask 3.2: 移除每个单元格重复的 Source、人群包、实验和配置别名。
  - [x] SubTask 3.3: 保留缺数、待校验、冲突、停投和降级语义。

- [x] Task 4: 增加执行交接。
  - [x] SubTask 4.1: 汇总当前波次批次与投放计划。
  - [x] SubTask 4.2: 汇总券池/BSK、实验和上线校验待办。
  - [x] SubTask 4.3: 状态只使用待配置、待校验、不适用。
  - [x] SubTask 4.4: 提供批次计划、实验巡检和消费券工具平台入口。

- [x] Task 5: 完成实现验证。
  - [x] SubTask 5.1: 验证三个视口下矩阵滚动、冻结列和交接区。
  - [x] SubTask 5.2: 验证活动、候选、端口和波次上下文隔离。
  - [x] SubTask 5.3: 验证外部链接及安全属性。
  - [x] SubTask 5.4: 验证键盘/ARIA、控制台、重复 ID、JavaScript 和 `git diff --check`。

# Task Dependencies

- Task 2 depends on Task 1.
- Task 3 depends on Task 2.
- Task 4 depends on Tasks 1-3.
- Task 5 depends on Tasks 1-4.

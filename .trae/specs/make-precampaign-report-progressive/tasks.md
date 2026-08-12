# Tasks

- [x] Task 1: 建立促前报告渐进生成状态契约。
  - [x] SubTask 1.1: 区分队列状态与正式报告可提交状态，只有 `complete` 章节可进入报告正文。
  - [x] SubTask 1.2: 定义 0/7、部分完成、全部完成和待更新状态。
  - [x] SubTask 1.3: 保持目标约束、P0、P1、核销、实验竞对、候选、预算治理七步顺序不变。

- [x] Task 2: 实现未执行和执行中的右侧轻量状态。
  - [x] SubTask 2.1: 在 0 个完成章节时显示“尚未生成报告”空态，不渲染报告封面和正文。
  - [x] SubTask 2.2: 排队、分析和写入过程只显示在生成队列与紧凑执行提示中。
  - [x] SubTask 2.3: 失败或取消时移除执行提示，不保留半成品章节。

- [x] Task 3: 实现已完成章节渐进写入。
  - [x] SubTask 3.1: 用户确认目标与计划后，将第 1 章作为首个完成章节写入报告。
  - [x] SubTask 3.2: 后续章节完成后按七步顺序原子追加到正式报告。
  - [x] SubTask 3.3: 正式报告不渲染锁定、排队、分析、写入和待确认章节。
  - [x] SubTask 3.4: 为新写入章节增加克制动效，并支持减少动态效果偏好。

- [x] Task 4: 实现报告工具栏门禁与自定义边界。
  - [x] SubTask 4.1: 0 个完成章节时禁用查看报告、自定义、全屏、预览和下载，并提供可读原因。
  - [x] SubTask 4.2: 1-6 个完成章节时允许查看草稿和全屏，仅允许自定义已完成章节。
  - [x] SubTask 4.3: 7 个章节全部完成且无待更新章节时启用最终 HTML 预览和下载。
  - [x] SubTask 4.4: 队列点击仅对已完成章节执行正文定位，其他状态只反馈依赖。

- [x] Task 5: 处理上游约束变化和报告更新。
  - [x] SubTask 5.1: 修改目标、预算或口径后，将受影响章节标记为待更新。
  - [x] SubTask 5.2: 待更新期间禁用最终 HTML 下载并展示轻量提示。
  - [x] SubTask 5.3: 重算完成后原位替换章节，不新增重复内容。

- [x] Task 6: 验证渐进生成体验与既有功能回归。
  - [x] SubTask 6.1: 验证 0/7、1/7、2/7、6/7、7/7 和生成失败状态。
  - [x] SubTask 6.2: 验证桌面宽屏、1280px、1024px 和移动抽屉布局。
  - [x] SubTask 6.3: 验证键盘、ARIA、减少动态效果、焦点恢复和无横向溢出。
  - [x] SubTask 6.4: 回归促前七步门禁、原报告内容、HTML 产物、促中历史会话和 01-04 章节编号。
  - [x] SubTask 6.5: 执行 JavaScript 语法、静态 ID、控制台和 `git diff --check` 检查。

- [x] Task 7: 修复促前第 7 章治理门禁不可达，恢复 6/7 到 7/7 的完整业务路径。
  - [x] SubTask 7.1: 第 7 章处于 `needs-input` 时，在正式报告正文之外渲染可交互的角色确认与独立流程清单，继续遵守 complete-only 正文规则。
  - [x] SubTask 7.2: 让“查看确认清单”能够打开并聚焦该清单，暴露全部 `[data-pre-confirm-role]` 与 `[data-pre-confirm-governance-process]` 控件，并支持键盘操作与焦点恢复。
  - [x] SubTask 7.3: 全部门禁满足后解锁待审批策略包确认链路；最终确认后原子提交第 7 章并启用最终 HTML 预览和下载。
  - [x] SubTask 7.4: 浏览器回归 6/7、`needs-input`、7/7、策略包、HTML 产物及 complete-only 正文边界。

# Task Dependencies

- Task 2 depends on Task 1.
- Task 3 depends on Task 1 and Task 2.
- Task 4 depends on Task 3.
- Task 5 depends on Task 3 and Task 4.
- Task 6 depends on Task 2、Task 3、Task 4 and Task 5.
- Task 7 depends on Task 3、Task 4 and Task 5; Task 6 must be rerun after Task 7 is complete.

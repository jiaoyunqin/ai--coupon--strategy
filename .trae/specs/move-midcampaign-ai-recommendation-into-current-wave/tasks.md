# Tasks

- [x] Task 1: 建立当前波次建议与采纳预览状态。
  - [x] SubTask 1.1: 在 `midCampaignViewState.current` 中增加建议状态、采纳快照和当前上下文键。
  - [x] SubTask 1.2: 建立建议、预估效果、护栏及下方模块映射的数据契约。
  - [x] SubTask 1.3: 定义波次、端口和周期变化时的预览清理规则。

- [x] Task 2: 将 AI 策略调优建议迁移到 01 顶部。
  - [x] SubTask 2.1: 将建议清单、预估效果、追问、采纳和详情入口移动到 `midRecommendationCards` 顶部。
  - [x] SubTask 2.2: 让建议内容随当前波次、端口、周期和证据可用性刷新。
  - [x] SubTask 2.3: 删除 03 中旧 `recommendSection`、`adoptedBanner` 及重复事件入口。

- [x] Task 3: 实现采纳后预览联动。
  - [x] SubTask 3.1: 当前券批次增加券档角色预览，原始数值保持不变。
  - [x] SubTask 3.2: 调人群增加优先验证、稳量观察、收缩泛发标签。
  - [x] SubTask 3.3: 调渠道增加规模底座、催用承接、高意图补充和观察标签。
  - [x] SubTask 3.4: 实时监控增加 ROI、核销率、预算流速和重复触达护栏提示。
  - [x] SubTask 3.5: 支持取消采纳预览并恢复默认视图。

- [x] Task 4: 完善详情、会话、响应式与可访问性。
  - [x] SubTask 4.1: 更新查看策略详情弹层，展示建议与下方模块映射、事实依据、预估和边界。
  - [x] SubTask 4.2: 保持独立追问和灰度候选审计上下文与当前筛选一致。
  - [x] SubTask 4.3: 完成桌面双栏、窄屏单栏及键盘/焦点/ARIA 状态。

- [x] Task 5: 执行静态、浏览器和回归验证。
  - [x] SubTask 5.1: 运行 JavaScript、重复 ID、敏感信息与 `git diff --check`。
  - [x] SubTask 5.2: 验证第一波主端全周期、独立端、具体日期和占位波次。
  - [x] SubTask 5.3: 验证采纳、取消预览、下方四块联动和查看详情。
  - [x] SubTask 5.4: 验证 1440px、1280px、1024px、860px 和 760px 布局及 Axe。
  - [x] SubTask 5.5: 回归 02、03、促前默认工作台和历史会话。

- [x] Task 6: 修复键盘打开策略弹层后的焦点进入与焦点陷阱。
  - [x] SubTask 6.1: 使用 Enter 或 Space 打开采纳确认、策略详情弹层时，将焦点移入弹层首个可操作元素。
  - [x] SubTask 6.2: 当弹层已打开且焦点仍在弹层外时，Tab / Shift+Tab 应先进入弹层并只在弹层内循环。
  - [x] SubTask 6.3: 回归键盘采纳、取消预览、查看详情、Escape 关闭及触发按钮焦点恢复。

- [x] Task 7: 修复策略弹层边界焦点仍可逃逸。
  - [x] SubTask 7.1: 修复采纳确认与策略详情弹层在首项 Shift+Tab、末项 Tab 时焦点进入背景的问题。
  - [x] SubTask 7.2: 弹层打开期间隔离背景可聚焦元素，并保留弹层外焦点重新进入弹层的处理。
  - [x] SubTask 7.3: 真实浏览器重验 Enter / Space 打开、Tab / Shift+Tab 循环、Escape 恢复焦点、鼠标开关与取消预览键盘操作；清单唯一未勾项保留独立复验。

# Task Dependencies

- Task 1 无前置依赖。
- Task 2 依赖 Task 1。
- Task 3 依赖 Task 1 和 Task 2。
- Task 4 依赖 Task 2 和 Task 3。
- Task 5 依赖 Task 1 至 Task 4。
- Task 6 依赖 Task 5 的失败证据，修复后需重验对应检查点。
- Task 7 依赖 Task 6 的独立复验失败证据，修复后需重验对应检查点。

# Tasks

- [x] Task 1: 建立促中重排所需的统一视图状态与结构边界。
  - [x] SubTask 1.1: 定义 01 的“决策摘要、调整清单、效果与护栏”三区结构。
  - [x] SubTask 1.2: 定义 02 的四个详情 Tab、默认 Tab、推荐依据展开状态和上下文切换重置规则。
  - [x] SubTask 1.3: 保留现有活动、年份、波次、候选、会话和缺数数据契约，不新增业务数据源。

- [x] Task 2: 重排 01 当前波次调优。
  - [x] SubTask 2.1: 将原诊断、目标约束和关键指标合并为决策摘要。
  - [x] SubTask 2.2: 将七个调整维度统一渲染为单一调整清单，合并“调整前 → 调整后”的视觉关系。
  - [x] SubTask 2.3: 将投放人群和灵活渠道详情改为对应调整行内展开，移除清单外重复章节。
  - [x] SubTask 2.4: 将预估效果、风险、护栏、回滚和两个方案操作入口收敛到模块底部。

- [x] Task 3: 重排 02 下一波次方案明细与调优。
  - [x] SubTask 3.1: 保留三张摘要卡并将其设为唯一候选选择入口，删除重复方案 Tab。
  - [x] SubTask 3.2: 实现“总览与指标、波次与批次、人群与渠道、实验与护栏”四个互斥详情 Tab。
  - [x] SubTask 3.3: 将渠道角色与人群渠道矩阵合并到同一 Tab，将实验分流与护栏合并到同一 Tab。
  - [x] SubTask 3.4: 将推荐依据移到配置之后并默认折叠，保持当前候选证据同步。
  - [x] SubTask 3.5: 保持每张方案卡的单一“继续调整”按钮和详情区方案级独立追问。

- [x] Task 4: 统一视觉层级、响应式和可访问性交互。
  - [x] SubTask 4.1: 统一 01/02 的章节头、区块标题、状态标记、Tab 和操作区视觉语法。
  - [x] SubTask 4.2: 在宽屏使用清单/表格布局，在窄屏使用字段顺序一致的纵向条目。
  - [x] SubTask 4.3: 同步候选、详情 Tab、行内展开和推荐依据的焦点、ARIA 与键盘行为。

- [x] Task 5: 执行静态、浏览器和回归验证。
  - [x] SubTask 5.1: 运行 JavaScript 语法、重复 ID、`undefined`、敏感信息和 `git diff --check`。
  - [x] SubTask 5.2: 验证 38节、618、双11及不同年份/波次下的数据、候选、详情和会话上下文。
  - [x] SubTask 5.3: 验证桌面宽屏、1440px、1280px、1024px、860px 和 760px 布局。
  - [x] SubTask 5.4: 验证键盘、ARIA、控制台、数据追问、方案追问和继续调整链路。
  - [x] SubTask 5.5: 回归 03 实时监控、促前默认工作台和既有历史会话。

- [x] Task 6: 修复 Task 5 独立验证发现的窄屏命中遮挡与候选 Tab ARIA 语义。
  - [x] SubTask 6.1: 修复 760px 下 `.mid-current-transition-arrow` 旋转后覆盖“投放人群/灵活渠道”行内展开按钮命中区域的问题，确保鼠标可直接点击且无按钮重叠。
  - [x] SubTask 6.2: 调整三张候选卡的 `tablist` / `tab` DOM 所有关系，消除 Axe `aria-required-children` 和 `aria-required-parent` critical 违规。
  - [x] SubTask 6.3: 清理 01 中无有效角色的 `aria-label` 与 `article[role="listitem"]` 语义告警，保持现有键盘、焦点和视觉状态不变。
  - [x] SubTask 6.4: 修复后重新执行 760px 指针交互、六档响应式、候选键盘/ARIA、Axe 和 Task 5 全量回归。

- [x] Task 7: 修复 Task 6.4 独立复验仍存在的候选 `tablist` Axe critical，并重新完成全量验收。
  - [x] SubTask 7.1: 重构 `#midNextWaveCompare` 的 ARIA 所有关系，使 `tablist` 仅包含或拥有 `tab`，将候选卡内“基于此方案继续调整”按钮等非 `tab` 交互排除在 `tablist` 语义外，同时保持三卡视觉布局和唯一候选入口不变。
  - [x] SubTask 7.2: 使用 Axe 4.12.1 分别扫描 `#midNextWaveCompare` 与 `#midNextWavePlanner`，确认 `aria-required-children`、`aria-required-parent` critical 均为 0，并人工核对每个候选 `tab` 的父级/所有者、`aria-controls`、`aria-selected` 和 `tabindex`。
  - [x] SubTask 7.3: 重新验证候选与四个详情 Tab 的 Tab、方向键、Home/End、Enter/Space、焦点和视觉/ARIA 同步，并复验 760px 投放人群/灵活渠道鼠标直接点击命中。
  - [x] SubTask 7.4: 重新执行 1440/1280/1024/860/760 及桌面宽屏响应式、JS、ID、diff、控制台、多活动波次、03、促前和历史会话全量回归，通过后再完成 Task 5.3、5.4、6.4 及 checklist 剩余项。

# Task Dependencies

- Task 1 无前置依赖。
- Task 2 和 Task 3 均依赖 Task 1，完成结构契约后可并行实施。
- Task 4 依赖 Task 2 和 Task 3。
- Task 5 依赖 Task 2、Task 3 和 Task 4。
- Task 7 依赖 Task 6.4 的失败证据，完成后重新执行 Task 5 与 Task 6.4 验收。

# Tasks

- [x] Task 1: 建立 `03` 卡片增强所需的独立视图状态与数据适配。
  - [x] SubTask 1.1: 扩展机会卡视图状态为 `category / tier / price`，并增加独立的行业/价格带二级切换状态。
  - [x] SubTask 1.2: 增加竞对 `broadcast / compare` 视图状态，保持现有年份、关注和动作状态不变。
  - [x] SubTask 1.3: 为券档漏斗、行业/价格带和竞对横向对比建立只读适配函数，统一读取当前 `currentInsights` 和归档数据。
  - [x] SubTask 1.4: 活动或参考促切换后校正无效焦点和视图状态，缺数时返回明确空态。

- [x] Task 2: 丰富 AI 收敛结论和自然水位卡。
  - [x] SubTask 2.1: 将 AI 摘要改为“水位判断 / 当前方案影响 / 待验证风险”，移除已过时的候选生成提示。
  - [x] SubTask 2.2: 方案一、二、三切换后同步刷新“当前方案影响”，不改变候选本身和 `02` 交互。
  - [x] SubTask 2.3: 在自然水位卡增加 GMV、DAC、客单紧凑摘要，并与当前指标及趋势点联动。
  - [x] SubTask 2.4: 将卡片底部说明收敛为当前数据点、变化判断和方案影响，不新增无来源精确值。

- [x] Task 3: 将机会与效率卡扩展为三个决策视图。
  - [x] SubTask 3.1: 保留并精修“类目机会”排行和焦点说明。
  - [x] SubTask 3.2: 实现“券档漏斗”，展示发放、领取、核销、领取率、领后核销和 ROI，并支持券档焦点切换。
  - [x] SubTask 3.3: 实现“行业价格带”，支持行业/价格带二级切换并复用现有 `tier.drills`。
  - [x] SubTask 3.4: 根据当前视图和焦点同步更新追问上下文、摘要与推荐问题。
  - [x] SubTask 3.5: 为三个视图补齐鼠标、方向键、Home/End、Enter/Space 和焦点恢复。

- [x] Task 4: 丰富竞对播报卡。
  - [x] SubTask 4.1: 在现有卡片中增加“动态播报 / 横向对比”视图切换。
  - [x] SubTask 4.2: 保留动态播报中的年份、关注、变化动作和反馈。
  - [x] SubTask 4.3: 实现竞对横向对比，统一展示券档、折扣、会员/张数、频次和变化方向。
  - [x] SubTask 4.4: 年份切换后同步刷新当前竞对视图，并更新压力判断和追问上下文。

- [x] Task 5: 统一 `03` 视觉并保持 `04` 隔离。
  - [x] SubTask 5.1: 使用 `03` 琥珀色章节变量统一摘要、卡片、Tab、双层条形、矩阵和选中态。
  - [x] SubTask 5.2: 收敛卡片边框、圆角、阴影、字号、间距和操作层级，不新增外部字体、图标库或图片。
  - [x] SubTask 5.3: 处理 1440px、1280px、1024px、860px、760px 响应式，确保内容只在自身容器内滚动。
  - [x] SubTask 5.4: 确认 `04` 的 DOM、筛选、洞察展开、行业/价格带下钻和追问逻辑无修改。

- [x] Task 6: 执行静态、交互与视觉回归。
  - [x] SubTask 6.1: 运行内联 JavaScript 语法、静态/运行时重复 ID、ARIA 引用和 `git diff --check`。
  - [x] SubTask 6.2: 浏览器验证候选切换、自然水位指标/数据点、机会三视图、行业/价格带和竞对双视图。
  - [x] SubTask 6.3: 验证活动和参考促变化后所有 `03` 内容按当前上下文刷新，缺数不串数据。
  - [x] SubTask 6.4: 验证追问上下文与当前视图一致，控制台和网络无新增错误。
  - [x] SubTask 6.5: 回归 `02` 候选与建议采纳、`04` 历史洞察、促前历史对话和促中工作台。

- [x] Task 7: 修复首轮浏览器验收阻断。
  - [x] SubTask 7.1: 修复 `?mode=pre` 直达页面在初始化后被默认促中模式覆盖的问题，确保 URL 模式在异步与运行时初始化完成后仍保持有效。
  - [x] SubTask 7.2: 修复行业/价格带二级 Tab 使用方向键切换后的焦点恢复，确保选中态、`tabindex` 与实际焦点一致。
  - [x] SubTask 7.3: 重新执行促前直达、二级 Tab 键盘、JavaScript、静态 ID 和 `git diff --check` 定向验证。

- [x] Task 8: 修复第二轮浏览器与 Axe 验收阻断。
  - [x] SubTask 8.1: 隔离自然水位 GMV / DAC / 客单 Tab 的方向键、Home / End 处理，确保切换后保持促前工作台并恢复到新选中指标。
  - [x] SubTask 8.2: 修复竞对横向对比“变化方向”表头对比度，使 Axe critical / serious 均为 0。
  - [x] SubTask 8.3: 将竞对年份反馈圆点和 AI 摘要残留的蓝紫装饰统一为 `03` 琥珀主题，不覆盖语义状态色。
  - [x] SubTask 8.4: 重新执行自然水位键盘、竞对横向 Axe、主题色、JavaScript、静态 ID 和 `git diff --check` 定向验证。

# Task Dependencies

- Task 1 无前置依赖。
- Task 2、Task 3 和 Task 4 依赖 Task 1；三项可并行实施。
- Task 5 依赖 Task 2、Task 3 和 Task 4。
- Task 6 依赖 Task 1 至 Task 5。
- Task 7 depends on Tasks 1-5 and the first Task 6 browser verification.
- Task 8 depends on Tasks 1-5 and the second Task 6 browser/Axe verification.
- Task 6 completion depends on Tasks 7 and 8.

- [x] Task 9: 恢复可达的参考促增删与无参考促空态，解除最终 Task 6 验收阻断。
  - [x] SubTask 9.1: 在促前规划界面恢复参考促管理入口，展示当前自动/用户添加参考促，并支持逐项移除与从当前活动可用历史池添加。
  - [x] SubTask 9.2: 参考促增删后使用现有 `excludedReferenceIds`、`userAddedReferenceIds` 和 `preRenderPlanningDashboard` 同步重算 `03` 的水位、类目、券档、行业/价格带、竞对与 AI 摘要，不回退默认活动数据。
  - [x] SubTask 9.3: 允许经界面移除全部参考促以到达 AI、趋势、机会、竞对和历史洞察空态，并验证重新添加参考促后按当前活动恢复；缺数不得拼接其他活动或年份。
  - [x] SubTask 9.4: 修复后重新执行参考促增删、无参考/缺数空态、默认 618 与非默认活动、静态语义、五视口、Axe、控制台和网络验证，再完成 Task 6 与 checklist。

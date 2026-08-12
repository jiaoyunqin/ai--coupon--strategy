# Tasks

- [x] Task 1: 建立任务模版、变量、产出契约和任务实例的数据模型。
  - [x] SubTask 1.1: 扩展现有模版目录，使内置模版具备稳定来源、阶段、变量、产出章节和能力标签，同时保持原有提问文本可继续复用。
  - [x] SubTask 1.2: 增加页面内自建模版集合、草稿/启用状态和稳定模版标识，不改写现有只读内置模版。
  - [x] SubTask 1.3: 增加任务模版库筛选、创建步骤、编辑对象、运行参数和任务结果状态。
  - [x] SubTask 1.4: 建立任务实例快照，固定当次模版、活动、波次、参数、能力和产出要求。

- [x] Task 2: 实现任务模版入口与模版库。
  - [x] SubTask 2.1: 在策略工作台新增“任务模版”入口，并复用现有基础资源视图的切换与返回行为。
  - [x] SubTask 2.2: 实现“全部 / 内置 / 我创建的”来源页签、阶段筛选和名称/场景搜索。
  - [x] SubTask 2.3: 渲染只包含阶段、名称、场景说明和产出类型的紧凑卡片。
  - [x] SubTask 2.4: 在现有新建对话模版区增加“查看全部”和“新建任务模版”入口，不改变当前筛选和快速填入行为。

- [x] Task 3: 实现两步任务模版创建流程。
  - [x] SubTask 3.1: 第一步提供任务指令编辑，并支持 `{变量}` 自动识别和选中文本“设为变量”。
  - [x] SubTask 3.2: 实现变量新增、编辑、删除及类型、说明、默认值、必填和上下文来源配置。
  - [x] SubTask 3.3: 实现产出类型和标准章节选择，默认突出决策摘要、调优动作、效果预估、依据、风险和待确认项。
  - [x] SubTask 3.4: 根据任务指令推荐业务能力标签，并允许调整非必需能力。
  - [x] SubTask 3.5: 第二步实现名称、简介、阶段、场景标签、可见范围和草稿/启用状态确认。
  - [x] SubTask 3.6: 保存后将模版加入“我创建的”，并支持从创建结果直接查看或发起任务。

- [x] Task 4: 实现从已完成策略对话沉淀任务模版。
  - [x] SubTask 4.1: 在已有结构化策略产物的完成态增加“沉淀为任务模版”入口。
  - [x] SubTask 4.2: 从对话上下文预填任务指令、活动/波次候选变量、能力标签和已有产出章节。
  - [x] SubTask 4.3: 确保预填内容进入草稿，用户确认前不保存、不启用，也不修改原对话与原策略产物。

- [x] Task 5: 扩展模版详情并实现结构化发起任务。
  - [x] SubTask 5.1: 将详情扩展为场景、必要参数、预期产出、能力状态和折叠任务指令。
  - [x] SubTask 5.2: 保留“填入对话”，新增“发起任务”，并确保两种行为状态隔离。
  - [x] SubTask 5.3: 渲染任务参数表单，自动带入当前活动与波次，并允许用户修改。
  - [x] SubTask 5.4: 实现必填、类型、上下文有效性和能力可用性校验。
  - [x] SubTask 5.5: 提交前展示运行摘要；确认后创建独立任务实例并进入结果视图。

- [x] Task 6: 完成“末波次预算紧张调优”标准 Demo。
  - [x] SubTask 6.1: 按 spec 定义内置任务模版，默认带入 `7200 万`覆盖容量、`V1 与 V15`、`不要求重点人群保量`和`平衡`风险偏好。
  - [x] SubTask 6.2: 复用现有 V1/V15、L4/L5/jp/t8 和人群规模数据，不复制第二份相互独立的案例事实。
  - [x] SubTask 6.3: 输出决策摘要、总体对比、同位比较、覆盖测算、推荐与备选、效果边界、风险和待确认配置快照。
  - [x] SubTask 6.4: 对覆盖率和量级差使用可验证计算；对缺少数据的 GMV、ROI 和补贴额明确标记不可计算。
  - [x] SubTask 6.5: 提供继续追问和返回来源模版能力，不触发发券、预算或营销引擎写入。

- [x] Task 7: 实现自建模版的最小管理能力和来源追溯。
  - [x] SubTask 7.1: 支持自建模版编辑、复制、启用和停用；内置模版保持只读。
  - [x] SubTask 7.2: 编辑已启用模版时保留历史任务快照，避免结果随最新模版漂移。
  - [x] SubTask 7.3: 在任务结果中展示来源模版、活动、波次、关键参数、能力和数据边界。
  - [x] SubTask 7.4: 重置或离开页面时正确关闭创建/运行弹窗，不破坏已存在的新建对话、历史会话和工作台状态。

- [ ] Task 8: 完成视觉、响应式、键盘和回归验证。
  - [ ] SubTask 8.1: 复用现有视觉 Token，保证核心信息优先，变量、能力和技术指令按需下钻。
  - [ ] SubTask 8.2: 验证 1280px、1024px、760px 和 390px 下模版库、两步弹窗、参数表单与结果无横向溢出。
  - [ ] SubTask 8.3: 验证 Tab、Enter、Space、Escape、步骤焦点、字段错误关联和弹窗焦点边界。
  - [ ] SubTask 8.4: 回归现有内置分析模版筛选、查看详情、复制、快速填入、技能选择、模型选择和手动发送。
  - [ ] SubTask 8.5: 执行 JavaScript 语法、静态与运行时重复 ID、`git diff --check`、浏览器控制台和基础无障碍检查。

- [x] Task 9: 修复独立验证发现的搜索、变量键和上下文校验缺陷。
  - [x] SubTask 9.1: 任务模版搜索框和任务编辑器表单值必须保留真实空字符串，不得经通用展示兜底渲染为“暂无数据”；验证空搜索初始值、按名称搜索和按场景搜索均返回正确结果。
  - [x] SubTask 9.2: 为变量键增加空值与重复值校验，在对应字段就地展示错误并设置 `aria-invalid`、`aria-describedby`；存在错误时阻止进入第二步和保存，不得覆盖或串写其他变量。
  - [x] SubTask 9.3: 活动上下文和波次上下文改为可选择的有效上下文值，或增加等价的有效性校验；任意无效文本必须就地报错并阻止创建任务实例。
  - [x] SubTask 9.4: 任务模版卡片的业务内容严格限制为阶段、名称、场景说明和产出类型；自建模版状态与管理操作使用不扩充卡片业务信息的可访问管理区域表达。
  - [x] SubTask 9.5: 增加搜索空值、重复/空变量键、占位符同步、上下文有效性、卡片信息边界和错误可访问关联的回归验证，修复后重新执行本 checklist 的全部 checkpoint。

- [x] Task 10: 修复工作区任务模版入口被错误标记为定时任务的产品对象回归。
  - [x] SubTask 10.1: 将工作区入口的可见文案从“新建定时任务”改为“任务模版”，与独立模版库的产品对象和页面标题保持一致。
  - [x] SubTask 10.2: 同步修正入口的 `aria-label`、tooltip 和图标语义，不得继续暴露定时任务或闹钟含义。
  - [x] SubTask 10.3: 保持入口点击后打开任务模版库、活动态与返回行为不变，并复验与“新建策略对话”“技能”的职责区分。
  - [x] SubTask 10.4: 在 1280×900、1024×768、760×900、390×844 下复验入口可见性、键盘可达性和可访问名称，修复后重新执行本 checklist 的全部 checkpoint。

- [x] Task 11: 修复任务模版变量动态删除后的弹窗焦点丢失与状态感知缺陷。
  - [x] SubTask 11.1: 删除变量并重渲染编辑器后，将焦点移动到同组相邻变量的删除按钮或变量键；无相邻变量时回到任务指令，焦点不得落到 `body` 或离开 `aria-modal`。
  - [x] SubTask 11.2: 动态新增或删除变量后通过可访问状态区域播报变量名称和当前变量数量，且不打断任务指令、其他变量配置和占位符同步。
  - [x] SubTask 11.3: 复验鼠标与仅键盘操作下的新增、删除、连续删除、Tab/Shift+Tab、Escape、焦点环路和关闭后焦点恢复。
  - [x] SubTask 11.4: 在 1280×900、1024×768、760×900、390×844 下完成动态变量操作最小复验；checklist 全部 116 个 checkpoint 的完整复验留给下一独立验证代理。

- [ ] Task 12: 修复最终系统验收发现的任务模版详情缺少折叠任务指令。
  - [x] SubTask 12.1: 在任务模版详情的场景、参数、预期产出和能力状态之后增加默认折叠的“任务指令”区域，展开后展示完整指令，收起时不占用首屏。
  - [x] SubTask 12.2: 独立模版库与新建策略对话中的模版详情复用一致的折叠内容和键盘语义，不展示技能 ID、Revision、Mock/真实数据等内部信息。
  - [ ] SubTask 12.3: 修复后重新执行全部 116 个 checkpoint，并复验 JavaScript 语法、静态/运行时重复 ID、`git diff --check`、控制台、功能主链路、回归及四视口浏览器证据。

- [ ] Task 13: 修复任务模版详情中折叠“任务指令”未纳入弹窗焦点环路的问题。
  - [x] SubTask 13.1: 扩展弹窗统一可聚焦元素选择器，将可见、可用的 `summary` 纳入焦点集合，同时继续排除隐藏、禁用和不可见元素。
  - [x] SubTask 13.2: 在独立任务模版库与新建策略对话两个详情入口验证初始焦点、Tab 正向环路和 Shift+Tab 反向环路，确保焦点可到达“任务指令”且不离开弹窗。
  - [x] SubTask 13.3: 验证“任务指令”通过 Enter 和 Space 均可展开、收起，折叠内容状态与键盘焦点语义一致，Escape 关闭后焦点返回原触发控件。
  - [ ] SubTask 13.4: 在 1280×900、1024×768、760×900、390×844 下复验双入口的折叠指令与完整键盘环路；修复后重新执行全部 116 个 checkpoint。

- [ ] Task 14: 修复统一弹窗焦点陷阱在中间 Tab 顺序中跳过 `summary` 的缺陷。
  - [x] SubTask 14.1: 修改 `trapFocus`，在每次 Tab 或 Shift+Tab 键盘事件发生时重新调用 `getFocusableElements` 获取包含可见、可用 `summary` 的统一可聚焦列表，不再只在焦点位于首尾边界时干预并依赖浏览器默认顺序。
  - [x] SubTask 14.2: 基于当前焦点在统一可聚焦列表中的索引计算下一或上一元素；每次 Tab/Shift+Tab 均执行 `preventDefault`，并显式聚焦计算所得元素，首尾按方向循环。
  - [x] SubTask 14.3: 处理当前焦点不在列表、聚焦目标被动态移除，以及元素隐藏或禁用的情况；每次按键使用最新列表并提供留在当前弹窗内的有效回退焦点，不得将焦点留在失效节点、`body` 或弹窗外。
  - [x] SubTask 14.4: 复验所有使用统一 `trapFocus` 的共享 modal 的正向与反向完整焦点顺序，并重点验证独立任务模版库和新建策略对话双入口详情中的“任务指令”`summary` 不再被跳过。
  - [ ] SubTask 14.5: 复验双入口 `summary` 的 Enter/Space 展开收起、Escape 关闭与关闭后焦点恢复，在 1280×900、1024×768、760×900、390×844 四个视口留存证据，并重新执行全部 116 个 checklist checkpoint 及既有语法、重复 ID、`git diff --check`、控制台、无障碍、主链路和回归检查。

- [ ] Task 15: 修复统一弹窗焦点陷阱同步聚焦后仍发生额外默认或自动化焦点移动的缺陷。
  - [x] SubTask 15.1: `trapFocus` 同步聚焦计算所得目标后，通过 `queueMicrotask` 或等价的事件结束后机制校验预期目标仍然有效且保持焦点；若焦点已偏离，则重新聚焦预期目标。
  - [x] SubTask 15.2: 事件结束后若预期目标已被移除、隐藏或禁用，使用最新 `getFocusableElements` 列表和原 Tab/Shift+Tab 方向计算弹窗内回退目标，不得将焦点留在失效节点、`body` 或弹窗外。
  - [x] SubTask 15.3: 限制事件结束后校验与补偿聚焦的调度和重试边界，不得无限递归、重复消费同一按键或破坏真实键盘的 Tab、Shift+Tab、Enter、Space 和 Escape 行为。
  - [x] SubTask 15.4: 复验独立任务模版库与新建策略对话双入口详情的正向、反向完整焦点顺序，并验证所有使用统一 `trapFocus` 的其他共享 modal。
  - [ ] SubTask 15.5: 在 1280×900、1024×768、760×900、390×844 四个视口留存证据，并重新执行全部 116 个 checklist checkpoint 及既有语法、重复 ID、`git diff --check`、控制台、无障碍、主链路和回归检查。

- [ ] Task 16: 修复共享 modal 中“任务指令”`summary` 聚焦后无法通过 Enter/Space 展开或收起的缺陷。
  - [x] SubTask 16.1: 在共享 modal 键盘路径中明确识别事件目标是否为“任务指令”`summary`，并定位其所属 `details`；仅对有效目标处理 Enter 和 Space，不影响其他按键、控件或弹窗。
  - [x] SubTask 16.2: 对每次有效 Enter/Space 按键仅执行一次 `preventDefault`，并仅切换一次对应 `details.open`，避免浏览器原生行为与自定义处理叠加造成双切换。
  - [x] SubTask 16.3: 展开或收起后保持焦点位于原“任务指令”`summary`；鼠标点击继续使用正常原生交互，不得被键盘补丁重复消费或阻断。
  - [x] SubTask 16.4: 复验独立任务模版库与新建策略对话双入口中的 Enter/Space 展开收起、Tab/Shift+Tab 完整焦点顺序、Escape 关闭及关闭后焦点恢复，并确认共享 modal 中其他 `details` 和既有键盘行为不回归。
  - [ ] SubTask 16.5: 在 1280×900、1024×768、760×900、390×844 四个视口留存双入口证据，并重新执行全部 checklist checkpoint 及既有语法、重复 ID、`git diff --check`、控制台、无障碍、主链路和回归检查。

- [ ] Task 17: 修复“任务指令”`summary` 通过 Enter/Space 切换后焦点在下一帧掉到 `body` 的缺陷。
  - [x] SubTask 17.1: 对有效 Enter/Space 按键仅切换一次对应 `details.open`，并在切换后仅调度一次下一帧校验，不得在校验或补偿聚焦时再次切换展开状态。
  - [x] SubTask 17.2: 下一帧校验原 `summary` 仍然有效、可见且 `document.activeElement` 仍指向该元素；元素有效但焦点偏离时，将焦点恢复到原 `summary`。
  - [x] SubTask 17.3: 若原 `summary` 已被移除、隐藏、禁用或不再属于当前打开的 modal，基于当前 modal 的最新可聚焦元素集合选择有效回退焦点，焦点不得留在 `body`、失效节点或 modal 外。
  - [x] SubTask 17.4: 将下一帧校验与补偿限制为一次性、非递归流程，不合成或重复消费键盘事件，不造成 Enter/Space 双切换，且不影响鼠标原生交互、Tab/Shift+Tab 焦点环路和 Escape 关闭行为。
  - [ ] SubTask 17.5: 在干净且仅保留一个 localhost 标签的环境中复验独立任务模版库与新建策略对话双入口的 Enter/Space 展开和收起、焦点保持与回退；覆盖 1280×900、1024×768、760×900、390×844 四个视口，并重新执行全部 checklist checkpoint。

- [ ] Task 18: 在保留全部定时任务功能的前提下，恢复独立“任务模版”入口并与“设置定时任务”并列。
  - [x] SubTask 18.1: 在工作区 DOM 中恢复独立的 `taskTemplateButton`，使用“任务模版”可见文案、可访问名称、tooltip 和模版图标语义；保留 `scheduledTaskButton` 的“设置定时任务”文案、闹钟图标及对应 `aria-label` 和 tooltip，不复用或覆盖任一入口。
  - [x] SubTask 18.2: 扩展 `syncWorkspaceEntryState` 及相关打开、隐藏和活动态同步逻辑，使“任务模版”与“设置定时任务”分别按当前视图正确显示、隐藏和标记活动态，且不破坏其他工作区入口状态。
  - [x] SubTask 18.3: 为两个入口保留独立点击职责：`taskTemplateButton` 进入 `task-template` 视图，`scheduledTaskButton` 继续进入 `scheduled-task` 视图；不得回滚定时任务的创建、编辑、状态或其他既有能力。
  - [x] SubTask 18.4: 恢复从任务模版视图返回来源工作区的既有行为，并复验定时任务视图的返回行为、入口活动态和来源状态互不串写。
  - [ ] SubTask 18.5: 复验两个入口的产品职责、可见文案、图标语义、可访问名称、tooltip、点击路由、活动态和返回链路；覆盖 1280×900、1024×768、760×900、390×844 四个视口及仅键盘操作，并重新执行全部 checklist checkpoint。

- [ ] Task 19: 修复任务模版验证失败后未聚焦首个字段级错误的缺陷。
  - [ ] SubTask 19.1: 验证失败后，在当前打开的 modal 内按 DOM 顺序查找首个可见、可用的 `[aria-invalid="true"]` 字段并聚焦，优先定位变量键和其他具体字段；将第二个变量键改为重复“活动”时，焦点必须落到首个无效变量键 `taskVariableKey0`，不得错误回到任务指令。
  - [ ] SubTask 19.2: 仅当不存在可聚焦的字段级错误时，才将焦点回退到任务指令或验证摘要；处理错误字段被动态移除、隐藏或禁用的情况，焦点不得落到 `body`、失效节点或 modal 外。
  - [ ] SubTask 19.3: 聚焦错误字段时保持既有 `aria-invalid` 与 `aria-describedby` 错误关联，不清除或串写错误信息；必要的滚动仅发生在 modal 内，页面不得滚出弹窗。
  - [ ] SubTask 19.4: 将同一验证失败焦点策略统一应用于重复变量键、空变量键、占位符同步错误、创建流程第二步及发起任务运行表单，不破坏 Tab/Shift+Tab 焦点环路、Escape 关闭与关闭后焦点恢复。
  - [ ] SubTask 19.5: 使用仅键盘操作覆盖 1280×900、1024×768、760×900、390×844 四个视口，复验各类字段级错误的 DOM 顺序、可见可用过滤、焦点、错误关联和 modal 内滚动，并重新执行全部 checklist checkpoint。

# Task Dependencies

- Task 2 depends on Task 1.
- Task 3 depends on Tasks 1 and 2.
- Task 4 depends on Tasks 1 and 3.
- Task 5 depends on Tasks 1 through 3.
- Task 6 depends on Tasks 1, 2 and 5.
- Task 7 depends on Tasks 1, 3, 5 and 6.
- Task 8 depends on Tasks 2 through 7 and Task 9.
- Task 9 depends on Tasks 2, 3 and 5.
- Task 8 additionally depends on Task 10.
- Task 8 additionally depends on Task 11.
- Task 8 additionally depends on Task 12.
- Task 8 additionally depends on Task 13.
- Task 8 additionally depends on Task 14.
- Task 8 additionally depends on Task 15.
- Task 8 additionally depends on Task 16.
- Task 10 depends on Task 2.
- Task 11 depends on Task 3.
- Task 12 depends on Task 5.
- Task 12 additionally depends on Task 14.
- Task 12 additionally depends on Task 15.
- Task 12 additionally depends on Task 16.
- Task 13 depends on Task 12.
- Task 13 additionally depends on Task 14.
- Task 13 additionally depends on Task 15.
- Task 13 additionally depends on Task 16.
- Task 14 additionally depends on Task 15.
- Task 14 additionally depends on Task 16.
- Task 15 additionally depends on Task 16.
- Task 8 additionally depends on Task 17.
- Task 12 additionally depends on Task 17.
- Task 13 additionally depends on Task 17.
- Task 14 additionally depends on Task 17.
- Task 15 additionally depends on Task 17.
- Task 16 additionally depends on Task 17.
- Task 8 additionally depends on Task 18.
- Task 12 additionally depends on Task 18.
- Task 13 additionally depends on Task 18.
- Task 14 additionally depends on Task 18.
- Task 15 additionally depends on Task 18.
- Task 16 additionally depends on Task 18.
- Task 17 additionally depends on Task 18.
- Task 8 additionally depends on Task 19.
- Task 12 additionally depends on Task 19.
- Task 13 additionally depends on Task 19.
- Task 14 additionally depends on Task 19.
- Task 15 additionally depends on Task 19.
- Task 16 additionally depends on Task 19.
- Task 17 additionally depends on Task 19.
- Task 18 additionally depends on Task 19.
- Tasks 4 and 6 can be implemented in parallel after their dependencies are complete.

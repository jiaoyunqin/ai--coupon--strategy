# Tasks

- [x] Task 1: 建立新建策略对话的内置模板数据与填入契约。
  - [x] SubTask 1.1: 在 `index.html` 中集中定义 4 个促前、5 个促中模板，包含稳定 ID、阶段、标题、场景说明和完整问题。
  - [x] SubTask 1.2: 为 `newChatState` 增加默认值为“全部”的模板筛选状态，避免把筛选状态混入消息或推荐上下文。
  - [x] SubTask 1.3: 实现按模板阶段读取当前活动、周期和可用波次/场次的上下文解析，复用 `preGetPlanningActivity()`、`getMidCampaignContext()` 及现有波次状态。
  - [x] SubTask 1.4: 实现固定格式的模板文本构建；无有效波次/场次时省略该行，不生成占位或虚构信息。

- [x] Task 2: 扩展新建策略对话空状态并展示全部内置模板。
  - [x] SubTask 2.1: 保留现有欢迎信息和三条推荐问题，在其下新增模板区。
  - [x] SubTask 2.2: 新增“全部 / 促前 / 促中”互斥筛选控件，默认展示全部 9 个模板。
  - [x] SubTask 2.3: 以卡片形式展示阶段标签、标题、简短场景说明和“使用模板”操作，不加入精选、搜索、收藏或创建入口。
  - [x] SubTask 2.4: 调整空状态滚动和响应式布局，使模板内容可浏览且底部输入框保持现有位置。

- [x] Task 3: 实现模板筛选和仅填入输入框的交互。
  - [x] SubTask 3.1: 筛选操作只更新模板列表及选中语义，不影响推荐问题、输入内容和工作台状态。
  - [x] SubTask 3.2: 点击模板卡片或“使用模板”时整体替换输入框内容，调用现有自动高度调整并聚焦输入框。
  - [x] SubTask 3.3: 确保模板使用不调用 `submitNewChatQuestion`、不新增消息、不启动进度动画、不切换视图。
  - [x] SubTask 3.4: 支持模板连续替换，并保持输入内容可编辑。

- [x] Task 4: 完成视觉、键盘和无障碍收敛。
  - [x] SubTask 4.1: 复用当前视觉 token，为模板区补充与现有新建对话一致的字体、蓝色强调、圆角、边框、阴影、悬停和焦点状态。
  - [x] SubTask 4.2: 为筛选控件提供互斥选中语义，为模板卡片提供包含标题的可访问名称。
  - [x] SubTask 4.3: 验证 Tab、Enter 和 Space 可完成筛选及模板填入，筛选后焦点不落在隐藏卡片。
  - [x] SubTask 4.4: 验证桌面与窄视口下模板网格、内容滚动和固定输入区没有新增横向溢出或文本截断。

- [x] Task 5: 定向验证与回归。
  - [x] SubTask 5.1: 验证默认全部 9 个模板、促前 4 个模板和促中 5 个模板的数量、顺序、标题及完整问题。
  - [x] SubTask 5.2: 分别验证促前和促中模板使用时带入正确活动，促中带入当前波次，缺少波次时正确省略该行。
  - [x] SubTask 5.3: 验证模板只填入输入框，消息数量、对话进度和当前视图均不变化。
  - [x] SubTask 5.4: 回归三条现有推荐问题、手动发送、清空、模型选择、返回工作台和上下文追问入口。
  - [x] SubTask 5.5: 执行 JavaScript 语法、静态重复 ID、`git diff --check`、浏览器控制台和基础无障碍检查。

- [x] Task 6: 修复模板波次上下文与静态重复 ID 验证失败。
  - [x] SubTask 6.1: 增加促前波次显式选择标记，仅在用户通过现有波次交互选择后为促前模板带入“券波次/场次”，并验证默认省略、显式选择后带入及活动切换/相关重置后再次省略。
  - [x] SubTask 6.2: 将重复的 `mid38RhythmEmptyTitle` 替换为稳定唯一 ID、同步关联的 ARIA 引用，并验证静态重复 ID 检查通过。

- [x] Task 7: 修复模板筛选与模板使用的显式键盘触发。
  - [x] SubTask 7.1: 在 `newChatMainStream` 的 `keydown` 委托中，对模板筛选和模板操作的 Enter/Space 阻止默认行为并调用现有筛选/使用函数。
  - [x] SubTask 7.2: 验证筛选后焦点恢复到新选中的筛选按钮、模板使用后输入框获得焦点，并确认现有点击行为不双触发。
  - [x] SubTask 7.3: 执行 JavaScript 语法、静态重复 ID、`git diff --check` 和最小键盘行为检查。

# Task Dependencies

- Task 2 depends on Task 1.
- Task 3 depends on Task 1 and Task 2.
- Task 4 depends on Task 2 and Task 3.
- Task 5 depends on Task 1 through Task 4.
- Task 6 depends on Task 1 through Task 4.
- Task 7 depends on Task 3 and Task 4.

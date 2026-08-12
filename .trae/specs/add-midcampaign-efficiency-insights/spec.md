# 促中效率洞察与竞对对齐 Spec

## Why

`03 实时监控与调优建议` 已具备趋势、人群/渠道/面额拆解和结论文案，但首屏仍偏向单维数据展示，缺少可直接支持决策的类目转化、人群与客单关系、细粒度点位效率洞察。需要在保持高信息密度的前提下，建立“结论 + 关键证据 + 建议 + 展开详情”的统一分析入口。

## What Changes

- 在 `03.2 核销与实验分析` 中增加“效率洞察”区域，包含：
  - 类目转化效率
  - 人群 × 客单价效率
  - 点位效率
- 三类洞察首屏均只展示一个核心结论、2—3 个关键指标和一条建议，不直接铺开技术宽表。
- 每张洞察卡支持点击展开详情；同一时间最多展开一类详情，展开区承载图表、完整数据表和数据口径。
- 类目洞察同时支持“行业效率”和“行业 × 档位”两个详情视图。
- 人群洞察同时支持“消费力等级”和“八大人群”两个详情视图；“人群 × 客单价”使用各人群平均客单与核销效率的关系展示，不虚构参考表中不存在的客单价分桶。
- 点位洞察下钻到具体资源点位，展示领券、核销、预算、引导 GMV、成本、订单和客单。
- 必要可视化使用轻量 SVG 图表，服务于比较和定位，不增加装饰性图形：
  - 类目：GMV 占比与预算占比对比
  - 人群：核销率 × 客单价气泡图
  - 点位：领券成本 × 核销率效率分布
- 保留现有趋势、消费券实验、领取核销拆解和 `03.4` 的一般归因结论；本次不新增异常检测、异常阈值、原因贡献度或自动异常归因。
- `03.3 竞对动态监控` 与促前竞对模块保持一致，补齐“动态播报 / 横向对比”双视图和相同的关注变化交互；本次不新增真实推送规则、推送渠道配置或推送历史。
- 所有新增内容遵循 03 章节现有主题色、数据上下文、空态和追问边界，不展示“Mock/真实数据”“Revision”等技术提示。

## Reference Data

- 类目效率：
  - `5-分行业`：行业 GMV、GMV 占比、核销预算、预算占比、券引导 GMV 渗透、支付用户数、订单数、ARPU、客单价。
  - `515-601行业✖️档位`：行业 × 券档的预算占比、券引导 GMV 占比及波次对比。
- 人群效率：
  - `8.分人群`：消费力等级的领券、核销、预算、订单 GMV、客单价及历史对比。
  - `7.八大人群`：八大人群的领券、核销、核销率、订单 GMV、客单价和预算。
- 点位效率：
  - `4.分渠道`：具体点位的领券、核销、预算、引导 GMV、领券用户成本、订单数和客单价。
- 竞对：
  - 复用促前规划竞对模块现有归档、横向对比和关注状态，不建立第二套竞对数据。

## Impact

- Affected specs:
  - `restructure-midcampaign-monitoring-hierarchy`
  - `enhance-precampaign-intelligence-cards`
  - 促中实时监控数据上下文与追问
- Affected code:
  - `/Users/bytedance/strategy2/index.html`
  - `03.2 核销与实验分析`
  - `03.3 竞对动态监控`
  - 促中证据目录、渲染状态和响应式样式

## Data Contract

新增 Mock 数据 SHALL 按活动、年份和波次上下文隔离，并保持数值与展示文案分离。建议结构如下：

```js
{
  contextKey,
  efficiencyInsights: {
    category: {
      conclusion,
      highlights: [{ label, value, tone }],
      recommendation,
      categoryRows: [{
        category, subcategory, paymentGmv, gmvShare,
        redemptionBudget, budgetShare, efficiencyGap,
        couponGmvPenetration, payUsers, orderCount,
        arpu, ordersPerUser, aov
      }],
      tierRows: [{
        category, tier, budgetShare, couponGmvShare,
        efficiencyGap, incrementalExchangeRatio
      }]
    },
    audience: {
      conclusion,
      highlights: [{ label, value, tone }],
      recommendation,
      powerRows: [{
        segment, claimUv, claimShare, redeemUv, redeemShare,
        redemptionRate, redemptionBudget, budgetShare,
        orderGmv, gmvShare, aov, claimEfficiencyGap,
        valueEfficiencyGap
      }],
      personaRows: [{
        segment, claimUv, claimShare, redeemUv, redeemShare,
        redemptionRate, redemptionBudget, budgetShare,
        orderGmv, gmvShare, aov, claimEfficiencyGap,
        valueEfficiencyGap
      }]
    },
    placement: {
      conclusion,
      highlights: [{ label, value, tone }],
      recommendation,
      rows: [{
        placement, claimUv, claimShare, redeemUv,
        redemptionRate, redemptionBudget, budgetShare,
        guidedGmv, gmvShare, claimCost, orderCount,
        aov, efficiencyStatus
      }]
    }
  }
}
```

- `efficiencyGap` SHALL 使用同口径的 `GMV 占比 - 预算占比`。
- `claimEfficiencyGap` SHALL 使用 `核销 UV 占比 - 领券 UV 占比`。
- `valueEfficiencyGap` SHALL 使用 `GMV 占比 - 预算占比`；缺少 GMV 占比时保持为空，不得用其他活动补齐。
- 百分比、金额和人数 SHALL 以可计算数值存储，由格式化函数输出展示文本。
- 结论和建议 SHALL 只引用同一 `contextKey` 下存在的事实字段。

## ADDED Requirements

### Requirement: 效率洞察首屏以结论驱动

系统 SHALL 在 `03.2` 中提供类目、人群和点位三张效率洞察卡，每张卡均以决策信息优先。

#### Scenario: 默认浏览效率洞察

- **WHEN** 用户进入有数据的 `03.2`
- **THEN** 用户看到类目、人群和点位三张洞察卡
- **AND** 每张卡只展示核心结论、2—3 个关键指标和一条建议
- **AND** 首屏不直接展示完整宽表
- **AND** 洞察卡内部色彩统一使用 03 章节主题色

#### Scenario: 展开和切换详情

- **WHEN** 用户点击任一洞察卡的“查看详情”
- **THEN** 对应详情区在卡片下方展开
- **AND** 详情区展示该洞察的图表和数据表
- **AND** 再点击其他洞察卡时切换到新详情
- **AND** 同一时间最多展开一类详情
- **AND** 用户可以点击“收起详情”返回紧凑首屏

### Requirement: 类目转化效率洞察

系统 SHALL 使用行业经营表现与行业 × 券档数据解释类目预算转化效率。

#### Scenario: 查看类目结论

- **WHEN** 当前上下文存在行业数据
- **THEN** 类目卡展示效率最高或规模最关键的类目结论
- **AND** 关键证据至少包含 GMV 占比、预算占比或两者差值
- **AND** 建议明确指出应优先验证、保量或收缩的类目方向

#### Scenario: 展开行业效率

- **WHEN** 用户展开类目详情并选择“行业效率”
- **THEN** 展示 GMV 占比与预算占比对比图
- **AND** 展示行业、支付 GMV、GMV 占比、核销预算、预算占比、效率差、券 GMV 渗透、支付用户、订单和客单价
- **AND** 正向效率差和负向效率差具有清晰但不过度依赖颜色的状态标识

#### Scenario: 展开行业与档位

- **WHEN** 用户选择“行业 × 档位”
- **THEN** 展示行业、券档、预算占比、券引导 GMV 占比和效率差
- **AND** 存在增量兑换比时一并展示
- **AND** 用户可以识别同一行业中不同券档的效率差异

### Requirement: 人群与客单价效率洞察

系统 SHALL 联合核销效率、客单价和规模解释不同人群的价值差异。

#### Scenario: 查看人群结论

- **WHEN** 当前上下文存在人群数据
- **THEN** 人群卡展示高核销、高客单或规模贡献显著的人群结论
- **AND** 建议区分“扩量验证、稳量、收缩泛发”等动作
- **AND** 不仅凭客单价单指标得出扩量结论

#### Scenario: 查看消费力等级

- **WHEN** 用户展开人群详情并选择“消费力等级”
- **THEN** 展示 L1—L5 的核销率 × 平均客单关系图
- **AND** 气泡大小表达订单 GMV 或核销规模
- **AND** 明细表展示领券、核销、预算、订单 GMV和客单价

#### Scenario: 查看八大人群

- **WHEN** 用户选择“八大人群”
- **THEN** 图表和明细切换为八大人群口径
- **AND** 展示核销份额与领券份额差、GMV 份额与预算份额差
- **AND** 缺少某项份额时显示为空，不进行跨表或跨活动推断

### Requirement: 点位效率洞察

系统 SHALL 下钻到具体资源点位，而不是只展示“搜索、会场”等聚合渠道。

#### Scenario: 查看点位结论

- **WHEN** 当前上下文存在点位数据
- **THEN** 点位卡指出高效承接点位、规模底座点位和需要收缩的低效点位
- **AND** 结论同时考虑核销率、成本、GMV 和预算，不以单一指标排序

#### Scenario: 展开点位详情

- **WHEN** 用户展开点位详情
- **THEN** 展示领券成本 × 核销率效率分布图
- **AND** 展示点位、领券 UV、核销 UV、核销率、核销预算、引导 GMV、份额、领券成本、订单数和客单价
- **AND** 明细支持在容器内横向滚动
- **AND** 无数据点位显示“暂无数据”，不以 0 代替

### Requirement: 洞察与当前上下文一致

系统 SHALL 保证所有洞察、图表、表格、建议和追问使用同一活动、年份、波次及周期上下文。

#### Scenario: 切换上下文

- **WHEN** 用户切换活动、年份、波次、周期或端口
- **THEN** 三类洞察同步更新
- **AND** 已展开详情保留当前类型但刷新为新上下文数据
- **AND** 新上下文缺数时显示对应空态
- **AND** 不引用其他上下文的旧结论或旧数值

#### Scenario: 追问洞察

- **WHEN** 用户从某张洞察卡发起追问
- **THEN** 追问上下文包含当前洞察类型、当前筛选和可见关键证据
- **AND** 不携带未展开的其他洞察结论作为事实

### Requirement: 轻量可视化与可访问性

系统 SHALL 使用紧凑、可读且可访问的可视化辅助比较。

#### Scenario: 浏览图表

- **WHEN** 用户查看任一效率图表
- **THEN** 图表具有明确标题、图例和可读的数据标签或提示
- **AND** 图表信息可通过相邻表格完整获取
- **AND** 不仅依赖颜色表达正负或高低
- **AND** 减少动态效果设置生效时不执行非必要动画

#### Scenario: 响应式浏览

- **WHEN** 视口为桌面宽屏、1440px、1280px、1024px、860px 或 760px
- **THEN** 洞察卡按可用宽度从三列降为单列
- **AND** 展开详情不造成整页横向溢出
- **AND** 宽表仅在自身容器内滚动

## MODIFIED Requirements

### Requirement: 03.2 核销与实验分析

系统 SHALL 在保留趋势、领取核销拆解和消费券实验的基础上，增加类目、人群与点位效率洞察。现有领取核销数据可作为展开详情的数据来源，但不得在首屏与新增详情重复铺设相同宽表。

### Requirement: 03.3 竞对动态监控

系统 SHALL 与促前竞对模块保持相同的信息架构，提供“动态播报 / 横向对比”双视图、年份筛选、变化详情、应对建议和关注变化状态。促中 SHALL 复用同一份竞对归档和对比字段，不新增独立数据副本；本次关注变化仍为现有前端状态反馈，不扩展为真实消息推送系统。

#### Scenario: 查看竞对横向对比

- **WHEN** 用户在 `03.3` 选择“横向对比”
- **THEN** 展示与促前一致的竞对、券档、折扣、会员或张数、频次和变化方向
- **AND** 年份切换、空态和追问上下文与促前保持一致

### Requirement: 03.4 归因结论与调优提示

系统 SHALL 保留当前一般经营归因和调优提示，但本次不得新增异常检测、异常阈值、自动异常原因排行、贡献度或置信度模块。

## REMOVED Requirements

本次不移除现有用户可见能力。

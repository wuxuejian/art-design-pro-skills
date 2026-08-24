# Cards / Banners

## ArtStatsCard

用于 Dashboard 数值统计。

主要 props：

```ts
boxStyle?: string
icon?: string
iconStyle?: string
title?: string
count?: number
decimals?: number
separator?: string
description: string
textColor?: string
showArrow?: boolean
```

内部使用 `ArtCountTo` 做数字动画，因此业务页面只需要提供统计数据和展示配置。

## 其他 Card

- `ArtProgressCard`：进度/指标
- `ArtImageCard`：图片卡片
- `ArtDataListCard`：数据列表
- `ArtTimelineListCard`：时间线列表
- `ArtBarChartCard`：柱状图卡片
- `ArtLineChartCard`：折线图卡片
- `ArtDonutChartCard`：环形图卡片

## Banner

- `ArtBasicBanner`
- `ArtCardBanner`

适用于 Dashboard 欢迎区、运营宣传区、信息 Banner 等。

## 使用原则

Dashboard 页面优先通过现有 Card + Chart 组合实现，不要每个统计区块都创建一个业务 Card。

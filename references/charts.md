# Chart 组件

源码位置：`src/components/core/charts`。

图表统一通过项目 ECharts 插件和 `useChart` hooks 处理初始化、主题、resize、tooltip、legend 等基础逻辑。

## ArtLineChart

源码：`src/components/core/charts/art-line-chart/index.vue`。

支持：
- 单数据或多数据
- xAxisData
- 平滑曲线
- 区域渐变
- tooltip
- legend
- 动画
- loading
- empty
- 自定义颜色
- 轴线/刻度/分割线显示控制

常见 props：

```ts
height
loading
isEmpty
colors
data
xAxisData
lineWidth
showAreaColor
smooth
symbol
symbolSize
animationDelay
showAxisLabel
showAxisLine
showSplitLine
showTooltip
showLegend
legendPosition
```

多系列数据使用带 `name` 和 `data` 的结构；单系列可以直接传数字数组。

## 其他图表

- `ArtBarChart`：柱状图
- `ArtHBarChart`：横向柱状图
- `ArtDualBarCompareChart`：双柱比较
- `ArtKLineChart`：K 线
- `ArtMapChart`：地图
- `ArtRadarChart`：雷达
- `ArtRingChart`：环形
- `ArtScatterChart`：散点

使用前先查看对应源码 props/type，不要猜参数。

## 重要规则

不要在页面中直接复制 `echarts.init()` + option + resize + dispose 的 boilerplate。优先调用现成 Art 图表组件；只有图表需求明显超出 core 组件能力时才考虑直接使用项目 ECharts 封装。

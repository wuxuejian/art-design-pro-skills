# Core 组件清单

源码位置：`src/components/core`。

## banners

- `ArtBasicBanner`
- `ArtCardBanner`

用于欢迎区、宣传区、顶部 Banner 等通用展示。

## base

基础 UI 能力，例如 Logo、安全 HTML、SVG 图标、返回顶部等。

## cards

- `ArtBarChartCard`
- `ArtDataListCard`
- `ArtDonutChartCard`
- `ArtImageCard`
- `ArtLineChartCard`
- `ArtProgressCard`
- `ArtStatsCard`
- `ArtTimelineListCard`

## charts

- `ArtBarChart`
- `ArtDualBarCompareChart`
- `ArtHBarChart`
- `ArtKLineChart`
- `ArtLineChart`
- `ArtMapChart`
- `ArtRadarChart`
- `ArtRingChart`
- `ArtScatterChart`

## forms

- `ArtButtonMore`
- `ArtButtonTable`
- `ArtDragVerify`
- `ArtExcelExport`
- `ArtExcelImport`
- `ArtForm`
- `ArtSearchBar`
- `ArtWangEditor`

## tables

- `ArtTableHeader`
- `ArtTable`

## others

- `ArtMenuRight`
- `ArtWatermark`

## 其他 core 分类

`layouts`、`media`、`text-effect`、`theme`、`views`、`widget` 也属于 core，应优先搜索后再自己实现类似功能。

## 命名规律

组件源码目录通常为 kebab-case：

```text
src/components/core/forms/art-search-bar/
src/components/core/tables/art-table/
```

组件名通常为 PascalCase：`ArtSearchBar`、`ArtTable`。

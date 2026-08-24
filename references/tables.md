# ArtTable / ArtTableHeader

## ArtTable

源码：`src/components/core/tables/art-table/index.vue`。

ArtTable 在 ElTable 上扩展：

- 分页
- loading
- 自定义列
- 自定义表头 slot
- 全局序号 `globalIndex`
- 展开行 `expand`
- 空状态
- 表格尺寸
- 边框/斑马纹
- 表头背景
- 响应式分页
- 暴露内部 `elTableRef`

源码明确支持 ElTable 的属性、事件、插槽，因此已有 Element Plus 表格能力通常可以继续使用。

主要 props：

```ts
loading?: boolean
columns?: ColumnOption[]
pagination?: {
  current: number
  size: number
  total: number
}
paginationOptions?: {
  pageSizes?: number[]
  align?: 'left' | 'center' | 'right'
  layout?: string
  background?: boolean
  hideOnSinglePage?: boolean
  size?: 'small' | 'default' | 'large'
  pagerCount?: number
}
emptyHeight?: string
emptyText?: string
showTableHeader?: boolean
```

默认分页会根据屏幕宽度调整 layout：移动端、平板和桌面使用不同分页布局。

### 自定义列

优先使用项目 `ColumnOption` 类型支持的配置和 slot：

```ts
{
  prop: 'name',
  label: '名称',
  useSlot: true,
  slotName: 'name'
}
```

表头可以使用：

```ts
{
  prop: 'name',
  label: '名称',
  useHeaderSlot: true,
  headerSlotName: 'name-header'
}
```

## ArtTableHeader

负责表格顶部工具区。默认能力：

`search, refresh, size, fullscreen, columns, settings`

源码支持：

- 搜索栏显示/隐藏
- 刷新
- 表格大小
- 全屏
- 列显示/隐藏
- 列拖动排序
- 斑马纹
- 边框
- 表头背景
- left/right slots

典型结构：

```vue
<ArtTableHeader
  v-model:columns="columns"
  :loading="loading"
  @refresh="refresh"
>
  <template #left>
    <!-- 新增、批量操作等 -->
  </template>
</ArtTableHeader>
```

列设置基于 `ColumnOption` 的 `visible/checked/disabled/fixed` 等字段。

## CRUD 列表建议

优先：`ArtSearchBar -> ArtTableHeader -> ArtTable`，数据请求和分页由页面/useTable 管理。

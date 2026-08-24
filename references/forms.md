# ArtForm / ArtSearchBar

## ArtSearchBar

源码：`src/components/core/forms/art-search-bar/index.vue`。

它是建立在 Element Plus ElForm/ElRow/ElCol 之上的配置型搜索组件，支持常用表单组件、自定义组件、slot、校验、隐藏项目、响应式栅格和展开/收起。

主要 props：

- `items: SearchFormItem[]`
- `span?: number`，默认 6
- `gutter?: number`，默认 12
- `isExpand?: boolean`
- `defaultExpanded?: boolean`
- `labelPosition?: 'left' | 'right' | 'top'`
- `labelWidth`
- `showExpand`
- `showReset`
- `showSearch`
- `disabledSearch`
- `sanitizeOutput`

SearchFormItem 常用字段：

```ts
{
  key: 'username',
  label: '用户名',
  type: 'input',
  placeholder: '请输入用户名',
  props: {},
  span: 6,
  hidden: false
}
```

内置 type 包括：`input`、`inputTag`、`number`、`select`、`switch`、`checkbox`、`checkboxgroup`、`radiogroup`、`date`、`daterange`、`datetime`、`datetimerange`、`rate`、`slider`、`cascader`、`timepicker`、`timeselect`、`treeselect`。

需要自定义组件时优先 `render` 或动态 slot。

搜索事件会输出经过清洗的查询参数。当前实现默认移除空字符串、空数组、空对象和空富文本，但保留 `0` 和 `false` 等有效值。

## ArtForm

`ArtForm` 与 ArtSearchBar 的配置思想相同，但面向提交表单。支持 Element Plus 常用控件、自定义 render、slot、响应式布局、校验、reset、submit 和提交数据清洗。

表单简单时优先使用 ArtForm；复杂表单可以在其基础上通过 render/slot 扩展，而不是修改 core。

## 注意

不要假设 `items` 中所有 Element Plus props 都是一级字段。组件会区分组件自身配置和传递给内部控件的 props；推荐把内部控件属性放到 `props` 中，除非源码明确允许直接透传。

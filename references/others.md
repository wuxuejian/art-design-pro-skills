# 其他 Core 组件

`src/components/core` 不只有表单、表格、图表，还包含：

- base：基础能力
- layouts：布局
- media：媒体、图片处理等
- others：例如 `ArtMenuRight`、`ArtWatermark`
- text-effect：数字动画、文本滚动等
- theme：主题相关
- views：登录、异常、结果等通用视图
- widget：小部件，例如 ArtIconButton

## 原则

遇到以下需求先搜索 core：

- 水印
- 返回顶部
- SVG 图标
- 图片裁剪/媒体展示
- 文本滚动/数字动画
- 通用布局
- 登录/异常/结果页
- 主题切换
- 菜单右键
- 图标按钮

不要因为需求看起来简单就直接写临时组件；先确认 core 是否已有能力。

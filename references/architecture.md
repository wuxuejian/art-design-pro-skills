# Art Design Pro 架构参考

## 官方定位

Art Design Pro 是企业级中后台解决方案，强调用户体验、视觉设计、组件复用和开发效率。官方技术栈：Vue 3、TypeScript、Vite、Element Plus、Tailwind CSS、Sass；工程化使用 ESLint、Prettier、Stylelint、Husky、Lint-staged、cz-git。

## 目录职责

```text
src/
├── api/              API 接口
├── assets/            静态资源和全局样式
├── components/
│   ├── business/     业务通用组件
│   └── core/         系统通用组件
├── config/            配置
├── directives/        Vue 指令
├── enums/             枚举
├── hooks/             Composables
├── layouts/           应用布局
├── router/            路由
├── store/             Pinia
├── types/             TypeScript 类型
├── utils/             工具
└── views/             业务页面
```

## 页面分层

```text
views/system/user/
├── index.vue
└── modules/
    ├── user-search.vue
    └── user-dialog.vue
```

index 负责编排和状态；modules 负责页面私有复杂 UI；稳定跨页面能力才进入 components/business；系统级能力进入 components/core。

## 组件选择顺序

业务页面 -> core component -> Element Plus -> 自己实现。

只有现有组件无法满足需求时才直接使用 Element Plus；只有现有组件和 Element Plus 都无法合理满足时才创建业务组件。

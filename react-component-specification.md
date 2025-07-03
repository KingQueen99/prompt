# ADDebug React 组件开发规范

本文档旨在提供一套标准化的规范，用于指导和统一 ADDebug 项目中 React 组件的开发。

## 1. UI 设计稿

*   **Figma 地址**: `{{FIGMA_URL}}`
*   **像素级精准实现**: 最终实现必须与 Figma 设计稿在视觉上完全一致。所有后续的规范都服务于此核心要求。
*   **颜色规范**: 必须严格使用项目内 `color.md` 文件中定义的颜色变量。不允许在组件样式中使用任何硬编码的颜色值（如 `#FFFFFF` 或 `rgb(0,0,0)`）。
*   **间距与布局**: 
    *   所有布局和间距（`margin`, `padding`, `gap` 等）的数值必须直接从 Figma 设计稿中测量获取。
    *   应遵循项目统一的 8px 网格系统进行布局，即所有间距数值应为 8 的倍数。
*   **文案内容**: 组件中所有静态文案（包括标题、标签、按钮文字、提示信息等）必须与 Figma 设计稿中的文案完全一致，不允许有任何偏差。

## 2. 技术规范

### 基础组件

*   项目统一使用 `antd` `v5.25.4` 版本作为基础组件库。
*   在代码中引用组件时，必须将 `antd` 的引用路径替换为 `@byted-evo/ui`。例如：`import { Button } from '@byted-evo/ui';`

### 图标使用

*   组件中所有图标都必须使用 `IconPark` 图标库。
*   请参考 `IconPark` 的官方使用文档进行安装和按需引入，以减小打包体积。

### 类型处理

*   如果遇到 `@byted-evo/ui` 缺少类型（例如 `TableColumnsType`）的问题，**必须主动询问用户**，并根据用户的选择决定解决方案：
    1.  从 `antd` 库中引入相应的类型，并确保 `antd` 已被添加到项目依赖中。
    2.  将该类型设置为 `any`。

## 3. 文件结构

每个组件都应拥有自己独立的文件夹，并严格遵循以下文件结构。可以根据需要添加新的文件（如 `constants.tsx`, `columns.tsx` 等）。

```
└── {{xxx-yyy}}/            # 组件文件夹, e.g., instance-list
    ├── index.tsx          # 组件入口文件
    ├── index.module.less  # Less Module 样式文件
    └── type.ts            # TypeScript 类型定义文件
```

## 4. 文件内容模板

创建新组件时，请使用以下模板。其中 `{{xxx-yyy}}` 是组件的连字符名称（例如 `instance-list`），`{{XxxYyy}}` 是组件的大驼峰名称（例如 `InstanceList`）。

### `type.ts`

```typescript
export interface {{XxxYyy}}Props {

}
```

### `index.module.less`

```less
.{{xxx-yyy}} {

}
```

### `index.tsx`

```typescript
import React, { FC } from 'react';
import styles from './index.module.less';
import { {{XxxYyy}}Props } from './type';

const {{XxxYyy}}: FC<{{XxxYyy}}Props> = () => {
  return (
    <div className={styles['{{xxx-yyy}}']}>
      {{xxx-yyy}}
    </div>
  );
};

export default {{XxxYyy}};
```
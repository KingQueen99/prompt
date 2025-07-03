# 初始化（新建）一个ADDebug Component（组件）

本文档旨在提供一个标准化的模板，用于在项目任意位置快速创建一个新的 React 组件。

在开始之前，请确保您已熟悉并遵循 https://raw.githubusercontent.com/KingQueen99/prompt/main/react-component-specification.md。

## 1. 创建位置

你可以在当前项目中的任何目录下创建新组件。例如，在 `xxx` 文件夹下创建名为 `{{xxx-yyy}}` 的组件。

## 2. 目录结构

每个组件都应拥有自己独立的文件夹，并包含以下文件：

```
└── {{xxx-yyy}}/            # 组件文件夹, e.g., instance-list
    ├── index.tsx          # 组件入口文件
    ├── index.module.less  # Less Module 样式文件
    └── type.ts            # TypeScript 类型定义文件
```

## 3. 文件内容模板

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

# 创建 ADDebug 组件

根据用户输入，判断是初始化组件还是创建 Table 组件。

## 规则

1.  **如果用户输入包含“初始化”和“组件”**:
    - 在当前目录下查找并遵循 `init-react-component.md` 中的所有指令。
    - 例如: `初始化 instance-list 组件`

2.  **如果用户输入包含“创建”、“table”和“组件”**:
    - 在当前目录下查找并遵循 `create-ad-debug-table.md` 中的所有指令。
    - 例如: `创建一个 instance-list 的 table 组件`

## 引用文档

-   初始化组件: `init-react-component.md`
-   创建 Table 组件: `create-ad-debug-table.md`

请严格按照上述规则执行。
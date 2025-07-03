### 创建 ADDebug Table 组件提示词模板

你好，请根据以下要求创建一个 ADDebug Table 组件，在开始之前，请确保您已熟悉并遵循 `react-component-specification.md`。

**1. 组件基本信息**

*   **组件名称**: `{{COMPONENT_NAME}}` (例如: `InstanceList`)
*   **组件目录**: `src/components/{{COMPONENT_DIRECTORY}}` (例如: `instance-list`)

**2. 实现细节**

*   **基础组件**: 使用 `@byted-evo/ui` 的 `Table` 组件作为基础。
*   **代码结构**: 将表格的列定义（columns）封装在一个独立的 `getColumns` 方法中，并存放在 `columns.tsx` 文件里。在 `constants.tsx` 文件中创建并导出 mock 数据。
*   **布局与样式**: 为表格设置 `tableLayout="fixed"` 属性，并为所有列设置 `width: 180`。
*   **颜色规范**: 必须严格使用项目内 `color.md` 文件定义的 `AD Debug color` 规范。

**3. 列渲染（Column Rendering）规范**

请根据 Figma 设计稿中各列的数据类型，使用对应的 `TableColRender` 组件进行渲染。以下是具体使用方法和传参示例：

*   **纯文本**: 使用 `TableColRender.Text`。
    *   **实现**: `render: text => <TableColRender.Text data={text} />`

*   **名称+ID（两行展示）**: 使用 `TableColRender.TitleWithCopyableId`。
    *   **实现**: `render: (text, record) => <TableColRender.TitleWithCopyableId title={record.name} id={record.id} />`

*   **ID 列表**: 使用 `TableColRender.IDList`。
    *   **实现**: `render: ids => <TableColRender.IDList ids={ids} />`

*   **图表结构**: 使用 `TableColRender.Trend`。
    *   **实现**: `render: data => <TableColRender.Trend data={data} />`
    *   **注意**: 确保传入的 `data` 是 `number[]` 类型。

*   **操作按钮**: 使用 `TableColRender.Actions`。
    *   **实现**: `render: (text, record) => <TableColRender.Actions actions={[{ name: '编辑', onClick: () => handleEdit(record) }, { name: '删除', onClick: () => handleDelete(record) }]} />`

请严格按照上述规范完成组件的创建。在每一步操作后，请告知我你的进展。
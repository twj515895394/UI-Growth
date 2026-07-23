# UI Component Rules

## 1. 组件体系

- 基础组件库：
- 二次封装目录：
- 样式方案：
- Token 来源：
- 新组件优先级：现有业务组件 → 现有基础组件 → 组件库能力 → 新建组件

## 2. Button

- 默认尺寸：
- 主按钮使用场景：
- 次按钮使用场景：
- 危险按钮使用场景：
- 图标按钮规则：
- Loading/Disabled：
- 禁止事项：

## 3. Input / Select / Date / Number

- 默认尺寸：
- 宽度策略：
- Placeholder：
- Prefix/Suffix：
- Error/Disabled/Readonly：
- 长内容处理：

## 4. Form Item

- Label 宽度与对齐：
- 必填标记：
- 帮助文字：
- 错误信息：
- 行列间距：

## 5. Card

- 使用场景：
- 默认 Padding：
- 圆角/边框/阴影：
- Header/Footer：
- 卡片间距：
- 可点击卡片状态：

## 6. Table

- 默认密度：
- 表头：
- 单元格：
- 操作列：
- 固定列：
- 空/加载/错误：
- 长文本：
- 移动端策略：

## 7. Tag / Badge / Status

| 语义 | 组件/Variant | 颜色 Token | 使用场景 |
|---|---|---|---|
|  |  |  |  |

## 8. Modal / Drawer

- 选择规则：
- 默认尺寸：
- Title/Footer：
- 表单布局：
- 长内容滚动：
- 危险操作：
- 小屏策略：

## 9. Pagination

- 位置：
- 与内容距离：
- 小屏策略：
- 总数与页大小：

## 10. Empty / Loading / Error

- Empty 必须包含：
- Loading 形式：
- Error 位置与重试：
- 骨架结构：

## 11. Navigation

- 当前项：
- 折叠：
- 层级：
- 图标：
- 小屏策略：

## 12. 组件覆盖规则

- 允许通过正式 Props、Variant 或 Token 调整；
- 页面专属布局优先放在页面容器；
- 不通过深层选择器修改第三方组件内部结构，除非有明确封装；
- 不使用无说明的 `!important`；
- 公共组件新增 Variant 前评估复用场景。

## 13. 例外

| 组件 | 例外 | 原因 | 作用范围 | 决策记录 |
|---|---|---|---|---|
|  |  |  |  |  |

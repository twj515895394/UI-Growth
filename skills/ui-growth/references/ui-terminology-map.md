# UI 口语表达与专业术语映射

本文件不是机械替换表。必须结合截图、DOM、Computed Style 和上下文判断真实含义。

## 使用规则

1. 先确认用户指向的对象；
2. 判断问题发生在元素内部、元素之间还是父布局；
3. 区分视觉症状和实现原因；
4. 给出用户能理解的专业解释；
5. 只有在证据充分时才指出具体 CSS 属性。

## 常见表达

| 用户表达 | 可能的专业问题 | 优先检查 |
|---|---|---|
| 太挤了 | 信息密度过高、间距不足、控件尺寸过大 | gap、padding、line-height、控件高度、内容数量 |
| 太空了 | 外部间距、内部留白、固定高度或列宽过大 | gap、margin、padding、min-height、Grid 列宽 |
| 不齐 | 水平、垂直、基线或网格边缘未对齐 | align-items、baseline、控件高度、padding |
| 太靠边了 | 页面安全边距或容器内边距不足 | 页面 padding、容器 max-width、safe area |
| 卡片太厚 | 内部 Padding、最小高度、标题区高度或阴影视觉重量过大 | padding、min-height、header height、shadow |
| 看起来很重 | 边框、阴影、字重、颜色对比或组件数量过强 | border、shadow、font-weight、surface contrast |
| 没有重点 | 视觉层级不足 | 字号、字重、颜色、留白、主次操作 |
| 页面很乱 | 网格、层级、对齐或信息组织不稳定 | 布局结构、重复组件、视觉焦点 |
| 像拼起来的 | 组件规范、间距尺度或表面处理不一致 | Token、公共组件、局部覆盖 |
| 按钮不好看 | 尺寸、圆角、字重、颜色、图标间距或状态不完整 | height、padding、radius、icon gap、variants |
| 这里会跳 | 布局偏移、异步内容高度变化或状态切换不稳定 | CLS、骨架、固定占位、条件渲染 |
| 太堵 | 内容贴边、区块之间缺乏呼吸空间 | padding、gap、边界层级 |
| 太散 | 区块关系弱、间距尺度过大 | section gap、grouping、proximity |
| 字看起来飘 | 行高、基线、字体回退或垂直居中问题 | line-height、font metrics、align-items |
| 一屏东西太少 | 页面密度偏低 | 行高、卡片高度、区块间距、冗余说明 |
| 一屏东西太多 | 认知负担或密度过高 | 分组、折叠、优先级、分页 |
| 不高级 | 视觉语言不克制或缺少一致性，不能直接等于某种风格 | 层级、色彩数量、阴影、圆角、留白、组件一致性 |
| 不够醒目 | 对比度或视觉优先级不足 | 色彩、字号、字重、位置、留白 |
| 太抢眼 | 视觉权重超过信息优先级 | 高饱和色、面积、字重、阴影、动画 |
| 边上空白很多 | 父容器 gap、页面 Padding、Grid 轨道或卡片 Margin 过大 | gap、padding、margin、grid-template-columns |
| 行间距太大 | 可能是文字 line-height，也可能是列表/表单 row-gap | 先确认对象，再看 line-height、row-gap、cell padding |
| 表格太松 | 行高或单元格 Padding 过大 | table size、cell padding、line-height |
| 弹窗很臃肿 | 宽度、Padding、区块间距或表单密度过低 | width、padding、section gap、footer |
| 按钮老是乱跑 | 响应式换行、父布局分布或内容宽度不稳定 | flex-wrap、justify-content、min-width |
| 文字被吃掉 | 溢出、截断或容器尺寸问题 | overflow、line-clamp、min-width: 0 |
| 下拉框被挡住 | 层级、Portal 挂载或定位上下文问题 | z-index、portal、overflow hidden |
| 手机端炸了 | 响应式规则或固定尺寸问题 | breakpoints、fixed width、overflow、touch target |

## 重点概念区分

### Gap 与 Margin

- `gap`：父容器统一控制子元素之间的距离；
- `margin`：元素自身与外部对象之间的距离；
- 相同兄弟项需要统一间距时，优先检查 `gap`；
- 单个元素需要特殊偏移时，再考虑 `margin`。

### Padding 与 Gap

- `padding`：内容到组件边界的距离；
- `gap`：同级元素之间的距离；
- 卡片与卡片之间太空，通常先检查父容器 `gap`；
- 卡片内容离边界太远，才是卡片 `padding`。

### Line-height 与 Row-gap

- `line-height`：同一段文字内部的行高；
- `row-gap`：多行布局或多组表单之间的距离；
- 表格行太高还可能来自单元格上下 Padding；
- 用户说“行间距”时必须先识别是哪一种“行”。

### 对齐与视觉居中

数学居中不一定等于视觉居中。图标 `viewBox`、字体上下留白和不同字形都可能造成“看起来偏”。应先保证布局对齐，再检查图标和字体度量。

### 紧凑与拥挤

- 紧凑：提高信息密度，但仍保持分组、可读和可点击；
- 拥挤：元素边界、文字和操作之间缺少必要空间；
- 调整目标不是简单缩小所有数值，而是保留信息层级的前提下减少无效空白。

### 留白与浪费空间

留白可以表达分组、层级和节奏。只有当空白没有承担结构意义、降低操作效率或与项目密度不一致时，才称为无效空白。

### 视觉重量

视觉重量由面积、颜色对比、字重、边框、阴影、圆角、图标和动画共同决定。用户说“太重”时，不要只改阴影。

## 推荐解释格式

```text
你的表达：这两个卡片边上空白太多。
专业判断：卡片之间的水平间距过大，导致横向信息密度偏低。
证据：父容器 column-gap 为 32px；卡片内部 padding 与项目其他卡片一致。
建议：只将 column-gap 调整为 16px，不修改卡片内部 padding。
相关概念：gap 控制组件之间距离，padding 控制组件内容与边界距离。
```

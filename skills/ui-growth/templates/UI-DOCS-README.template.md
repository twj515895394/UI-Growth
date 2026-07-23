# 项目 UI 文档

本目录记录项目已经确认的 UI 规则、候选规范、重要决策、审计结果和页面例外。

## 文档导航

- [`UI-DESIGN-SYSTEM.md`](UI-DESIGN-SYSTEM.md)：颜色、字体、间距、圆角、阴影、控件尺寸和主题；
- [`UI-LAYOUT-RULES.md`](UI-LAYOUT-RULES.md)：页面、查询区、列表、表单、卡片、弹窗和滚动布局；
- [`UI-COMPONENT-RULES.md`](UI-COMPONENT-RULES.md)：常用组件的 Size、Variant、状态和覆盖规则；
- [`UI-INTERACTION-RULES.md`](UI-INTERACTION-RULES.md)：加载、错误、空状态、提交、删除和反馈；
- [`UI-RESPONSIVE-RULES.md`](UI-RESPONSIVE-RULES.md)：支持设备、断点和布局降级；
- [`UI-DECISION-LOG.md`](UI-DECISION-LOG.md)：系统级 UI 决策及重要例外；
- [`UI-AUDIT-REPORT.md`](UI-AUDIT-REPORT.md)：当前实现审计和待确认建议；
- `page-specs/`：特殊或高价值页面规范；
- `baselines/`：视觉回归基线截图。

## 规则状态

- **Confirmed**：已由文档、Token、公共组件或用户决策确认；
- **Candidate**：代码中存在稳定模式，但仍需确认；
- **Exception**：有明确业务原因的局部例外；
- **Conflict**：相同角色存在无理由差异；
- **Deprecated**：旧规则仍存在，但新开发不再使用；
- **Unknown**：证据不足。

## 使用方式

开发或修改页面前：

1. 读取与任务相关的最小文档集合；
2. 优先遵循 Confirmed 规则；
3. 遇到 Candidate 或 Conflict 时，不要自行升级为全局标准；
4. 页面确需例外时，说明原因和范围；
5. 修改公共组件或全局 Token 时，更新决策日志。

## 更新原则

- 不把单页硬编码值直接写成全局规范；
- 不复制所有 CSS 和组件配置；
- 只记录会改变实现选择的规则；
- 事实、建议和已确认决策必须分开；
- 普通局部修复无需强制更新全部文档；
- 重要规则变更必须记录迁移策略。

## 当前适用范围

- 产品/前端包：
- 技术栈：
- 组件库：
- 维护者：
- 最后审计：

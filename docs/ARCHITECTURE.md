# UI Growth Architecture

## 1. 产品定位

UI Growth 是单一主 Skill 加按需参考资料和可复制模板的结构。当前不引入运行时服务、CLI 或框架绑定。

## 2. 核心流程

```text
用户截图/口语描述/代码上下文
        ↓
对象和真实意图识别
        ↓
视觉问题分类与专业术语转换
        ↓
项目代码、Token、组件和规范证据读取
        ↓
修改范围 S1–S5 与风险判断
        ↓
低风险直接处理 / 中高风险专业确认
        ↓
生成 UI 修改执行合同
        ↓
代码 Agent 最小范围实现
        ↓
同视口截图、状态、响应式和回归验收
        ↓
更新规范、页面说明或设计决策
        ↓
向用户解释 1–2 个本次相关 UI 概念
```

## 3. 模块

### 3.1 Intent Interpreter

职责：

- 解析“这里、边上、太堵、太空、不齐”等口语；
- 识别截图标注对象；
- 保留用户原始意图；
- 区分症状与实现原因。

对应文件：

- `references/ui-terminology-map.md`
- `references/ui-issue-taxonomy.md`

### 3.2 UI Advisor

职责：

- 识别真实设计分歧；
- 给出推荐方案和备选；
- 说明影响范围；
- 控制询问数量。

对应文件：

- `references/clarification-protocol.md`

### 3.3 Project Evidence Reader

职责：

- 识别技术栈和组件体系；
- 读取 Token、主题、公共组件和代表页面；
- 建立证据与置信度；
- 避免从局部硬编码推导全局规则。

对应文件：

- `references/project-audit.md`

### 3.4 Execution Contract Builder

职责：

- 生成目标、范围、约束和验收条件；
- 让另一个代码 Agent 可以直接执行；
- 防止无关重构和范围扩张。

对应文件：

- `references/execution-contract.md`
- `templates/UI-CHANGE-TASK.template.md`

### 3.5 Visual Validator

职责：

- 同视口前后对比；
- 响应式检查；
- 交互状态检查；
- 公共组件抽样回归；
- 标记无法运行验证的部分。

对应文件：

- `references/visual-validation.md`
- `templates/UI-VALIDATION-REPORT.template.md`

### 3.6 Design Governance

职责：

- 生成项目 UI 文档；
- 区分 Confirmed、Candidate、Exception、Conflict；
- 维护设计决策；
- 控制局部规则升级为全局规范。

对应文件：

- `references/design-governance.md`
- `templates/UI-*.template.md`
- `templates/PAGE-SPEC.template.md`

### 3.7 Learning Feedback

职责：

- 将本次用户表达映射到专业术语；
- 解释一个关键区别；
- 让用户在真实开发中逐渐形成 UI 判断能力。

该模块嵌入主 Skill 的最终报告，不单独增加大段课程。

## 4. 上下文加载策略

主 Skill 始终加载，但 references 按任务最小化加载：

| 任务 | 参考文件 |
|---|---|
| 截图和口语诊断 | taxonomy + terminology |
| 需要用户确认 | clarification |
| 生成规范 | project-audit + design-governance |
| 委托其他 Agent | execution-contract + task template |
| 修改后验收 | visual-validation + report template |

## 5. 文档输出模型

UI Growth 面向目标项目生成：

```text
docs/ui/
├── README.md
├── UI-DESIGN-SYSTEM.md
├── UI-LAYOUT-RULES.md
├── UI-COMPONENT-RULES.md
├── UI-INTERACTION-RULES.md
├── UI-RESPONSIVE-RULES.md
├── UI-DECISION-LOG.md
├── UI-AUDIT-REPORT.md
├── baselines/
└── page-specs/
```

目标项目已有规范目录时，适配现有结构，不创建平行体系。

## 6. 未来可插拔能力

以下能力可在未来作为可选适配器加入，但不应污染核心 Skill：

- Vue/Element Plus 适配参考；
- React/Ant Design 适配参考；
- 小程序/Vant Weapp 适配参考；
- Playwright 截图验收脚本；
- CSS Token 扫描脚本；
- 截图标注编号解析约定；
- 视觉差异报告生成。

核心流程必须保持技术栈无关。

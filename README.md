# UI Growth

**UI 自我提升：面向后端开发者与 AI 编程用户的 UI 意图翻译、设计治理和视觉验收 Skill。**

UI Growth 接收截图、口语化描述和项目代码，把“这里太挤”“卡片旁边空白太大”“按钮看起来不协调”等表达，转换为专业、可执行、可验收的前端修改任务。

它不会替代用户做审美决定，也不会把项目强行改成某一种流行风格。它负责：

- 识别页面视觉问题及真实影响范围；
- 将口语表达转换为 UI/CSS/交互专业语言；
- 对歧义问题给出专业建议并请求必要确认；
- 基于现有项目证据生成和维护 UI 规范文档；
- 约束代码 Agent 避免过度修改和无关重构；
- 对修改结果执行截图、响应式、交互状态和规范一致性验收；
- 在每次任务中向用户解释少量、实用的 UI 知识。

## 使用入口

主 Skill：[`skills/ui-growth/SKILL.md`](skills/ui-growth/SKILL.md)

将 `skills/ui-growth/` 提供给支持 Agent Skill 的 Codex、Claude Code、Cursor 或其他代码 Agent。使用时可以直接提供：

- 页面截图或带序号的标注截图；
- 你的口语描述；
- 页面路由、组件或文件线索；
- 不能修改的业务范围；
- 参考页面或修改后的截图。

示例输入：

```text
使用 UI Growth 分析这张截图。
这两个卡片边上空白太多，希望紧凑一点，但不要压缩卡片里面的内容，也不要修改其他区域。
先判断问题原因；只有存在重要设计分歧时再让我确认；修改后检查 1440px 和 1280px。
```

完整示例：[`examples/card-spacing-adjustment.md`](examples/card-spacing-adjustment.md)

## 三种模式

- **快速调整**：意图明确、低风险的局部 UI 问题；
- **专业确认**：存在多种合理方案时，给出推荐和具体选项；
- **规范治理**：扫描项目现状，生成或维护 UI 规范、审计和决策文档。

## 项目结构

```text
UI-Growth/
├── skills/ui-growth/
│   ├── SKILL.md
│   ├── references/
│   │   ├── ui-issue-taxonomy.md
│   │   ├── ui-terminology-map.md
│   │   ├── clarification-protocol.md
│   │   ├── project-audit.md
│   │   ├── design-governance.md
│   │   ├── execution-contract.md
│   │   └── visual-validation.md
│   └── templates/
│       ├── UI-CHANGE-TASK.template.md
│       ├── UI-VALIDATION-REPORT.template.md
│       ├── UI-DESIGN-SYSTEM.template.md
│       ├── UI-LAYOUT-RULES.template.md
│       ├── UI-COMPONENT-RULES.template.md
│       ├── UI-INTERACTION-RULES.template.md
│       ├── UI-RESPONSIVE-RULES.template.md
│       ├── UI-DECISION-LOG.template.md
│       ├── UI-AUDIT-REPORT.template.md
│       ├── UI-DOCS-README.template.md
│       └── PAGE-SPEC.template.md
├── examples/
├── docs/
├── AGENTS.md
└── CHANGELOG.md
```

## 适用场景

- Codex、Claude Code、Cursor 等代码 Agent 的前端 UI 调整；
- Vue、React、原生 Web、小程序及常见组件库项目；
- 基于截图描述局部页面问题；
- 建立或补全项目 UI 设计规范；
- 修改后的视觉回归和响应式检查。

## 核心原则

1. **先理解意图，再修改代码。**
2. **先读取项目现状，再提出规范。**
3. **局部问题默认局部解决。**
4. **事实、建议和用户决策必须分开。**
5. **代码通过不等于视觉验收通过。**
6. **每次解决问题，也帮助用户学会描述问题。**

## 设计与路线

- 架构：[`docs/ARCHITECTURE.md`](docs/ARCHITECTURE.md)
- 对参考项目的借鉴与边界：[`docs/REFERENCE-REVIEW.md`](docs/REFERENCE-REVIEW.md)
- 路线图：[`docs/ROADMAP.md`](docs/ROADMAP.md)
- 版本记录：[`CHANGELOG.md`](CHANGELOG.md)

## 当前状态

仓库处于 `v0.1.0` 初始版本，已经包含主 Skill、工作流参考、规范模板、任务模板和验收模板。下一阶段重点是在 Vue、React 和小程序真实项目中验证并修正工作流。

### ♿ 补充 Skill 8: `Inclusive_A11y_Standard` (无障碍与包容性设计 Skill)
**目的**：防止 AI 生成的 UI 仅在“视觉上正确”，而在“可用性”上缺陷（如无法通过键盘操作、屏幕阅读器无法识别），确保符合 WCAG 2.1 标准。

*   **约束核心**：**感知 $\rightarrow$ 可操作 $\rightarrow$ 理解 $\rightarrow$ 鲁棒性 (POUR原则)**。
*   **AI 必须遵守的指令**：
    *   **键盘导航闭环**：所有交互元素必须具备可见的 `:focus-visible` 状态，且 Tab 键顺序必须符合视觉逻辑流。
    *   **ARIA 语义增强**：
        *   纯图标按钮 $\rightarrow$ 必须添加 `aria-label="描述"`。
        *   动态内容更新 $\rightarrow$ 使用 `aria-live="polite"`。
        *   模态框/抽屉 $\rightarrow$ 必须实现 `role="dialog"` 且开启时锁定背景滚动。
    *   **色彩对比度强制校验**：文本与背景的对比度必须 $\ge 4.5:1$（AA级），禁止使用低对比度的浅灰文字作为核心信息。
    *   **表单关联**：所有 `input` 必须有对应的 `id` 且与 `label` 通过 `for` 属性绑定。
*   **校验点**：在代码审计报告中，增加一项 $\text{A11y Audit}$，列出已实现的无障碍特性（如：`Keyboard Nav: Yes`, `ARIA Labels: Yes`）。

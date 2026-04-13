#### 2. `Atomic_Component_Logic` (原子化组件构建 Skill)
**目的**：防止 AI 在一个页面里写 5 个样式几乎一样的按钮，强制它进行组件化思考。
*   **约束核心**：**原子设计理论 (Atomic Design)** $\rightarrow$ 原子 $\rightarrow$ 分子 $\rightarrow$ 组织。
*   **AI 必须遵守的指令**：
    *   **禁止重复样式**：如果一个样式出现两次，必须将其提取为独立组件或 CSS 类。
    *   **Props 驱动**：所有组件必须通过 Props 控制状态。例如按钮必须有 `variant="primary|secondary|ghost"` 和 `size="sm|md|lg"`。
    *   **单一职责**：一个组件只做一件事。
    *   **校验点**：在写页面代码前，AI 必须先列出本项目需要的【原子组件清单】。

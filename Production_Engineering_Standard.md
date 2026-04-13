#### 5. `Production_Engineering_Standard` (生产级代码规范 Skill)
**目的**：消除 AI 生成代码中常见的“业余感”（如：滥用 `any`、混乱的 CSS 类名、臃肿的组件逻辑），确保交付的代码符合工业级标准，具备极高的可维护性和生产环境的稳定性。

*   **约束核心**：**类型安全 (Type Safety) + 结构化样式 (Structured Styling) + 逻辑解耦 (Logic Decoupling)**。
*   **AI 必须遵守的指令**：
    *   **TypeScript 零 `any` 容忍 (Zero-Any Policy)**：
        *   严禁在任何地方使用 `any` 类型。
        *   所有 API 响应、组件 Props、状态变量必须定义明确的 `interface` 或 `type`。
        *   对于不确定的动态键值，必须使用 `Record<string, unknown>` 或泛型 $\langle T \rangle$。
    *   **BEM 命名规范 (Block Element Modifier)**：
        *   禁止使用随机的类名（如 `.box1`, `.title-style`）。
        *   必须严格遵循 BEM 规范：`block__element--modifier`。
        *   *示例*：`.card` (Block) $\rightarrow$ `.card__title` (Element) $\rightarrow$ `.card__title--highlighted` (Modifier)。
    *   **逻辑解耦与 Composables/Hooks 模式**：
        *   **禁止“巨型组件”**：组件内部禁止编写超过 20 行的复杂业务逻辑。
        *   **强制抽离**：Vue3 必须提取至 `composables/`，React 必须提取至 `hooks/`。
        *   **职责定义**：组件内只保留：`状态定义` $\rightarrow$ `调用 Hook` $\rightarrow$ `视图渲染`。
    *   **性能工程化 (Performance Engineering)**：
        *   **资源优化**：所有图片引用必须建议使用 `.webp` 格式，并包含 `loading="lazy"` 属性。
        *   **加载策略**：路由必须采用 `Dynamic Import` (懒加载) 模式。
        *   **渲染优化**：在循环渲染大量数据时，必须强制使用 `key` (且禁止使用 index)，并建议使用虚拟列表 (Virtual List)。
        *   **减少重排**：优先使用 `transform` 和 `opacity` 实现动画，严禁通过频繁修改 `top/left/width/height` 触发重排 (Reflow)。
*   **校验点**：
    *   **代码审计报告 (Code Audit Report)**：在输出代码块之后，AI 必须附带一份【代码审计清单】，包含以下内容：
        1.  **类型审计**：确认所有接口定义无 `any`。
        2.  **命名审计**：确认 CSS 类名完全符合 BEM 规范。
        3.  **解耦审计**：标注哪些逻辑被抽离到了 Composables/Hooks 中。
        4.  **优化点标注**：明确指出代码中为了性能而采取的措施（如：`useMemo`, `lazy-load` 等）。

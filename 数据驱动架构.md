#### 3. `Data_Driven_Architecture` (数据驱动架构 Skill)
**目的**：防止 AI 编写“静态死代码”，强制其将**数据逻辑**与**视图渲染**分离，确保代码可直接对接真实接口。

*   **约束核心**：**数据驱动视图 (Data-Driven UI)** $\rightarrow$ `Data Object` $\rightarrow$ `Mapping` $\rightarrow$ `UI Component`。
*   **AI 必须遵守的指令**：
    *   **禁止硬编码重复项**：禁止在 JSX/HTML 中手动复制重复的元素。只要出现 2 个以上相似的项，必须定义一个 `const DATA = [...]` 数组，并使用 `.map()` 进行遍历渲染。
    *   **接口定义优先 (Interface First)**：在编写组件逻辑前，必须先定义数据的类型接口（TypeScript Interface 或 JS 伪代码），明确每个字段的名称和类型。
    *   **强制处理“三态”逻辑**：任何涉及数据请求的组件，必须同时实现以下三种状态的 UI 处理，禁止只写“成功”状态：
        1.  `Loading State`：加载中的骨架屏或 Spinner。
        2.  `Empty State`：无数据时的缺省页/提示。
        3.  `Error State`：请求失败时的错误提示及重试机制。
    *   **逻辑抽离**：禁止在 JSX 模板内部编写复杂的计算逻辑，必须在 `return` 之前完成数据的清洗和转换。
*   **校验点**：
    *   自检：代码中是否出现了重复的 HTML 结构？（如果有 $\rightarrow$ 必须转换为 `.map()`）。
    *   自检：是否定义了清晰的数据模型（Interface/Type）？
    *   自检：是否覆盖了 `Loading` 和 `Empty` 两种边界状态？

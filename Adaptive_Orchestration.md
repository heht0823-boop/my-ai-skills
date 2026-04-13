#### 4. `Adaptive_Orchestration` (极致响应式编排 Skill)
**目的**：防止 AI 采用简单的 `@media (max-width: 768px)` 这种粗暴的“缩放”式适配，强制其实现能够平滑过渡、在不同设备上具有原生感且布局合理的流式界面。

*   **约束核心**：**流式设计 (Fluid Design) + 结构性重编排 (Structural Re-orchestration)**。
*   **AI 必须遵守的指令**：
    *   **禁止固定宽度 (No Hard-coded Widths)**：
        *   严禁在任何容器上使用 `width: 1200px` 或 `width: 400px` 等固定像素值。
        *   必须采用 `max-width` 限制最大宽度 $\rightarrow$ `width: 90%` 或 `width: calc(100% - 32px)` 保证边距 $\rightarrow$ `margin: 0 auto` 居中。
    *   **实现流式字体 (Fluid Typography)**：
        *   禁止在不同断点重复写多次 `font-size`。
        *   必须使用 CSS `clamp()` 函数实现字体在最小、理想、最大值之间平滑缩放。
        *   *标准公式*：`font-size: clamp([最小值], [随视口变化的动态值], [最大值]);` (例如：`font-size: clamp(1rem, 5vw, 2.5rem);`)。
    *   **执行布局重编排 (Layout Re-orchestration)**：
        *   **禁止单纯缩小**：在移动端，禁止仅仅通过减小字体和间距来强行塞入内容。
        *   **必须执行模式转换**：
            *   **表格 $\rightarrow$ 卡片**：复杂 Data Table 在移动端必须转换为 `Stacked Card` (堆叠卡片) 模式。
            *   **侧边栏 $\rightarrow$ 底部导航/抽屉**：PC 端的 `Sidebar` 在移动端必须转换为 `Bottom Navigation` 或 `Hamburger Menu Drawer`。
            *   **多列网格 $\rightarrow$ 单列流**：使用 `grid-template-columns: repeat(auto-fit, minmax(280px, 1fr))` 实现自动填充，而非手动写死断点。
*   **校验点**：
    *   **响应式适配清单 (Adaptive Checklist)**：在输出代码前，AI 必须先提供一个适配清单，格式如下：
        *   `[Desktop]`: $\rightarrow$ 布局描述 (如：3列网格 + 侧边栏)
        *   `[Tablet]`: $\rightarrow$ 布局描述 (如：2列网格 + 顶部导航)
        *   `[Mobile]`: $\rightarrow$ 布局描述 (如：单列卡片流 + 底部菜单)
    *   **视觉自检**：检查代码中是否依然存在 `width: XXXpx` 的硬编码。
    *   **函数自检**：检查关键标题是否使用了 `clamp()` 实现平滑缩放。

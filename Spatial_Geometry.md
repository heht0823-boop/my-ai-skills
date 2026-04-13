## 🛠️ Skill 1: `Spatial_Geometry` (空间几何与间距约束)
**目的**：解决 AI 随意写 `padding: 20px` 或 `margin: 15px` 导致页面视觉不协调的问题。

*   **约束核心**：**强制执行 8pt Grid System (8px 步进法则)**。
*   **AI 必须遵守的指令**：
    *   所有间距（Padding/Margin/Gap）必须是 8 的倍数（8, 16, 24, 32, 48, 64...）。
    *   极小间距（如图标与文字之间）允许使用 4px。
    *   **必须定义并使用空间变量**：
        ```css
        :root {
          --space-xs: 4px;
          --space-sm: 8px;
          --space-md: 16px;
          --space-lg: 24px;
          --space-xl: 32px;
          --space-xxl: 48px;
          --space-huge: 64px;
        }
        ```
*   **校验点**：在输出代码前，AI 必须自检所有 `px` 值是否符合 8px 步进，禁止出现 `13px`, `15px`, `20px` 等非标准值。

---

## ✍️ Skill 2: `Typographic_Hierarchy` (字体层级与排版)
**目的**：避免页面出现过多杂乱的字体大小，建立清晰的信息架构。

*   **约束核心**：**模块化字体比例 (Modular Scale)**。
*   **AI 必须遵守的指令**：
    *   禁止随意定义 `font-size`，必须使用预设的层级变量。
    *   **必须定义字体变量**：
        ```css
        :root {
          --text-xs: 12px;    /* 辅助文本 */
          --text-sm: 14px;    /* 正文/次要 */
          --text-base: 16px;  /* 标准正文 */
          --text-lg: 18px;    /* 小标题 */
          --text-xl: 20px;    /* 标题 */
          --text-2xl: 24px;   /* 核心标题 */
          --text-3xl: 30px;   /* 页面大标题 */
        }
        ```
    *   **行高约束**：正文行高统一为 `1.5` 或 `1.6`；标题行高统一为 `1.2`。
*   **校验点**：检查是否所有文本都映射到了变量，且没有出现 `font-size: 17px` 这种中间值。

---

## 🌈 Skill 3: `Chromatic_System` (色彩系统与对比度)
**目的**：防止 AI 使用高饱和度的“刺眼”颜色（如纯红 #FF0000）或不统一的灰色调。

*   **约束核心**：**语义化色彩映射 (Semantic Color Mapping)**。
*   **AI 必须遵守的指令**：
    *   禁止在组件中直接写 `#hex` 或 `rgb()`，必须使用语义化变量。
    *   **必须定义色彩变量集**：
        *   **品牌色**：`--color-primary`, `--color-primary-hover`, `--color-primary-light`
        *   **中性色 (灰阶)**：`--color-gray-100` (最浅) $\rightarrow$ `--color-gray-900` (最深)
        *   **状态色**：`--color-success`, `--color-warning`, `--color-error`, `--color-info`
        *   **界面色**：`--color-bg-main`, `--color-bg-surface`, `--color-border`
    *   **对比度要求**：文本与背景的对比度必须符合 WCAG AA 级标准。
*   **校验点**：检索代码中是否存在硬编码的颜色值，强制替换为变量。

---

## ⚡ Skill 4: `Interactive_Motion` (交互动效与反馈)
**目的**：消除 AI 编写的“瞬间跳变”效果，增加平滑的专业交互感。

*   **约束核心**：**标准化过渡时间与曲线 (Timing & Easing)**。
*   **AI 必须遵守的指令**：
    *   所有状态切换（Hover, Focus, Active）必须包含 `transition`。
    *   **必须定义动效变量**：
        ```css
        :root {
          --transition-fast: 150ms cubic-bezier(0.4, 0, 0.2, 1);
          --transition-normal: 300ms cubic-bezier(0.4, 0, 0.2, 1);
          --transition-slow: 500ms cubic-bezier(0.4, 0, 0.2, 1);
        }
        ```
    *   **交互反馈**：所有可点击元素必须有 `:hover` (亮度/色相微调) 和 `:active` (轻微缩放 `scale(0.98)`) 效果。
*   **校验点**：检查所有的交互元素是否配置了 `transition`，是否存在生硬的视觉跳变。

---

## 📱 Skill 5: `Adaptive_Layout` (响应式适配)
**目的**：防止 AI 只写桌面端代码，或使用不统一的断点导致页面在特定设备上崩坏。

*   **约束核心**：**移动优先 (Mobile First) 与 标准断点**。
*   **AI 必须遵守的指令**：
    *   优先编写移动端样式，使用 `@media (min-width: ...)` 向上扩展。
    *   **强制执行标准断点**：
        *   `sm`: 640px (手机横屏)
        *   `md`: 768px (平板)
        *   `lg`: 1024px (笔记本)
        *   `xl`: 1280px (桌面显示器)
    *   **布局禁令**：禁止在响应式布局中使用固定宽度 `width: 1200px`，必须使用 `max-width` 和百分比/`rem`/`vw`。
*   **校验点**：确认是否存在 `@media` 查询，且断点值是否统一。

---

## 🏗️ Skill 6: `Semantic_Architecture` (语义化架构)
**目的**：解决 AI 滥用 `<div>` 导致代码难以维护且不利于 SEO 和无障碍（Accessibility）的问题。

*   **约束核心**：**HTML5 语义化标签强制化**。
*   **AI 必须遵守的指令**：
    *   **禁令**：禁止在可以用语义标签的地方使用 `div`。
    *   **替换映射表**：
        *   页面头部 $\rightarrow$ `<header>`
        *   主内容区 $\rightarrow$ `<main>`
        *   侧边栏 $\rightarrow$ `<aside>`
        *   导航栏 $\rightarrow$ `<nav>`
        *   独立区块 $\rightarrow$ `<section>` 或 `<article>`
        *   页脚 $\rightarrow$ `<footer>`
    *   **无障碍要求**：所有 `img` 必须有 `alt` 属性；所有交互按钮必须有明确的 `aria-label`（如果无文字）。
*   **校验点**：扫描代码，统计 `div` 数量，检查是否有可被替换为语义标签的容器。

---

### 🚀 AI 执行工作流 (Execution Pipeline)
当接收到前端开发需求时，AI 必须按照以下顺序执行：
1.  **Define Variables** $\rightarrow$ 根据 `Skill 1-4` 定义 CSS 变量集。
2.  **Build Structure** $\rightarrow$ 根据 `Skill 6` 构建语义化 HTML。
3.  **Apply Geometry** $\rightarrow$ 根据 `Skill 1` 应用 8px 间距。
4.  **Refine Visuals** $\rightarrow$ 根据 `Skill 2-3` 配置字体与色彩。
5.  **Add Interaction** $\rightarrow$ 根据 `Skill 4` 添加过渡动效。
6.  **Adapt Layout** $\rightarrow$ 根据 `Skill 5` 完成响应式适配。
7.  **Self-Check** $\rightarrow$ 逐项核对上述 6 个 Skill 的校验点。

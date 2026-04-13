# 🌐 全平台全场景 UI 工程调度系统 (CP-UIOS v2.0)

**系统核心逻辑**：
AI 在接收任务时，必须首先锁定 **`Platform_ID`（决定骨架/交互/密度）**，随后锁定 **`Theme_ID`（决定色彩/材质/动效）**。严禁在未指定平台的情况下直接应用风格。

---

## 🛠️ 第一维度：平台基准 (Platform Base)
*平台基准决定了：布局逻辑、导航架构、信息密度和交互习惯。*

### 🖥️ Platform_ID: `Web_Landing` (品牌展示型网页)
*   **核心目标**：视觉引导 $\rightarrow$ 品牌传递 $\rightarrow$ 转化。
*   **布局逻辑**：**纵向流式布局 (Vertical Storytelling)**。采用大面积 Section 分割，强调首屏视觉冲击力。
*   **交互特性**：依赖 `Hover` 状态，支持视差滚动 (Parallax)，强调全屏过渡动画。
*   **信息密度**：**低 (Low)**。大量留白，单屏聚焦一个核心视觉点。
*   **导航架构**：顶部透明/毛玻璃导航栏 $\rightarrow$ 底部冗长页脚 (Fat Footer)。

### ⚙️ Platform_ID: `Software_SaaS` (生产力软件/管理后台)
*   **核心目标**：高效操作 $\rightarrow$ 快速导航 $\rightarrow$ 数据处理。
*   **布局逻辑**：**工作区架构 (Workspace Layout)**。典型的 `左侧导航 + 顶部状态栏 + 中间主内容区 + 右侧属性面板`。
*   **交互特性**：密集点击，支持快捷键，复杂的表格/表单交互，强调状态实时反馈。
*   **信息密度**：**高 (High)**。紧凑的组件排布，最小化冗余留白，追求单屏信息承载量。
*   **导航架构**：多级侧边栏 (Side Nav) + 面包屑 (Breadcrumbs) + 快速搜索。

### 📱 Platform_ID: `Mobile_App` (小程序/移动端 App)
*   **核心目标**：单手触达 $\rightarrow$ 碎片化操作 $\rightarrow$ 任务闭环。
*   **布局逻辑**：**堆叠卡片流 (Stacked Card Flow)**。垂直单列，重要操作区集中在屏幕底部（拇指区）。
*   **交互特性**：彻底放弃 `Hover` $\rightarrow$ 采用 `Tap` (点击), `Swipe` (滑动), `Long Press` (长按)。
*   **信息密度**：**中 (Medium)**。通过卡片化将信息分块，利用抽屉 (Drawer) 和模态框 (Modal) 承载次要信息。
*   **导航架构**：底部标签栏 (Bottom Tab Bar) + 顶部标题栏 + 右上角功能按钮。

### 🎮 Platform_ID: `Game_UI` (游戏界面/沉浸式应用)
*   **核心目标**：世界观融合 $\rightarrow$ 状态监控 $\rightarrow$ 极低认知成本。
*   **布局逻辑**：**HUD 布局 (Heads-Up Display)**。核心信息分布在屏幕四周（四角分布），中心区域留空给核心场景。
*   **交互特性**：强视觉反馈（点击时有震动感/光效），非标准形状按钮，依赖全屏覆盖菜单。
*   **信息密度**：**动态切换 (Dynamic)**。平时极低（仅显示关键状态），触发事件时瞬时变为极高。
*   **导航架构**：全屏覆盖式菜单 (Full-screen Overlay) + 功能快捷环。

---

## 🎨 第二维度：风格预设 (Style Preset)
*风格预设是“皮肤”，可以套在任何平台上。*

| Theme_ID | 视觉核心 | 色彩方向 | 材质感 | 动效逻辑 |
| :--- | :--- | :--- | :--- | :--- |
| `SaaS_Precision` | 极致精密 | 纯黑/深灰 $\rightarrow$ 荧光点缀 | 暗色玻璃/极细线 | 快速、干脆、无惯性 |
| `Apple_Bento` | 果味便当 | 纯白/浅灰 $\rightarrow$ 马卡龙色 | 大圆角/柔和投影 | 弹性、自然、回弹感 |
| `Neo_Brutalist` | 新野兽主义 | 高对比原色 $\rightarrow$ 纯黑边框 | 平面化/硬阴影 | 跳跃、无过渡、直接 |
| `Organic_Fluid` | 有机流动 | 暖白/米色 $\rightarrow$ 同色系渐变 | 磨砂/纸质/噪点 | 丝滑、缓慢、漂浮感 |
| `Industrial_Cyber` | 工业赛博 | 钢灰/军绿 $\rightarrow$ 琥珀色荧光 | 金属拉丝/扫描线 | 打字机/闪烁/展开 |
| `Digital_Editorial`| 数字社论 | 极简黑白 $\rightarrow$ 单色高亮 | 纯净平面/大字号 | 视差滚动/渐显 |

---

## 🔄 第三部分：调度矩阵 (The Orchestration Matrix)

**当你组合两者时，AI 必须执行以下逻辑映射：**

*   **`Software_SaaS` $\times$ `SaaS_Precision`** $\rightarrow$ 结果：像 **Linear/Vercel** 一样专业的开发者工具。
*   **`Mobile_App` $\times$ `Apple_Bento`** $\rightarrow$ 结果：像 **iOS 原生/Airbnb** 一样精致的现代化 App。
*   **`Web_Landing` $\times$ `Digital_Editorial`** $\rightarrow$ 结果：像 **Vogue/高端建筑事务所** 一样的艺术视觉页。
*   **`Game_UI` $\times$ `Industrial_Cyber`** $\rightarrow$ 结果：像 **赛博朋克 2077/星际公民** 的系统操作界面。

---

## 🚀 第四部分：AI 严格执行指令集 (Implementation Protocol)

**当你（AI）接收到任务时，必须按照以下步骤执行，严禁跳步：**

1.  **Step 1: 锁定骨架 (Platform Analysis)**
    *   检查 `Platform_ID`。如果是 `Software_SaaS`，立即规划侧边栏和信息密度；如果是 `Mobile_App`，立即规划拇指区和卡片流。
2.  **Step 2: 注入皮肤 (Theme Injection)**
    *   检查 `Theme_ID`。生成对应的 `:root` 变量表（颜色、圆角、阴影、字体）。
3.  **Step 3: 冲突解决 (Adaptation)**
    *   如果 `Theme_ID` 是 `Neo_Brutalist`（硬边框）而 `Platform_ID` 是 `Mobile_App`（习惯圆角），AI 需优先保证 `Theme_ID` 的视觉特征，但优化 `Platform_ID` 的触控面积。
4.  **Step 4: 产出代码 (Production)**
    *   输出基于变量的 CSS/SCSS 代码 $\rightarrow$ 适配响应式布局 $\rightarrow$ 实现对应平台的动效。

---

## 📖 使用示例 (Trigger Example)

**用户输入：**
> 「启动新项目：【AI 虚拟助手管理后台】
> **Platform_ID**: `Software_SaaS`
> **Theme_ID**: `Industrial_Cyber`
>
> **要求**：开发主仪表盘界面，包含左侧导航和右侧数据监控面板。确保符合工业赛博风格的金属感和扫描线效果，且信息密度符合 SaaS 软件的高效要求。」

**AI 响应预期：**
1.  **骨架**：构建左侧窄导航 $\rightarrow$ 中间大看板 $\rightarrow$ 右侧详情页（SaaS 结构）。
2.  **皮肤**：定义深钢灰背景、琥珀色荧光文字、1px L型装饰边框（Cyber 皮肤）。
3.  **细节**：给背景添加 `linear-gradient` 扫描线，所有按钮采用等宽字体且无圆角。
4.  **结果**：产出一个像“军事级 AI 控制台”一样的专业软件界面。

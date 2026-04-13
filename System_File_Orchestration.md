### 🛠️ 补充 Skill 7: `System_File_Orchestration` (项目文件编排 Skill)
**目的**：防止 AI 将所有代码堆在一个文件里，或采用随意的文件夹命名，确保项目结构符合行业标准，方便多人协作和长期维护。

*   **约束核心**：**分层架构 (Layered Architecture) $\rightarrow$ 职责分离 $\rightarrow$ 路径可预测**。
*   **AI 必须遵守的指令**：
    *   **强制执行标准目录结构**：
        ```text
        src/
        ├── assets/          # 静态资源 (images, fonts, global-styles)
        ├── components/      # 原子化组件
        │   ├── common/      # 通用原子组件 (Button, Input)
        │   └── business/    # 业务分子组件 (UserCard, OrderTable)
        ├── composables/     # 逻辑抽离 (Vue hooks / React hooks)
        ├── stores/          # 全局状态管理 (Pinia/Redux)
        ├── views/           # 页面级组件 (Page-level components)
        ├── types/           # 全局 TypeScript 类型定义
        └── utils/           # 纯工具函数 (formatters, validators)
        ```
    *   **命名一致性**：
        *   组件文件：`PascalCase` (如 `BaseButton.vue`)。
        *   逻辑文件：`camelCase` (如 `useAuth.ts`)。
        *   样式文件：`kebab-case` (如 `main-layout.scss`)。
    *   **导出规范**：强制使用 `index.ts` 导出模式，减少组件引入时的路径冗余（如 `import { Button } from '@/components/common'`）。
*   **校验点**：在输出代码前，AI 必须提供一个 $\text{File Tree}$ 预览，标注每个代码块将存放于哪个具体路径。

#### 6. `Global_State_Management` (全局状态流转 Skill - Setup Store 版)
**目的**：消除冗余的 Option Store 样板代码，通过 Pinia Setup Store 实现极致的响应式数据流。强制执行【Store-First】原则，确保所有接口请求与业务逻辑在 Store 层闭环，组件仅负责视图触发与数据消费。

*   **约束核心**：**Setup Store 模式 $\rightarrow$ 单一真理来源 (Single Source of Truth)**。
*   **AI 必须遵守的指令**：
    *   **强制使用 Setup Store 语法**：
        *   **禁令**：严禁使用 `state: () => ({})`, `getters: {}`, `actions: {}` 这种 Option 结构。
        *   **标准定义**：必须使用 `defineStore('id', () => { ... })` 这种函数式定义。
        *   **映射关系**：
            *   $\text{State} \rightarrow$ 使用 `ref()` 或 `reactive()`。
            *   $\text{Getters} \rightarrow$ 使用 `computed()`。
            *   $\text{Actions} \rightarrow$ 使用简单的 `async function`。
    *   **Store-First 闭环链路**：
        *   **组件禁令**：严禁在 `.vue` 组件中直接调用 API (axios/fetch)。
        *   **唯一流向**：`组件` $\rightarrow$ `调用 Store Function` $\rightarrow$ `API 请求` $\rightarrow$ `直接修改 Store ref` $\rightarrow$ `组件自动响应`。
    *   **响应式消费规范**：
        *   在组件中使用 Store 时，必须使用 `storeToRefs()` 来解构 state 和 computed，以确保响应式不丢失。
        *   *示例*：`const { userInfo, isLoaded } = storeToRefs(userStore);`
    *   **逻辑极简原则**：
        *   **无需中间层**：直接在 Store 函数内定义逻辑，无需经过复杂的 Dispatch/Commit。
        *   **即时更新**：API 返回结果后，直接对 `ref` 赋值，确保全平台所有引用该数据的组件立即同步。
*   **校验点**：
    *   **结构审计**：检查 Store 是否依然包含 `state/getters/actions` 关键字？（如果有 $\rightarrow$ 立即重构为 Setup Store 函数式）。
    *   **调用审计**：检查 `.vue` 文件中是否出现了 API 请求代码？（如果有 $\rightarrow$ 强制迁移至 Store Function）。
    *   **响应式审计**：检查组件解构 Store 时是否漏掉了 `storeToRefs`？（如果有 $\rightarrow$ 修正以防止数据不更新）。

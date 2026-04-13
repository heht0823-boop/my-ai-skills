### 🧪 补充 Skill 9: `QA_Verification_Protocol` (交付验证协议 Skill)
**目的**：消除 AI 的“自我感觉良好”，强制其在交付前模拟用户真实操作路径，通过“自测清单”确保代码在边缘情况下不会崩溃。

*   **约束核心**：**黑盒测试模拟 (Black-box Simulation) $\rightarrow$ 边界压力测试**。
*   **AI 必须遵守的指令**：
    *   **执行“极端数据”模拟**：AI 必须自问：
        1.  *“如果标题文字长到 100 个字符，布局是否会撑破？”* $\rightarrow$ $\text{Solution: clamp/ellipsis}$。
        2.  *“如果 API 返回 null 且没有错误信息，界面是否会白屏？”* $\rightarrow$ $\text{Solution: Optional Chaining / Fallback UI}$。
        3.  *“如果用户在 Loading 状态下快速点击 10 次按钮，是否会触发 10 次请求？”* $\rightarrow$ $\text{Solution: Debounce / Loading Lock}$。
    *   **交互链路走查**：AI 必须输出一个 $\text{Interaction Trace}$ (交互链路图)，例如：`点击登录` $\rightarrow$ `按钮进入 Loading` $\rightarrow$ `Store 状态变更` $\rightarrow$ `页面跳转` $\rightarrow$ `加载骨架屏`。
*   **校验点**：在交付代码的最末端，附带一个 $\text{QA Test Report}$：
    *   `[Boundary Test]`: $\checkmark$ 文本溢出处理
    *   `[State Test]`: $\checkmark$ 加载/空/错误态覆盖
    *   `[Stability Test]`: $\checkmark$ 防抖/节流处理

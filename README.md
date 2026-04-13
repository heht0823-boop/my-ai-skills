# my-ai-skills
工作规范、技能指令集、前后端开发约束、设计标准

# 🚀 FISS: Frontend Implementation Skills Specification
### (前端工程化实现技能约束体系)

`FISS` 是一套旨在消除 AI 生成代码“随机感”和“业余感”的工业级指令集。通过 8 个核心维度的强约束，强制 AI 遵循**【定义 $\rightarrow$ 架构 $\rightarrow$ 实现 $\rightarrow$ 审计】**的专业开发链路，确保产出代码具备极高的一致性、鲁棒性和可维护性。

---

## 🗺️ 体系地图 (The 8 Pillars)

本体系由 8 个互补模块组成，覆盖了从需求分析到生产交付的全生命周期：

| 序号 | 模块名称 | 核心目的 | 约束焦点 | 角色 |
| :--- | :--- | :--- | :--- | :--- |
| 01 | **`UI_Scheduling_System`** | 全局基调定义 | 主题 $\rightarrow$ 场景 $\rightarrow$ 需求优先级 | **调度员** |
| 02 | **`Spatial_Geometry`** | 消除视觉随意性 | 8px 步进 $\rightarrow$ 空间变量 $\rightarrow$ 对齐 | **量尺** |
| 03 | **`Atomic_Component_Logic`** | 防止代码冗余 | 原子 $\rightarrow$ 分子 $\rightarrow$ 组织 $\rightarrow$ Props 驱动 | **建筑师** |
| 04 | **`Global_State_Management`**| 杜绝数据碎片化 | Pinia Setup Store $\rightarrow$ Store-First 闭环 | **仓库管理员** |
| 05 | **`Data_Driven_Architecture`**| 消除静态死代码 | TS Interface $\rightarrow$ 数据映射 $\rightarrow$ 三态逻辑 | **发动机** |
| 06 | **`Interaction_State_Matrix`**| 覆盖边缘场景 | Loading $\rightarrow$ Empty $\rightarrow$ Error $\rightarrow$ Disabled | **质检员** |
| 07 | **`Adaptive_Orchestration`** | 实现完美适配 | `clamp()` 流式设计 $\rightarrow$ 布局重编排 | **变色龙** |
| 08 | **`Production_Engineering_Standard`**| 确保生产级质量 | TS 零 any $\rightarrow$ BEM 命名 $\rightarrow$ 性能审计 | **工程师** |

---

## 🛠️ 落地执行流程 (The Execution Pipeline)

**严禁直接要求 AI “写一个页面”**。必须引导 AI 按照以下五个阶段顺序执行，每一步必须经过你的确认才能进入下一步。

### 第一阶段：环境初始化 (Bootstrapping)
将所有 `.md` 技能文件发送给 AI，并发送启动指令：
> **Prompt**: "请加载 FISS 前端工程化约束体系的所有 8 个模块。在接下来的开发中，你必须严格遵守这些 Skill 的约束，并在每个交付阶段执行对应的【校验点】。确认加载完成请告知。"

### 第二阶段：需求调度与计划 (Orchestration)
基于 `UI_Scheduling_System` 定义本次任务的全局基调。
> **Prompt**: "现在执行 [XXX 需求]。请基于 `UI_Scheduling_System` 输出本次任务的【调度计划】，包含：主题风格、目标用户场景、核心功能优先级。"

### 第三阶段：架构蓝图定义 (Blueprinting)
在写代码前，强制 AI 完成底层设计（这是防止代码崩坏的关键）。
> **Prompt**: "请在进入代码实现前，提供以下架构方案：
> 1. **[组件清单]**：基于 `Atomic_Component_Logic` 列出本次需要的原子组件。
> 2. **[状态模型]**：基于 `Global_State_Management` 定义 Pinia Setup Store 的结构及 Store-First 流转逻辑。
> 3. **[数据契约]**：基于 `Data_Driven_Architecture` 定义所有接口的 TypeScript Interface。"

### 第四阶段：分层开发实现 (Layered Build)
引导 AI 按照视觉 $\rightarrow$ 结构 $\rightarrow$ 逻辑 $\rightarrow$ 适配的顺序编写代码。
> **Prompt**: "请开始实现代码。必须严格遵循：`Spatial_Geometry` 的 8px 步进 $\rightarrow$ `Adaptive_Orchestration` 的流式布局 $\rightarrow$ `Interaction_State_Matrix` 的全状态覆盖 $\rightarrow$ `Production_Engineering_Standard` 的 BEM 命名与 TS 类型。"

### 第五阶段：生产级审计 (Final Audit)
要求 AI 对产出的代码进行自我批判和审计。
> **Prompt**: "请基于 `Production_Engineering_Standard` 对上述代码进行【代码审计】，提交审计报告，重点标注：TS 类型完整度、BEM 规范执行情况、逻辑解耦程度以及性能优化点。"

---

## 🚨 违规红线 (Red-Line Checks)

如果在 AI 的输出中看到以下内容，请立即判定为 **FISS 违规** 并要求其重写：

*   **视觉违规**：出现 `padding: 15px` 或 `margin: 21px` $\rightarrow$ $\text{Violation: Spatial\_Geometry}$
*   **结构违规**：在页面中看到重复的 HTML 结构块，而非 `.map()` 渲染 $\rightarrow$ $\text{Violation: Data\_Driven\_Architecture}$
*   **数据违规**：在 `.vue` 组件中直接出现 `axios.get` 或 `fetch` $\rightarrow$ $\text{Violation: Global\_State\_Management}$
*   **状态违规**：只有成功加载的界面，缺失骨架屏或空状态 $\rightarrow$ $\text{Violation: Interaction\_State\_Matrix}$
*   **适配违规**：出现 `width: 1200px` 或简单的 `max-width` 缩放 $\rightarrow$ $\text{Violation: Adaptive\_Orchestration}$
*   **工程违规**：出现 `any` 类型、`.box-1` 类名或巨型组件逻辑 $\rightarrow$ $\text{Violation: Production\_Engineering\_Standard}$

---

## 📂 文件组织建议

建议将本体系文件存储于项目根目录的 `.fiss` 文件夹中：

```text
/your-project
  ├── .fiss/
  │   ├── 01_UI_Scheduling_System.md
  │   ├── 02_Spatial_Geometry.md
  │   ├── 03_Atomic_Component_Logic.md
  │   ├── 04_Global_State_Management.md
  │   ├── 05_Data_Driven_Architecture.md
  │   ├── 06_Interaction_State_Matrix.md
  │   ├── 07_Adaptive_Orchestration.md
  │   └── 08_Production_Engineering_Standard.md
  └── README.md (本文件)
```

---
**FISS 旨在将 AI 的输出从 "It works" (能跑就行) 提升至 "Production Ready" (生产可用)。**

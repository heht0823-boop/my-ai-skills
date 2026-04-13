# my-ai-skills
工作规范、技能指令集、前后端开发约束、设计标准

# 🚀 FISS: Frontend Implementation Skills Specification
### (前端工程化实现技能约束体系 v3.0)

`FISS` 是一套旨在消除 AI 生成代码“随机感”、“业余感”和“不可维护性”的工业级指令集。它通过 11 个维度的强约束，强制 AI 遵循 **【调度 $\rightarrow$ 架构 $\rightarrow$ 实现 $\rightarrow$ 审计 $\rightarrow$ 验证】** 的专业开发闭环，确保产出代码达到 **Production-Ready (生产级)** 标准。

**核心哲学**：不信任 AI 的“直觉”，只信任基于约束的“工程化输出”。

---

## 🗺️ 体系地图 (The 11 Pillars)

FISS 体系由 11 个互补模块组成，覆盖从视觉定义到质量交付的全生命周期：

| 序号 | 模块名称 | 核心目的 | 约束焦点 | 角色定位 |
| :--- | :--- | :--- | :--- | :--- |
| **01** | **`UI_Scheduling_System`** | 全局基调定义 | $\text{Platform\_ID} \times \text{Theme\_ID} \rightarrow$ 骨架与皮肤 | **调度员** |
| **02** | **`Spatial_Geometry`** | 消除视觉随意性 | 8pt Grid System $\rightarrow$ 语义化空间变量 | **量尺** |
| **03** | **`Atomic_Component_Logic`**| 防止代码冗余 | 原子 $\rightarrow$ 分子 $\rightarrow$ 组织 $\rightarrow$ Props 驱动 | **建筑师** |
| **04** | **`Global_State_Management`**| 杜绝数据碎片化 | Pinia Setup Store $\rightarrow$ Store-First 闭环 | **仓库管理员** |
| **05** | **`Data_Driven_Architecture`**| 消除静态死代码 | TS Interface $\rightarrow$ 数据映射 $\rightarrow$ 三态逻辑 | **发动机** |
| **06** | **`Interaction_State_Matrix`**| 覆盖边缘场景 | $\text{Loading} \rightarrow \text{Empty} \rightarrow \text{Error} \rightarrow \text{Disabled}$ | **质检员** |
| **07** | **`Adaptive_Orchestration`** | 实现完美适配 | `clamp()` 流式设计 $\rightarrow$ 结构性重编排 | **变色龙** |
| **08** | **`Production_Engineering_Standard`**| 确保生产质量 | 零 `any` $\rightarrow$ BEM 命名 $\rightarrow$ 逻辑解耦 | **工程师** |
| **09** | **`System_File_Orchestration`**| 规范项目组织 | 分层架构 $\rightarrow$ 路径可预测 $\rightarrow$ 导出规范 | **图书管理员** |
| **10** | **`Inclusive_A11y_Standard`** | 确保可用性/无障碍 | POUR原则 $\rightarrow$ ARIA增强 $\rightarrow$ 键盘导航 | **包容官** |
| **11** | **`QA_Verification_Protocol`** | 消除交付盲点 | 黑盒模拟 $\rightarrow$ 边界压力测试 $\rightarrow$ 链路走查 | **压力测试员** |

---

## 🛠️ 落地执行流 (The Execution Pipeline)

**严禁跳步执行**。必须引导 AI 按照以下五个阶段顺序进行，每一步需经过用户确认。

### Phase 1: 环境初始化 (Bootstrapping)
**动作**：加载 FISS 全量 11 个 Skill 模块。
> **Prompt**: "请加载 FISS 前端工程化约束体系的所有 11 个模块。在接下来的开发中，你必须严格遵守这些 Skill 的约束，并在每个交付阶段执行对应的【校验点】。确认加载完成请告知。"

### Phase 2: 需求调度与计划 (Orchestration)
**动作**：基于 `UI_Scheduling_System` 锁定视觉与交互基调。
> **Prompt**: "现在执行 [XXX 需求]。请输出【调度计划】：
> 1. 锁定 $\text{Platform\_ID}$ 与 $\text{Theme\_ID}$。
> 2. 分析目标用户场景、信息密度及交互优先级。"

### Phase 3: 架构蓝图定义 (Blueprinting)
**动作**：在写代码前，定义所有静态契约与物理结构（防止代码崩坏的关键）。
> **Prompt**: "请在实现代码前，提供【架构方案】：
> 1. **[组件清单]**：基于 `Atomic_Component_Logic` 定义原子/分子组件。
> 2. **[状态模型]**：基于 `Global_State_Management` 定义 Setup Store 结构。
> 3. **[数据契约]**：基于 `Data_Driven_Architecture` 定义 TS Interface。
> 4. **[文件编排]**：基于 `System_File_Orchestration` 提供具体的 $\text{File Tree}$ 预览及存放路径。"

### Phase 4: 分层开发实现 (Layered Build)
**动作**：由浅入深，将视觉、结构、逻辑、无障碍逐层注入。
> **Prompt**: "请开始实现代码。执行顺序：
> $\text{CSS Variables} \rightarrow \text{Semantic HTML} \rightarrow \text{8px Geometry} \rightarrow \text{Fluid Layout} \rightarrow \text{A11y Standards} \rightarrow \text{Full-State Logic} \rightarrow \text{TS Type Safety}$。"

### Phase 5: 生产级审计与验证 (Audit & Verification)
**动作**：强制 AI 进行自我批判与极端场景模拟。
> **Prompt**: "请提交【最终交付报告】，包含：
> 1. **[代码审计]**：基于 `Production_Engineering_Standard` 检查 $\text{any}$ 使用、BEM 命名与解耦程度。
> 2. **[无障碍审计]**：基于 `Inclusive_A11y_Standard` 确认键盘导航与 ARIA 标签覆盖情况。
> 3. **[QA 验证报告]**：基于 `QA_Verification_Protocol` 执行极端数据模拟（长文本/空数据/并发点击）并输出 $\text{Interaction Trace}$。"

---

## 🚨 违规红线 (Red-Line Checks)

一旦出现以下特征，立即判定为 **FISS 违规**，要求重写：

| 违规类型 | 典型症状 | 判定依据 |
| :--- | :--- | :--- |
| **视觉违规** | `padding: 13px`, `margin: 20px` | $\text{Violation: Spatial\_Geometry}$ |
| **结构违规** | 手动复制重复 HTML 块而非 `.map()` | $\text{Violation: Data\_Driven\_Architecture}$ |
| **数据违规** | 在组件内直接写 `axios.get` 或 `fetch` | $\text{Violation: Global\_State\_Management}$ |
| **状态违规** | 缺失 Skeleton 骨架屏或 Empty State | $\text{Violation: Interaction\_State\_Matrix}$ |
| **适配违规** | 出现 `width: 1200px` 或简单的 `@media` 缩放 | $\text{Violation: Adaptive\_Orchestration}$ |
| **工程违规** | 出现 `any` 类型, `.box-1` 类名, 或巨型组件 | $\text{Violation: Production\_Engineering\_Standard}$ |
| **组织违规** | 将所有代码堆在一个文件 / 随意命名文件夹 | $\text{Violation: System\_File\_Orchestration}$ |
| **可用性违规** | 纯图标按钮无 `aria-label` / 无法 Tab 导航 | $\text{Violation: Inclusive\_A11y\_Standard}$ |
| **验证违规** | 交付代码时未提供 $\text{QA Test Report}$ | $\text{Violation: QA\_Verification\_Protocol}$ |

---

## 📂 项目组织建议

建议将 FISS 约束体系作为项目的“法典”存储在根目录下，确保 AI 随时可检索：

```text
/your-project
  ├── .fiss/                 # FISS 约束法典 (Read-Only)
  │   ├── 01_UI_Scheduling_System.md
  │   ├── 02_Spatial_Geometry.md
  │   ├── 03_Atomic_Component_Logic.md
  │   ├── 04_Global_State_Management.md
  │   ├── 05_Data_Driven_Architecture.md
  │   ├── 06_Interaction_State_Matrix.md
  │   ├── 07_Adaptive_Orchestration.md
  │   ├── 08_Production_Engineering_Standard.md
  │   ├── 09_System_File_Orchestration.md
  │   ├── 10_Inclusive_A11y_Standard.md
  │   └── 11_QA_Verification_Protocol.md
  ├── src/                   # 严格遵循 FISS 产出的代码
  └── README.md              # 本文档
```

---
**FISS v3.0 旨在将 AI 的角色从 "Code Generator" (代码生成器) $\rightarrow$ "Software Architect" (软件架构师) $\rightarrow$ "QA Engineer" (质量工程师) 实现全链路升级。**

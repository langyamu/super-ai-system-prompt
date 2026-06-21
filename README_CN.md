# Super AI System Prompt

## 概述

面对 AI 的虚假附和与机械输出，你需要的不只是"更会思考"的模型，而是一套**可追问、可验证、可迭代的思辨规则系统**。

本项目采用"道法术"三层治理结构：以根本信条（Dao）约束价值观，以命名规则（Fa）定义可触发行为，以动态决策树（Shu）适配不同对话场景。通过 `use clm`（方法编目）、`use cm`（挑战验证）、`use dc`（深度澄清）等快捷命令，实现从"被动回答"到"主动思辨"的跃迁。

这是一套可直接加载到支持长上下文的 Chat 环境中的系统提示词协议，包含完整的规则定义、使用示例与版本历史。

---

思路参考：`thinking-claude` (启发性项目)

## 使用

> 历史版本见：[.archive](./.archive/)

### Chat

在支持长上下文的 chat 环境中加载 [v3.0.1.md](./prompt/v3.0.1.md) 即可使用。

> 若模型回复时使用了"联网"功能，建议在末尾追加 `use meta_rules` 指令，以防协议内容被截断遗忘。

加载后，可通过快捷命令激活对应规则：

| 命令 | 作用 |
|---|---|
| `use clm` | 针对当前问题推荐 2–3 个候选框架 |
| `use clm -a` | 全量列出所有已知方法论框架 |
| `use m [方法论名]` | 直接执行指定框架的推演 |
| `use cm` | 对已有推演结果进行跨框架挑战验证 |
| `use dc` | 发起深度澄清（九维分析） |

- 提示词：[v3.0.1.md](./prompt/v3.0.1.md)
- 英文版：[v3.0.1.en.md](./prompt/v3.0.1.en.md)

## Change Log

### v3.0.1 (2026-06-21)

refactor(v3.0.1): 规则命名规范化与命令体系调整

**命名规范化：**
- 规则名称统一调整为更精确的语义：
  - `rule:fast-clarify-trigger` → `rule:quick-clarify-requirement`
  - `rule:deep-clarification-trigger` → `rule:deep-clarify-requirement`
  - `rule:framework-discipline` → `rule:discipline-methodology-selection`
  - `rule:methodology-trigger` → `rule:apply-methodology`
  - `rule:think-methodology-trigger` → `rule:catalog-methodology`
  - `rule:cross-methodology-trigger` → `rule:challenge-methodology`
- 迭代接口输出标签：`[Methodology]` → `[Analysis Lens]`

**命令调整：**
- `use tm` → `use clm`
- 新增 `use clm -a` 参数支持全量编目模式
- 移除 `use fc`，快速澄清改为由 AI 在 `rule:redefine-before-answer` 阶段自行判断触发

**文档：**
- 更新 `prompt/v3.0.1.md` 与 `prompt/v3.0.1.en.md`

### v3.0.0 (2026-06-14)

feat(v3.0.0): 架构范式迁移——从 ATPE 模式系统到“道法术”规则系统

**核心变更：**
- 架构重构：彻底弃用 `[mode:analysis/think/methods/plan/exec]` 五模式体系，转向基于 `[rule:xxx]` 的命名规则系统
- 引入“道法术”三层认知架构：
  - 道（Fundamental Tenets）：四条根本信条（求真、系统、追问、迭代）
  - 法（Core Principles）：十条核心规则（重新定义、快速澄清、深度澄清、认知谦逊、框架纪律、方法论触发、方法推荐、跨方法验证、可证伪性、分层输出）
  - 术（Thinking Process）：动态决策树，根据对话状态只执行最必要的一步

**交互升级：**
- 新增五条快捷命令：`use tm`（方法推荐）、`use m [name]`（方法执行）、`use cm`（交叉验证）、`use fc`（快速澄清）、`use dc`（深度澄清）
- 迭代接口重构：从 `Used: {mode list}` 升级为 `[Methodology] + [Assumptions] + [Next Steps]`，其中 `[Next Steps]` 提供 `o1-o3` 可执行选项供用户直接选择

**规则增强：**
- 深度澄清机制：将旧版 `[mode:analysis]` 的九维分析（R1-R9）升级为 `[rule:deep-clarification-trigger]`，并新增 `[rule:fast-clarify-trigger]` 用于最小成本消除致命歧义
- 方法论体系化：新增 `[rule:think-methodology-trigger]`（候选框架推荐）与 `[rule:cross-methodology-trigger]`（多框架交叉验证）
- 质量把关：新增 `[rule:falsifiability-check]`（可证伪性检查）与 `[rule:layered-output]`（分层输出约束）
- 认知谦逊：新增 `[rule:epistemic-humility]`，替代旧版 Professional objectivity 段落

**精简与移除：**
- 移除 `[mode:analysis]` / `[mode:think]` / `[mode:methods]` / `[mode:plan]` / `[mode:exec]` 五种独立模式及其组合逻辑
- 移除 Mode Autonomy Policy、Proactiveness、Context Management、Continuous Requirement Refinement 等独立段落，其精华融入具体规则
- 移除“侦探/专家/哲学家/顾问”四种角色隐喻，转为四条根本信条

**文档：**
- 新增 `prompt/v3.0.0.md`
- 新增 `prompt/v3.0.0.en.md`
- v2.11.0 归档至 .archive

### v2.11.0 (2026-01-06)

refactor(v2.11.0): 从 skills 到 modes 的语义重构

**核心变更：**
- 重命名模式：[sk:*] → [mode:*]
- 模式独立性：每个模式完全独立，无依赖关系
- 灵活组合：支持任意顺序使用（顺序/并行/混合）

**架构调整：**
- 新增"模式自治策略"（独立运作、灵活组合、软性指导）
- [mode:plan] 增强最佳实践
- [mode:methods] 交接改为可选
- [mode:exec] 支持无计划灵活执行

**文档：**
- 提示词：prompt/v2.11.0.md
- 更新所有模板和命令
- v2.10.0 归档至 .archive

### v2.10.0 (2025-11-16)

feat(v2.10.0): 引入 v2.10.0 系列提示词与 Claude 代码模板；加强模式模块化

**提示词变更：**
- 核心文件重命名为版本化：`prompt/v2.10.0.md`、`prompt/v2.10.0.en.md`、`prompt/v2.10.0.enhanced.md`
- 结构重写，显式拆分为章节：`[behavior]`、`[mode:analysis]`、`[mode:think]`、`[mode:methods]`、`[mode:plan]`、`[mode:exec]`
- 新增"Proactiveness（主动性）"与"Mode Autonomy Policy（模式自治策略）"，明确何时分析/规划/执行
- `v2.10.0.enhanced.md` 保留并扩展特定场景模块（如风格迁移模板、专业知识雷达）

**模板：**
- 新增 `template-claude-code/`，包含 `CLAUDE.md` 与 `.claude/commands/sk/*`，用于基于命令的模式调用
- `template-trae/.trae/user_rules.md` 与 v2.10.0 模式分类对齐；`rules/project_rules.md` 进一步完善

**文档与使用：**
- README 链接切换为 `prompt/v2.10.0.md`
- 旧版本保留于 `.archive/v2.9.0`

### v2.9.0 (2025-10-06)

refactor(v2.9.0): 全面重构提示词架构，简化工作流并强化执行力

**核心架构变更：**
- 从嵌套标记语言格式迁移至扁平化 Markdown 结构，大幅提升可读性
- 引入"分析-计划-执行"(Analyze-Plan-Execute)核心原则，强化系统性思维
- 简化思维框架：从"抽象-具体化-重构-增强"四步简化为"抽象-具体化-重构"三步核心流程

**模式系统优化：**
- 移除"自主模式/手动模式"的复杂模式切换机制
- 简化为两个一次性命令：`/think`（仅输出思考块）和 `/result`（仅输出答案）
- 默认行为统一为：先输出 brainstorming 块，再给出正式答案

**Brainstorming 块重构：**
- 移除 "Enhancement"（增强）步骤，避免过度关注 prompt 优化
- 新增 "Planning"（规划）步骤，聚焦可执行路线图：优先级排序、策略匹配、执行顺序、应急预案
- 优化 "Abstraction" 描述，明确使用第一性原理进行逻辑重构
- 改进 "Reframing" 说明，强调视角多样性与综合统一
- 将 continuous_requirement_correction 的 9 个分析模板项标记为 R1-R9，提升结构化

**行为规则精简：**
- 将原 9 条 core_rules 精简整合到 behavior 的 default 行为中
- 移除冗余的"AI 自主决定思考深度"等描述性规则
- 保留核心行为准则：侦探式深挖、专家式应用方法论、哲学式多维思考、顾问式持续校准

**持续需求修正优化：**
- 简化 analysis_framework，移除"福尔摩斯式推理"等修饰性描述
- 保留 4 条核心原则：持续分析、拒绝表面需求、主动挖掘深层意图、归纳到演绎的思维进阶

**文档一致性：**
- 统一 thinking.md、thinking.cn.md、thinking.en.md 三个语言版本的核心结构
- thinking.enhanced.md 在标准版基础上增加"风格转换 prompt 生成"和"专业知识雷达"功能模块

### v2.8.2 (2025-09-08)

refactor(v2.8.2): 更新文档结构并优化提示词内容

- 重构文档目录结构，将旧版本归档至.archive目录
- 统一并优化中英文提示词内容，增强一致性
- 删除冗余片段文件，合并功能到主提示词文件
- 改进提示词格式和标记语言，提升可读性
- 添加专家面板功能片段，扩展系统能力

### v2.8.1 (2025-09-04)

refactor: 重构思维框架并添加新功能模块

- 将“持续需求修正”
(continuous_requirement_correction)模块拆分为独立文件
- 添加“文生图风格转换提示规范”(text_to_image_style_transfer_prompt_specification)功能模块
- 更新thinking.enhanced.md整合所有功能

### v2.8.0 (2025-09-03)

feat: 重构SASP协议并迁移至新标记语言格式

重构核心协议文件，将XML格式迁移至更简洁的标记语言格式，优化文档结构和描述。更新README文件以反映最新协议版本和使用方式。

新增多语言支持：
- 添加thinking.cn.md、thinking.en.md和thinking.md作为核心协议文件
- 更新文档结构，将历史版本移至.archive目录

其他变更：
- 添加.vscode目录到.gitignore
- 删除不再使用的.pre目录
- 简化项目概述并改进使用说明

### (pre)v2.7.0 (2025-08-12)

refactor(pre): 更新协议文档，优化描述和框架结构

- 改进协议描述，更清晰说明SASP的目的和功能
- 重构思维框架部分，使用更简洁的术语
- 完善brainstorming_block的示例和说明
- 调整模式定义，明确/deep和/fast的区别

### (pre)v2.7.0 (2025-08-02)

refactor(pre)更新v2.7.0

- 移除命令语法相关内容，简化文档结构
- 更新模式描述，更清晰地说明/deep和/fast的区别
- 添加新README文件说明如何使用思维框架

### v2.6.2 (2025-07-22)

refactor(prompt,template,gitignore): 重构项目规则文件并更新gitignore

- template-trae: 将.SASP/_note.md迁移至.trae/rules/project_rules.md
- 更新gitignore添加.trae目录排除
- 优化XML文件结构，删除重复内容
- 重命名basic_rules为basic_thinking_rules
- 完善用户交互选项逻辑描述
- 统一中英文版本的核心目标格式

### v2.6.1 (2025-07-20)

- 增强brainstorming_block响应选项机制
- 新增AI灵活选择：直接回答vs继续思考vs工具查询
- 统一标签命名并同步所有提示词版本
- 更新README使用文档

# Super AI System Prompt

## 概述

这是一份外显化 AI 的思考过程的提示词。同时也是一套将“抽象化-具体化-重写-问题清单-规划-下一步”六个步骤为轻量工作流的尝试，旨在将 AI 从一个简单的答案提供者，转变为一个能对用户主动提问、共同探索复杂问题的思考伙伴。

---

思路参考：`thinking-claude` (启发性项目)

## 使用

> 历史版本见：[.archive](./.archive/)

### Chat

> 在 chat 环境下如果模型回复时使用了“联网”功能，那么需要在您的回复的末尾添加 `use meta_rules` 指令，否则模型可能会忘记 meta_rules 协议的内容 。

- 提示词：[v2.10.0.md](./prompt/v2.10.0.md)
  - 在支持在线网页解析的 chat 环境下输入
    ```plantext
    https://github.com/langyamu/super-ai-system-prompt/raw/refs/heads/main/prompt/v2.10.0.md

    use meta_rules
    ```
    或者
    ```plantext
    https://github.com/langyamu/super-ai-system-prompt/raw/refs/heads/main/prompt/v2.10.0.md

    All subsequent conversations will default to using the meta_rules
    ```
### Project Template

- 模板参考：[template-trae](./template-trae/)
- 模板参考：[template-claude-code](./template-claude-code/)

## Change Log

### v2.10.0 (2025-11-16)

feat(v2.10.0): 引入 v2.10.0 系列提示词与 Claude 代码模板；加强技能模块化

**提示词变更：**
- 核心文件重命名为版本化：`prompt/v2.10.0.md`、`prompt/v2.10.0.en.md`、`prompt/v2.10.0.enhanced.md`
- 结构重写，显式拆分为章节：`[behavior]`、`[sk:analysis]`、`[sk:think]`、`[sk:methods]`、`[sk:plan]`、`[sk:exec]`
- 新增“Proactiveness（主动性）”与“Skill Autonomy Policy（技能自治策略）”，明确何时分析/规划/执行
- `v2.10.0.enhanced.md` 保留并扩展特定场景模块（如风格迁移模板、专业知识雷达）

**模板：**
- 新增 `template-claude-code/`，包含 `CLAUDE.md` 与 `.claude/commands/sk/*`，用于基于命令的技能调用
- `template-trae/.trae/user_rules.md` 与 v2.10.0 技能分类对齐；`rules/project_rules.md` 进一步完善

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

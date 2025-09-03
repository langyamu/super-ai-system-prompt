# Super AI System Prompt

## 概述

这是一份外显化 AI 的思考过程的提示词。同时也是一套将“抽象化-具体化-重写-增强-问题清单-下一步”六个步骤为轻量工作流的尝试，旨在将 AI 从一个简单的答案提供者，转变为一个能对用户主动提问、共同探索复杂问题的思考伙伴。

---

思路参考：`thinking-claude` (启发性项目)

## 使用

> 历史版本见：[.archive](./.archive/)

### chat

> 在 chat 环境下如果模型回复时使用了“联网”功能，那么需要在您的回复的末尾添加 `use SASP` 指令，否则模型可能会忘记 SASP 协议的内容 。

- 提示词：[thinking.md](./prompt/thinking.md)
  - 在支持在线网页解析的 chat 环境下输入
    ```plantext
    https://github.com/langyamu/super-ai-system-prompt/raw/refs/heads/main/prompt/thinking.md

    use SASP
    ```
    或者
    ```plantext
    https://github.com/langyamu/super-ai-system-prompt/raw/refs/heads/main/prompt/thinking.md

    All subsequent conversations will default to using the SASP
    ```
### project

- 模板参考：[template-trae](./template-trae/)

## Change Log

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

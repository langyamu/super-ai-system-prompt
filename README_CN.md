# Super AI System Prompt

## 项目概述

项目旨在探索和定义一套通用的 user 与 AI 协作方式的 super system
prompt，其核心目标是引导 AI
在处理任何用户请求时，通过一些通用的结构化的分析方法、思想(通用方法论)等，展现出深层次、结构化的思考过程，以及更精准的需求洞察和高效、富有同理心的沟通能力。

---

思路参考：`thinking-claude` (启发性项目)

## 使用

### chat

- 提示词：[chat](./prompt/thinking.chat.xml)

- 在支持在线网页解析的 chat 环境下输入
  ```plantext
  https://github.com/langyamu/super-ai-system-prompt/raw/refs/heads/main/prompt/thinking.chat.xml

  start $:SASP
  ```
  或者
  ```plantext
  https://github.com/langyamu/super-ai-system-prompt/raw/refs/heads/main/prompt/thinking.chat.xml

  All subsequent conversations will default to using the $:SASP
  ```

### project

- 提示词：[project](./prompt/thinking.project.xml)

- 模板参考：[template-trae](./template-trae/)

## Change Log

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

# Super AI System Prompt

[View Chinese Version](./README_CN.md)

## Project Overview

This project aims to explore and define a universal super system prompt for
user-AI collaboration. Its core objective is to guide AI in demonstrating deep,
structured thinking processes, more precise requirement insights, and efficient,
empathetic communication capabilities when handling any user request through
universal structured analysis methods and thinking approaches (general
methodologies).

---

Inspiration: `thinking-claude` (inspirational project)

## Usage

### chat

- Prompt: [chat](./prompt/thinking.chat.xml)

- In AI chat environments that support online webpage parsing, input:
  ```plaintext
  https://github.com/langyamu/super-ai-system-prompt/raw/refs/heads/main/prompt/thinking.chat.xml

  start $:SASP
  ```
  or
  ```plantext
  https://github.com/langyamu/super-ai-system-prompt/raw/refs/heads/main/prompt/thinking.chat.xml

  All subsequent conversations will default to using the $:SASP
  ```

### project

- Prompt: [project](./prompt/thinking.project.xml)

- Template reference: [template-trae](./template-trae/)

## Change Log

### (pre)v2.7.0 (2025-08-12)

refactor(pre): Update protocol documentation to enhance descriptions and framework structure

- Refined protocol description for clearer explanation of SASP’s purpose and capabilities  
- Restructured thinking framework section with more concise terminology  
- Expanded and clarified brainstorming_block examples and explanations  
- Revised mode definitions to explicitly distinguish /deep from /fast

### (pre)v2.7.0 (2025-08-02)

refactor(pre) update v2.7.0

- Removed command syntax content to simplify documentation structure
- Updated mode descriptions to clarify the difference between /deep and /fast
- Added a new README file explaining how to use the thinking framework

### v2.6.2 (2025-07-22)

refactor(prompt,template,gitignore): reorganize project rules file and update
.gitignore

- template-trae: moved `.SASP/_note.md` to `.trae/rules/project_rules.md`
- updated `.gitignore` to exclude the `.trae` directory
- optimized XML structure and removed duplicate content
- renamed `basic_rules` to `basic_thinking_rules`
- refined user interaction option logic descriptions
- unified the format of core objectives across Chinese and English versions

### v2.6.1 (2025-07-20)

- Enhanced brainstorming_block response options mechanism
- Added AI flexible choices: direct answer vs continue thinking vs tool query
- Unified tag naming and synchronized all prompt versions
- Updated README usage documentation

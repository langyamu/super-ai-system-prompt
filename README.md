# Super AI System Prompt

[View Chinese Version](./README_CN.md)


## Overview

This is a prompt that externalizes the AI's thinking process. It is also an attempt to create a lightweight workflow with six steps: "Abstraction-Concretization-Reframing-Enhancement-Question_List-Next_Steps". It aims to transform the AI from a simple answer provider into a thinking partner that can proactively ask users questions and explore complex problems together.

---

Inspired by: `thinking-claude` (an inspirational project)

## Usage

> For historical versions, see: [.archive](./.archive/)

### Chat

> In a chat environment, if the model uses features like "web search", you need to add the `use SASP` command at the end of your reply, otherwise the model might forget the content of the SASP protocol.

- Prompt: [thinking.md](./prompt/thinking.md)
  - In a chat environment that supports parsing online web pages, enter:
    ```plantext
    [https://github.com/langyamu/super-ai-system-prompt/raw/refs/heads/main/prompt/thinking.md](https://github.com/langyamu/super-ai-system-prompt/raw/refs/heads/main/prompt/thinking.md)

    use SASP
    ```
    or
    ```plantext
    [https://github.com/langyamu/super-ai-system-prompt/raw/refs/heads/main/prompt/thinking.md](https://github.com/langyamu/super-ai-system-prompt/raw/refs/heads/main/prompt/thinking.md)

    All subsequent conversations will default to using the SASP
    ```

### Project

- Template reference: [template-trae](./template-trae/)

## Change Log

### v2.8.0 (2025-09-03)

Feature: Refactor the SASP Protocol and Migrate to a New Markup Language Format

Refactor the core protocol file, migrate from the XML format to a more concise markup language format, and optimize the document structure and descriptions. Update the README file to reflect the latest protocol version and usage.

Add multilingual support:
- Add thinking.cn.md, thinking.en.md, and thinking.md as the core protocol files.
- Update the document structure, moving historical versions to the .archive directory.

Other changes:
- Add the .vscode directory to .gitignore.
- Remove the unused .pre directory.
- Simplify the project overview and improve the usage instructions.

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

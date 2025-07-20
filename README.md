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

### project

- Prompt: [project](./prompt/thinking.project.xml)

- Template reference: [template-trae](./template-trae/)

## Change Log

### v2.6.1 (2025-07-20)

- Enhanced brainstorming_block response options mechanism
- Added AI flexible choices: direct answer vs continue thinking vs tool query
- Unified tag naming and synchronized all prompt versions
- Updated README usage documentation

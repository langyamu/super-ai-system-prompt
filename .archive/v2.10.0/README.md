# Super AI System Prompt

[View Chinese Version](./README_CN.md)


## Overview

This is a prompt that externalizes the AI's thinking process. It is also an attempt to create a lightweight workflow with six steps: "Abstraction-Concretization-Reframing-Question_List-Planning-Next_Steps". It aims to transform the AI from a simple answer provider into a thinking partner that can proactively ask users questions and explore complex problems together.

---

Inspired by: `thinking-claude` (an inspirational project)

## Usage

> For historical versions, see: [.archive](./.archive/)

### Chat

> In a chat environment, if the model uses features like "web search", you need to add the `use meta_rules` command at the end of your reply, otherwise the model might forget the content of the meta_rules protocol.

- Prompt: [v2.10.0.md](./prompt/v2.10.0.md)
  - In a chat environment that supports parsing online web pages, enter:
    ```plantext
    https://github.com/langyamu/super-ai-system-prompt/raw/refs/heads/main/prompt/v2.10.0.md

    use meta_rules
    ```
    or
    ```plantext
    https://github.com/langyamu/super-ai-system-prompt/raw/refs/heads/main/prompt/v2.10.0.md

    All subsequent conversations will default to using the meta_rules
    ```

### Project Template

- Template reference: [template-trae](./template-trae/)
- Template reference: [template-claude-code](./template-claude-code/)

## Change Log

### v2.10.0 (2025-11-16)

feat(v2.10.0): Introduce new prompt series and Claude code template; strengthen skills modularization

**Prompt changes:**
- Rename core prompt files to versioned names: `prompt/v2.10.0.md`, `prompt/v2.10.0.en.md`, `prompt/v2.10.0.enhanced.md`
- Rewrite structure with explicit sections: `[behavior]`, `[sk:analysis]`, `[sk:think]`, `[sk:methods]`, `[sk:plan]`, `[sk:exec]`
- Add "Proactiveness" and "Skill Autonomy Policy" to clarify when to analyze/plan/execute
- `v2.10.0.enhanced.md` retains specialized modules (e.g., style-transfer template, knowledge radar)

**Templates:**
- New `template-claude-code/` with `CLAUDE.md` and `.claude/commands/sk/*` for command-based skill invocation
- `template-trae/.trae/user_rules.md` aligned with v2.10.0 skills taxonomy; `rules/project_rules.md` refined

**Docs & Usage:**
- Update README links to use `prompt/v2.10.0.md`
- Keep older versions under `.archive/v2.9.0`

### v2.9.0 (2025-10-06)

refactor(v2.9.0): Comprehensive prompt architecture refactoring to simplify workflow and enhance execution

**Core Architecture Changes:**
- Migrated from nested markup language format to flat Markdown structure, significantly improving readability
- Introduced "Analyze-Plan-Execute" (APE) core principle to strengthen systematic thinking
- Simplified thinking framework: reduced from "Abstraction-Concretization-Reframing-Enhancement" four steps to "Abstraction-Concretization-Reframing" three core steps

**Mode System Optimization:**
- Removed complex "Autonomous Mode/Manual Mode" switching mechanism
- Simplified to two one-time commands: `/think` (output thinking block only) and `/result` (output answer only)
- Unified default behavior: output brainstorming block first, then provide formal answer

**Brainstorming Block Refactoring:**
- Removed "Enhancement" step to avoid over-focusing on prompt optimization
- Added "Planning" step, focusing on actionable roadmap: prioritization, strategy matching, execution sequence, contingency plans
- Optimized "Abstraction" description to explicitly use first principles for logical reconstruction
- Improved "Reframing" explanation to emphasize perspective diversity and unified synthesis
- Labeled the 9 continuous_requirement_correction analysis template items as R1-R9 for better structure

**Behavior Rules Streamlining:**
- Consolidated original 9 core_rules into behavior's default actions
- Removed redundant descriptive rules like "AI decides thinking depth autonomously"
- Retained core behavioral principles: detective-style deep diving, expert-style methodology application, philosopher-style multi-dimensional thinking, consultant-style continuous calibration

**Continuous Requirement Correction Optimization:**
- Simplified analysis_framework, removed decorative descriptions like "Holmesian deduction"
- Retained 4 core principles: continuous analysis, reject surface needs, proactively uncover deep intentions, progress from induction to deduction

**Documentation Consistency:**
- Unified core structure across thinking.md, thinking.cn.md, and thinking.en.md language versions
- thinking.enhanced.md adds "style transfer prompt generation" and "specialized knowledge radar" modules on top of standard version

### v2.8.2 (2025-09-08)

refactor(v2.8.2): Restructure documentation and refine prompt content

- Reorganize directory layout; archive legacy versions to .archive folder  
- Harmonize and optimize Chinese-English prompts for greater consistency  
- Remove redundant snippet files, merging functionality into main prompt files  
- Improve prompt formatting and markup to enhance readability  
- Add expert-panel feature snippet, extending system capabilities

### v2.8.1 (2025-09-04)

refactor: Reconstructed the thinking framework and added new functional modules

- Split the "continuous_requirement_correction" module into a separate file  
- Added the "text_to_image_style_transfer_prompt_specification" functional module  
- Updated thinking.enhanced.md to integrate all features  

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

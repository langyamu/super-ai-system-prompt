# Super AI System Prompt

[View Chinese Version](./README_CN.md)


## Overview

Tired of AI's false agreement and mechanical output? You need more than a "smarter" model—you need a **thinking rule system open to challenge, verification, and iteration**.

This project adopts a "Dao-Fa-Shu" three-layer governance structure: fundamental tenets (Dao) constrain values, named rules (Fa) define triggerable behaviors, and dynamic decision trees (Shu) adapt to different conversation contexts. Through quick commands like `use clm` (methodology catalog), `use cm` (challenge verification), and `use dc` (deep clarification), we transform AI from a passive answerer into an active thinking partner.

This is a system-level prompt protocol that can be directly loaded into long-context chat environments, including complete rule definitions, usage examples, and version history.

---

Inspired by: `thinking-claude` (an inspirational project)

## Usage

> For historical versions, see: [.archive](./.archive/)

### Chat

Load [v3.0.1.en.md](./prompt/v3.0.1.en.md) in a long-context chat environment to get started.

> If the model uses web search or browsing during the conversation, consider appending `use meta_rules` at the end of your message to prevent the protocol from being truncated or forgotten.

After loading, activate rules via quick commands:

| Command | Function |
|---|---|
| `use clm` | Recommend 2–3 candidate frameworks for the current problem |
| `use clm -a` | List all known methodologies comprehensively |
| `use m [methodology]` | Execute the specified framework directly |
| `use cm` | Challenge-verify existing deductions with complementary frameworks |
| `use dc` | Trigger a deep clarification (9-dimension analysis) |

- Prompt: [v3.0.1.en.md](./prompt/v3.0.1.en.md)
- Chinese Version: [v3.0.1.md](./prompt/v3.0.1.md)

## Change Log

### v3.0.1 (2026-06-21)

refactor(v3.0.1): Rule naming normalization and command system adjustment

**Naming Normalization:**
- Rule names unified to more precise semantics:
  - `rule:fast-clarify-trigger` → `rule:quick-clarify-requirement`
  - `rule:deep-clarification-trigger` → `rule:deep-clarify-requirement`
  - `rule:framework-discipline` → `rule:discipline-methodology-selection`
  - `rule:methodology-trigger` → `rule:apply-methodology`
  - `rule:think-methodology-trigger` → `rule:catalog-methodology`
  - `rule:cross-methodology-trigger` → `rule:challenge-methodology`
- Iteration interface output tag: `[Methodology]` → `[Analysis Lens]`

**Command Adjustment:**
- `use tm` → `use clm`
- Added `use clm -a` parameter to support full catalog mode
- Removed `use fc`; fast clarification is now triggered automatically by AI during the `rule:redefine-before-answer` stage

**Docs:**
- Updated `prompt/v3.0.1.md` and `prompt/v3.0.1.en.md`

### v3.0.0 (2026-06-14)

feat(v3.0.0): Architectural paradigm migration—from ATPE mode system to "Dao-Fa-Shu" rule system

**Core Changes:**
- Architectural refactoring: Completely deprecated the `[mode:analysis/think/methods/plan/exec]` five-mode system, migrated to a named rule system based on `[rule:xxx]`
- Introduced the "Dao-Fa-Shu" three-layer cognitive architecture:
  - Dao (Fundamental Tenets): Four core convictions (truth-seeking, systems thinking, inquiry, iterability)
  - Fa (Core Principles): Ten named rules (redefine-before-answer, fast-clarify, deep-clarification, epistemic-humility, framework-discipline, methodology-trigger, think-methodology, cross-methodology, falsifiability-check, layered-output)
  - Shu (Thinking Process): Dynamic decision tree that executes only the most necessary step based on conversation state

**Interaction Upgrade:**
- Added five quick commands: `use tm` (method recommendation), `use m [name]` (method execution), `use cm` (cross-validation), `use fc` (fast clarification), `use dc` (deep clarification)
- Iteration interface refactored: Upgraded from `Used: {mode list}` to `[Methodology] + [Assumptions] + [Next Steps]`, where `[Next Steps]` provides `o1-o3` actionable options

**Rule Enhancements:**
- Deep clarification mechanism: Upgraded the legacy `[mode:analysis]` nine-dimension analysis (R1–R9) to `[rule:deep-clarification-trigger]`, and added `[rule:fast-clarify-trigger]` for minimal-cost elimination of fatal ambiguities
- Methodology systematization: Added `[rule:think-methodology-trigger]` (candidate framework recommendation) and `[rule:cross-methodology-trigger]` (multi-framework cross-validation)
- Quality gate: Added `[rule:falsifiability-check]` (falsifiability check) and `[rule:layered-output]` (layered output constraint)
- Epistemic humility: Added `[rule:epistemic-humility]`, replacing the legacy Professional objectivity section

**Removed:**
- Removed the five independent modes `[mode:analysis]` / `[mode:think]` / `[mode:methods]` / `[mode:plan]` / `[mode:exec]` and their composition logic
- Removed Mode Autonomy Policy, Proactiveness, Context Management, Continuous Requirement Refinement sections; their essence integrated into specific rules
- Removed the four role metaphors (detective/expert/philosopher/consultant), replaced with four fundamental tenets

**Docs:**
- Added `prompt/v3.0.0.md`
- Added `prompt/v3.0.0.en.md`
- Archived v2.11.0 under .archive

### v2.11.0 (2026-01-06)

refactor(v2.11.0): Semantic reconstruction from skills to modes - enhance architectural flexibility

**Core Changes:**
- Rename modes: [sk:*] → [mode:*]
- Mode independence: Each mode operates independently without dependencies
- Flexible composition: Support arbitrary order usage (sequential/parallel/mixed)

**Architecture Adjustments:**
- Add "Mode Autonomy Policy" (independent operation, flexible composition, soft guidance)
- [mode:plan] enhanced with best practices
- [mode:methods] handoff changed to optional
- [mode:exec] supports flexible execution without mandatory plans

**Docs:**
- Prompt: prompt/v2.11.0.md
- Update all templates and commands
- v2.10.0 archived under .archive

### v2.10.0 (2025-11-16)

feat(v2.10.0): Introduce new prompt series and Claude code template; strengthen modes modularization

**Prompt changes:**
- Rename core prompt files to versioned names: `prompt/v2.10.0.md`, `prompt/v2.10.0.en.md`, `prompt/v2.10.0.enhanced.md`
- Rewrite structure with explicit sections: `[behavior]`, `[mode:analysis]`, `[mode:think]`, `[mode:methods]`, `[mode:plan]`, `[mode:exec]`
- Add "Proactiveness" and "Mode Autonomy Policy" to clarify when to analyze/plan/execute
- `v2.10.0.enhanced.md` retains specialized modules (e.g., style-transfer template, knowledge radar)

**Templates:**
- New `template-claude-code/` with `CLAUDE.md` and `.claude/commands/sk/*` for command-based mode invocation
- `template-trae/.trae/user_rules.md` aligned with v2.10.0 modes taxonomy; `rules/project_rules.md` refined

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

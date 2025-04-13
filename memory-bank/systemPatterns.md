# System Patterns

## System Architecture

*   Primarily a hierarchical file system structure designed for clear categorization of software repositories.
*   Management involves user actions (placing initial files/cloning into `_Import`) and AI-driven processes (sorting imports, documentation updates) triggered by commands/requests.

## Key Technical Decisions

*   **Directory Structure:** Use of a predefined, multi-level directory structure (`Work`, `Personal`, `OpenSource`, `MCP/...`, `_Import`, `Uncategorized`) as the core organization method.
*   **Specialized Category:** Establishment of a distinct `MCP` category with its own internal structure.
*   **Staging & Workflow:** Use of an `_Import` staging directory and a specific command (`/sort_imports`) for controlled intake of new repositories.
*   **README Mandate:** Requirement for a `README.md` file within each repository directory.
*   **Documentation Standard:** Use of Markdown (`.md`) for all guiding documents (`AI_PROJECT_MANAGEMENT_GUIDE.md`) and the Memory Bank.
*   **AI Delegation:** Assigning primary responsibility for file system manipulation, rule adherence, and documentation updates to the AI assistant.

## Design Patterns in Use

*   **Rule-Based System:** AI actions governed by explicit rules in `AI_PROJECT_MANAGEMENT_GUIDE.md`.
*   **Staging Area:** `_Import` directory isolates incoming items before processing.
*   **Hierarchical Categorization:** Standard pattern for organizing repositories.

## Component Relationships

*   **File System:** The primary "runtime" environment.
*   **Category Folders:** Containers for repository folders.
*   **`_Import` Folder:** Designated input point for new repositories.
*   **`AI_PROJECT_MANAGEMENT_GUIDE.md`:** Rulebook/configuration for AI behavior.
*   **`memory-bank/`:** Stores the evolving context and state of the project organization system itself.
*   **AI Assistant:** Interacts with the file system and documentation based on user prompts and defined rules. 
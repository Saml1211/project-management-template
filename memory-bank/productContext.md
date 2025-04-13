# Product Context

## Why This Project Exists

*   To address the challenges of managing numerous software repositories in a disorganized manner.
*   Problems solved:
    *   Difficulty in locating specific projects quickly.
    *   Ambiguity regarding the context/purpose of projects (Work, Personal, OpenSource, MCP).
    *   Inconsistent and ad-hoc processes for integrating new repositories.
    *   Lack of clear guidelines for AI assistants managing the workspace, risking errors.
*   Goal: Create a predictable, maintainable, and efficient environment for all projects within the `/Projects` directory.

## How It Should Work

*   **Structure Enforcement:** Operates based on a predefined folder structure (`Work`, `Personal`, `OpenSource`, `MCP`, `Uncategorized`, `_Import`) with a specific sub-structure for `MCP` (`OpenSource`, `Personal`, `Management`).
*   **AI-Driven Management:** AI assistants are the primary agents responsible for maintaining the structure, following rules in `AI_PROJECT_MANAGEMENT_GUIDE.md`.
*   **Import Workflow:** New repositories are added via `/_Import/` and sorted into their correct category by an AI upon the `/sort_imports` command.
*   **README Requirement:** Every repository directory must contain a `README.md` file (basic one created if missing).
*   **Documentation Integrity:** Key documents (`README.md`, `AI_PROJECT_MANAGEMENT_GUIDE.md`, `memory-bank/`) are kept current.

## User Experience Goals

*   **Clarity:** Instantly understand the location and purpose of any repository via the structure.
*   **Consistency:** Uniform and predictable organization, regardless of who adds/moves repositories.
*   **Efficiency:** Quick and easy finding, adding, and managing of repositories; streamlined import process.
*   **Reliability:** Trust in the correct maintenance of the structure by AI assistants and the accuracy of documentation.
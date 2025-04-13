# AI Project Management Guide: `/Projects` Directory

**Objective:** To maintain a consistently organized `Projects` workspace by correctly categorizing and placing software repositories and related files.

**Audience:** AI Assistants tasked with managing files and repositories within this directory.

## Core Directory Structure

The `/Projects` directory uses a top-level categorization system:

1.  **`/Work/`**: Repositories directly related to professional employment or contracts.
2.  **`/Personal/`**: Repositories for personal projects, experiments, or utilities not intended for open source or work.
3.  **`/OpenSource/`**: Repositories intended for public release, forks of public projects, or contributions to them.
4.  **`/MCP/`**: A specialized top-level category for *all* projects related to the Model Context Protocol (MCP). **Crucially, MCP projects should *not* be placed in the general `Work`, `Personal`, or `OpenSource` folders.**
5.  **`/Uncategorized/`**: A *temporary* holding area. If a project's category cannot be determined, place it here and flag it for human review. The goal is to keep this empty.

## The `/MCP/` Sub-Structure

The `/MCP/` directory has its own internal categorization:

*   **`/MCP/OpenSource/`**: MCP servers, tools, or libraries that are open source.
*   **`/MCP/Personal/`**: Custom MCP servers, tools, libraries, or related documentation/files that are private/personal.
*   **`/MCP/Management/`**: Tools, scripts, or agents specifically designed for managing, monitoring, deploying, or interacting with MCP servers and configurations.

## Importing and Sorting New Repositories

To streamline the process of adding new repositories:

1.  **Place New Repos:** Clone or download any new repositories directly into the `/_Import/` directory at the root of the `Projects` workspace.
2.  **Initiate Sorting:** Use the command `/sort_imports`.
3.  **AI Action:** Upon receiving this command, the AI assistant MUST:
    *   Review this guide (`AI_PROJECT_MANAGEMENT_GUIDE.md`).
    *   List the contents of `/_Import/`.
    *   For each **directory** found within `/_Import/`, execute the "Standard Workflow for Adding/Moving Repositories" (steps 1-6) outlined above, moving the directory from `/_Import/` to its final categorized location.
    *   Generate a summary report of actions taken.
    *   Update the directory tree in the root `README.md`.

## Standard Workflow for Adding/Moving Repositories

1.  **Identify Project Type:** Determine the primary nature of the repository/files.
    *   Is it related to the **Model Context Protocol (MCP)**? If YES, proceed to step 2. If NO, proceed to step 3.
2.  **Categorize MCP Project:**
    *   Is it **Open Source**? Place in `/MCP/OpenSource/`.
    *   Is it a **Management Tool/Script/Agent**? Place in `/MCP/Management/`.
    *   Is it **Personal/Private** (including documentation)? Place in `/MCP/Personal/`.
    *   **STOP HERE** for MCP projects.
3.  **Categorize Non-MCP Project:**
    *   Is it for **Work**? Place in `/Work/`.
    *   Is it **Open Source**? Place in `/OpenSource/`.
    *   Is it **Personal**? Place in `/Personal/`.
    *   If unsure after reviewing READMEs or context, place in `/Uncategorized/` and notify the user.
4.  **Verify README:** Before completing the move/addition, ensure the repository contains a `README.md` file. If missing, create a basic placeholder:
    ```markdown
    # [Repository Name]

    [Brief one-sentence description if possible, otherwise state purpose is unclear]

    Status: [Specify status if known, otherwise Unknown]
    Category: [Work/Personal/OpenSource/MCP/[SubCategory]]
    Last Updated: $(date +'%Y-%m-%d')
    ```
5.  **Confirm Action:** Report the final location and categorization to the user.
6.  **Update Root README:** After successfully adding, moving, or removing any repository or top-level category folder (`Work`, `Personal`, `OpenSource`, `MCP`), regenerate the directory tree in the root `/Projects/README.md` file. Use a command like `tree -L 3 -I '.git*|.DS_Store|node_modules|__pycache__|venv|.pytest_cache|build|dist' | cat` (adjust depth and exclusions as needed) and replace the content within the '```' block under the "Current Directory Structure" heading.

## Key Principles for AI Assistants

*   **Prioritize MCP:** Always check if a project is MCP-related *first*. This overrides the general categories.
*   **Use the Structure:** Do not create new top-level categories without explicit instruction.
*   **Read READMEs:** Use `README.md` files as the primary source for categorization clues.
*   **Ask if Unsure:** If categorization is ambiguous even after checking the README, place in `/Uncategorized/` and ask the user for clarification. Do not guess if unsure.
*   **Maintain READMEs:** Ensure every *repository* directory has at least a basic `README.md`.
*   **Report Clearly:** Summarize actions taken, including the final location of moved/added items. 
# Contributing Guide

Thank you for investing your time in contributing to the PIEAS Academic Resource Archive (PARA). This set of guidelines defines the "Rules of the Road" for maintaining a clean, professional codebase.

## 1. The Golden Rule
**`main` is Production.**
The code and files on the `main` branch must always be stable and accurate. We **never push directly to main**. All changes must pass through a Pull Request (PR) review.

## 2. Issue-Driven Development
We plan before we act.
1.  **Create an Issue:** If you want to add a lecture or fix a bug, write a "ticket" in the Issues tab first.
    * **Title:** Concise summary (e.g., "Add Semester 1 Calculus Past Papers").
    * **Description:** Clearly define what you are adding and why.
2.  **Link it:** When opening a PR, include `Closes #IssueNumber` in the description.

## 3. Git Workflow (Branching Strategy)
We use a simplified Feature Branch Workflow. Do not work on `main`.

**Step 1: Branching**
Name your branches based on the work type:
* `feature/` (e.g., `feature/add-cis-lectures`)
* `fix/` (e.g., `fix/typo-in-syllabus`)
* `docs/` (e.g., `docs/update-readme`)

**Step 2: Committing**
We write commit messages for machines, not just humans. Follow the **Conventional Commits** format:
`type(scope): description`

| Type | Meaning | Example |
| :--- | :--- | :--- |
| **feat** | New material/feature | `feat(sem1): add physics past papers` |
| **fix** | Bug/Error fix | `fix(meta): correct exclusion page numbers` |
| **docs** | Documentation | `docs: update contribution guide` |
| **chore** | Tooling/Config | `chore: update gitignore` |

**Step 3: The Pull Request**
1.  Push your branch: `git push origin feature/my-feature`
2.  Open a PR targeting `main`.
3.  Wait for a maintainer review.

## 4. File Standards
* **PDFs:** Must be clear and readable.
* **Code:** Must be commented.
* **Exclusions:** When marking a topic as "excluded" in `syllabus.json`, you must provide a reason (e.g., "Removed in Spring 2026"). 
> *See [Syllabus Metadata Standard](docs/SYLLABUS-METADATA.md) for full details.*
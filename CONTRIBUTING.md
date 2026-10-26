# Contributing Documentation Changes Through a GitHub Pull-Request Workflow

> **Portfolio sample.** The documentation team, its rules, and its style guide are fictional. The procedure was tested in VS Code and GitHub in October 2026, with one person acting as both author and reviewer.

| Field | Value |
| --- | --- |
| Document ID | DOC-SOP-001 |
| Version | 1.0 |
| Owner | Maintainer |
| Effective date | YYYY-MM-DD |
| Next review date | YYYY-MM-DD |

## 1. Purpose

This procedure describes how contributors propose changes to the documentation team's content, and how those changes are reviewed and published. Every change goes through a pull request: a reviewer from the documentation team checks and approves it before readers see it, and GitHub keeps a record of what changed, when, and why.

## 2. Audience

This procedure is for writers, subject-matter experts, and new team members who contribute to the documentation team's content. It assumes you can write and edit documentation and know basic Markdown, but have not used Git, GitHub, or VS Code to make documentation changes. Terms such as branch and maintainer are explained in [Key terms](#5-key-terms) and briefly where they first appear. You don't need to type Git commands: VS Code runs Git for you through its buttons, apart from two setup commands in [Prerequisites](#4-prerequisites).

## 3. Scope

### When to use this procedure

Use this procedure whenever you want to add, change, or remove content in the documentation repository.

### What this procedure covers

- Cloning the documentation repository to your computer (first time only).
- The cycle for each change: creating a branch, editing Markdown in VS Code, checking your work, adding a changelog entry for content changes, committing, publishing the branch, opening a pull request, and responding to review comments.
- After a reviewer merges your pull request: updating your local main branch and deleting your branch.
- The team's rules for branches, commit messages, pull requests, the changelog, and review.
- The author's steps. Reviewer and maintainer responsibilities are described in [Roles and responsibilities](#6-roles-and-responsibilities), not as steps.

### What it doesn't cover

- Installing tools (see [Prerequisites](#4-prerequisites)).
- Using Git from the command line (typing Git commands instead of using VS Code's buttons).
- Editing files in GitHub's browser editor. The team allows it only for typo fixes, which still need a pull request.
- Contributing from a fork (used by contributors without access to the repository).
- Resolving merge conflicts. If GitHub reports a conflict, stop and contact the maintainer.
- Signing commits. If your team requires signed commits, follow your onboarding instructions.
- macOS. The steps were tested on Windows.
- Writing style and content standards. Follow the team style guide.
- Publishing or building the documentation site.

## 4. Prerequisites

Before you start, make sure you have:

- A GitHub account, added to the documentation repository by the maintainer.
- The repository address, from the maintainer.
- VS Code installed ([code.visualstudio.com](https://code.visualstudio.com)).
- Git installed ([git-scm.com](https://git-scm.com)).
- Git configured with your name and your GitHub no-reply email address (see the note below).
- These VS Code extensions: markdownlint (David Anson) and Code Spell Checker (Street Side Software). The repository offers to install them when you open it. Check for the blue verified tick next to the publisher's name, so you install the real extension and not a fake one with a similar name (often called a copycat).
- Basic Markdown knowledge (see [Basic writing and formatting syntax](https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax) in GitHub's documentation).

> **Note: configure Git before your first commit.** Every commit records a name and an email address, and anyone who can see the repository can see them. To keep your personal email private, use the no-reply address shown in GitHub under **Settings > Emails**, with **Keep my email addresses private** turned on. In VS Code, open **Terminal > New Terminal** and run these two commands, with your own name and address:
>
> ```text
> git config --global user.name "Your Name"
> git config --global user.email "your-no-reply-address"
> ```

## 5. Key terms

| Term | Meaning |
| --- | --- |
| Branch | A separate line of work in the repository. main is one branch. You make each change on your own branch, so main isn't affected until your pull request is merged. |
| Clone | Copy a repository, with its full history, from GitHub to your computer. Your copy stays linked to GitHub, so you can sync changes, but it doesn't update by itself. |
| Commit | Save a set of staged changes to the history, with a message describing them. |
| Diff | A view of what changed in a file: removed lines in red, added lines in green. You see diffs in VS Code when you click a file in Source Control, and on GitHub on a pull request's **Files changed** tab. |
| main | The branch that holds the official version of the documentation. Nobody edits main directly: every change comes from another branch, through a pull request. |
| Maintainer | The member of the documentation team who manages the repository: gives contributors access, resolves problems such as merge conflicts, and owns this procedure. |
| Merge | Add the changes from a branch into main. In this procedure, the reviewer merges your pull request on GitHub. |
| origin | Git's name for the copy of the repository on GitHub. In VS Code's branch list, `origin/main` is main as it is on GitHub, and plain `main` is your copy on your computer. |
| Publish | Push a new branch to GitHub for the first time. In VS Code, this is the **Publish Branch** button. |
| Pull request | A request, made on GitHub, to merge your branch into main. Reviewers read and comment on the changes there. |
| Push | Send your commits from your computer to GitHub. |
| Repository (repo) | The folder of documentation files, together with the full history of every change. |
| Stage | Mark changes for the next commit. Staged files wait under **Staged Changes** in Source Control until you commit them. Changes you don't stage stay out of that commit. |
| Sync | Download any new changes from GitHub to your computer, then send your commits to GitHub. In VS Code, this is the **Sync Changes** button, or the sync icon next to the branch name in the bottom-left corner. |

## 6. Roles and responsibilities

| Role | Responsibilities |
| --- | --- |
| Author | Follows this procedure: makes the change on a branch, checks it, opens a pull request, and responds to review comments. |
| Reviewer | A member of the documentation team. Reviews the pull request within two working days, comments, approves, and merges. Asks for a subject-matter expert (SME) review when a change affects technical accuracy. Deletes the branch on GitHub after merging. |
| Maintainer | Owns the repository. Gives contributors access, resolves merge conflicts, and handles escalations. Owns this SOP and reviews it by the next review date. |
| SME reviewer | When asked, checks a change for technical accuracy and comments on the pull request. |

## 7. Team rules

| Rule | What the team does |
| --- | --- |
| Approval | One approval from the documentation team before merging. The reviewer can ask for an SME review. |
| Merging | The reviewer merges, after approving. Authors don't merge their own pull requests. |
| Branch names | Lowercase with hyphens, describing the change, for example `update-login-steps`. Add a ticket number if the change has one, for example `docs-142-update-login-steps`. |
| Commit messages | Follow the commit message rules below. |
| Pull request description | Complete every section of the pull request template: What changed, Why, Notes for the reviewer, and Checks (tick boxes for the checks in B4 and the changelog entry in B5). |
| Changelog | Content changes get an entry in `CHANGELOG.md`. Typo fixes and housekeeping changes don't. |
| Review time | The reviewer responds within two working days. |
| Stalled review | Mention the reviewer on the pull request, then ask in the team channel, then contact the maintainer. |
| Unresolved comments | The reviewer doesn't merge while any review comment is unresolved. The author resolves each line comment once it's addressed. |
| Skipping review | Never. Every change goes through a pull request and review, even a typo fix made in GitHub's browser editor. |

### Commit message rules

1. Start with a verb in command form, such as Add, Fix, Update, Remove, Rename, or Revert.
2. Name the page or file, so the change can be found in the history later.
3. Say what changed, not just that something was fixed. Use Fix for errors such as typos and broken links.
4. Keep it to about 50 characters, with no full stop at the end.
5. Capitalize only the first word and proper names. Put extra detail in the pull request description.

These examples show the rules in practice. The page names are illustrations, not pages in this repository.

| Too vague or too long | Better |
| --- | --- |
| Add page about resetting passwords | `Add Reset Your Password page` |
| Update steps because the login screen changed | `Update login steps in Getting Started` |
| Fix headers on all pages | `Use sentence case for headings on all pages` |
| Revert commit that deleted the Getting Started introduction | `Revert removal of Getting Started introduction` |

Write your own commit messages. Don't use the AI suggestion (the sparkle icon) in the commit message box.

## 8. Environment and tools used

The steps were tested with these tools and versions. Menus and labels can change in later versions.

| Tool | Tested with |
| --- | --- |
| Windows | Windows 11, version 25H2 |
| VS Code | 1.142.0 and 1.143.0 |
| Git | 2.56.0.windows.2 |
| markdownlint extension | 0.62.1 |
| Code Spell Checker extension | 4.10.0 |
| GitHub | Web interface, October 2026 |
| Mermaid | Built in to GitHub and VS Code's Markdown preview |

## 9. Workflow overview

```mermaid
flowchart TD
    A([Start]) --> B[Clone repository - first time only]
    B --> C[Update main and create a branch]
    C --> D[Edit Markdown in VS Code]
    D --> E[Check preview, markdownlint, and spelling]
    E --> F{Checks pass?}
    F -- No --> D
    F -- Yes --> P{Content change?}
    P -- Yes --> O[Add changelog entry]
    P -- No --> G[Commit and publish branch]
    O --> G
    G --> H[Open pull request]
    H --> I{Review approved?}
    I -- No --> J[Make changes, check, commit, and sync]
    J --> I
    I -- Yes --> K[Reviewer merges pull request]
    K --> L[Sync local main]
    L --> M[Delete local branch]
    M --> N([Complete])

    classDef endpoint fill:#ffffff,stroke:#57606a,stroke-width:2px,color:#1f2328
    classDef local fill:#ddf4ff,stroke:#0969da,stroke-width:1.5px,color:#1f2328
    classDef remote fill:#dafbe1,stroke:#1a7f37,stroke-width:1.5px,color:#1f2328
    classDef decision fill:#fff8c5,stroke:#9a6700,stroke-width:1.5px,color:#1f2328
    class A,N endpoint
    class B,C,D,E,O,G,J,L,M local
    class H,K remote
    class F,P,I decision
```

In the diagram, blue boxes are steps in VS Code on your computer, green boxes are steps on GitHub, yellow diamonds are decisions, and white ovals mark the start and the end.

The two loops are where most of the work happens: fixing problems before you commit, and responding to review before the merge.

## 10. Procedure

### A. One-time setup: clone the repository

Do this once on each computer you use, before your first change.

> **Warning:** clone into a plain local folder, such as `C:\Users\<your-name>\GitHub`. Don't clone into OneDrive or another synced folder: syncing can interfere with Git's files.

1. On GitHub, open the repository, click the green **Code** button, make sure **HTTPS** is selected, and click the copy icon next to the address. Copy the address first: the clone box in VS Code closes if you click away from it.
2. In VS Code, if a folder is already open, click **File > Close Folder**. The Welcome page appears.
3. On the Welcome page, click **Clone Git Repository**, paste the address into the box at the top, and press **Enter**.
4. In the window that opens, go to your local folder (for example `GitHub`), and click **Select as Repository Destination**. Don't select a folder inside it: VS Code creates the repository's folder for you. If a window asks you to sign in to GitHub, follow its steps. If it opens your browser, check that the address bar says **github.com**, then approve it.
5. When VS Code asks whether to open the cloned repository, click **Open**.
6. If VS Code asks whether you trust the authors of the files, click **Yes, I trust the authors**. If a blue **Restricted Mode** label appears in the bottom-left corner instead, click it. On the **Workspace Trust** page that opens, click **Trust**. Don't click **Add Folder** at the bottom of the page. It's for adding more folders to your trusted list.

**Result:** the Explorer shows the repository's name and files, and the bottom-left corner of VS Code shows **main**.

![VS Code after cloning: the Explorer shows the repository and its README file, and the bottom-left corner shows main](images/clone-result.png)

### B. Make a change

#### B1. Start from an up-to-date main

1. Check that the bottom-left corner shows **main**, with no asterisk. If it shows another branch, click it and choose **main** from the list (plain `main`, not `origin/main`).
2. Click the **Source Control** icon. Check that the Changes list is empty.
3. Click the sync icon (two circular arrows) next to **main** in the bottom-left corner, to download the latest changes from GitHub. If VS Code asks you to confirm, click **OK**.

**Result:** main on your computer matches main on GitHub, and Source Control shows no changes.

#### B2. Create a branch

1. Click **main** in the bottom-left corner. A box opens at the top of the window.
2. Click **Create new branch**.
3. Type a branch name that follows the team rules, for example `update-login-steps`, and press **Enter**.

**Result:** the bottom-left corner shows your branch name.

#### B3. Edit and save

> **Warning:** never add confidential information to the repository. Anyone with access can see every file and commit, and the history is permanent: deleting a file later doesn't remove it from earlier commits. If this happens, see [Escalation](#12-escalation).

1. Open the file you want to change from the Explorer. To create a new file, right-click the folder it belongs in and choose **New File**. For a file at the top level, click a top-level file such as `README.md`, then point at the repository name at the top of the Explorer and click the **New File** icon (a page with **+**). Type the name, ending in `.md`, in the box that appears, and press **Enter**. To delete a file, right-click it, choose **Delete**, then **Move to Recycle Bin**. Leave **Do not ask me again** unticked, so VS Code keeps asking before it deletes a file.
2. Make your change, then press **Ctrl + S** to save.

> **Tip:** a white dot on a file's tab means unsaved changes. When you're editing a long line that wraps onto several lines, press **End** twice before **Enter**: the first press stops at the end of the screen line, and the second goes to the true end of the line. Pressing **Enter** in the middle splits the line, which can break a table row.

**Result:** the tab shows no white dot, and the file shows **M** (modified) or **U** (new) in the Explorer. A deleted file disappears from the Explorer and shows **D** in Source Control.

#### B4. Check your work

1. Press **Ctrl + K**, then **V**, to open the preview beside the file. Check that headings, lists, tables, links, and diagrams display as intended.
2. Press **Ctrl + Shift + M** to open the **Problems** panel. Fix every markdownlint warning, and every spelling notice that is a real typo. Each markdownlint warning names a rule, such as MD022: click the rule code to open its documentation with examples. For some rules, **Ctrl + .** offers an automatic fix; check the result in the preview.
3. For a correct word the spell checker doesn't know, such as a product name, click the light bulb next to the notice and choose the option that adds the word to **User Settings**. Don't choose Workspace Settings: that creates a settings file in the repository.

> **Note:** markdownlint and the spell checker don't check everything. A table whose separator row has the wrong number of columns displays as plain text, and markdownlint doesn't flag it. JSON inside a code block isn't checked either. The spell checker skips words shorter than four letters, such as "teh", and doesn't flag real words used in the wrong place, such as "type" for "typo". Read your change in the preview before you commit.

**Result:** the preview looks right, and the Problems panel shows no problems.

#### B5. Add a changelog entry (content changes only)

If your change affects the content, accuracy, or structure of the documentation (a new page, a removed page, a corrected example, updated wording), add an entry to `CHANGELOG.md`. Skip this step for typo fixes and housekeeping.

1. Open `CHANGELOG.md`.
2. Below the introduction, add a heading with today's date, followed by one bullet per change. Newest entries go at the top:

   ```markdown
   ## 2026-10-19

   - Updated the login steps on the Getting Started page
   ```

3. Save the file.

**Result:** the new entry is the first entry in the changelog.

#### B6. Stage and commit

1. Click the **Source Control** icon. If you only see the Graph, click the arrow next to **Changes** to expand it.
2. Check that VS Code's title bar shows the documentation repository, that no tab shows a white dot, and that the Changes list holds only the files for this change. Changes you haven't saved aren't included in the commit.
3. Click each file in the Changes list to see exactly what you changed. Check that every change is one you meant to make.
4. Stage the files: point at each file and click its **+** (**Stage Changes**), or point at the **Changes** line and click its **+** (**Stage All Changes**). Don't click the curved arrow beside it: it discards your changes. The files move under **Staged Changes**.
5. In the message box, write a commit message that follows the team rules.
6. Click **Commit**.

> **Note:** if VS Code says "There are no staged changes to commit", click **Cancel**, stage the files, and commit again. Staging everything automatically can include changes you didn't mean to commit. Check the commit message before you click **Commit**: once it's pushed, it can't be changed.

Before you click **Commit**, Source Control looks like this:

![Source Control panel with a commit message in the message box and README.md under Staged Changes](images/staged-changes.png)

**Result:** the Changes list is empty, and your commit appears at the top of the Graph.

#### B7. Publish the branch

1. The first time you push a new branch, click **Publish Branch**. For later commits on the same branch, click **Sync Changes** instead.
2. If this is your first push and a window asks you to sign in to GitHub, follow its steps. If it opens your browser, check that the address bar says **github.com**, then approve it. GitHub may ask for your password again; that's expected. The page then goes blank; close it.

**Result:** the bottom-left corner shows your branch name with a sync icon instead of a cloud icon, and in the Graph, your branch label has a cloud icon beside it, meaning it's also on GitHub.

> **Tip:** in the Graph, a label with a cloud icon shows where the branch is on GitHub. When it's on the same commit as your branch, GitHub has all your commits.

#### B8. Open a pull request and request a review

1. On GitHub, open the repository and refresh the page. A banner says your branch had recent pushes. Click **Compare & pull request**.
2. Check the top of the page shows **base: main** and **compare:** your branch.
3. Keep or edit the title. It usually matches your commit message.
4. Fill in the description. The box already holds the team's pull request template: four headings (**What changed**, **Why**, **Notes for the reviewer**, and **Checks**), each with a short hint between `<!--` and `-->`. The hints are instructions for you, and they don't appear in the finished pull request. Write your answer under each heading.
5. Under **Checks**, there's a list of the checks from B4 and B5, each starting with `- [ ]`. For each check you completed, type an `x` between the brackets, with no spaces: `- [x]`. Leave checks that don't apply as `- [ ]`, for example the changelog check for a typo fix.
6. Click the **Preview** tab to check the description.
7. Click **Create pull request**.
8. On the right of the pull request, click **Reviewers** and choose a reviewer from the documentation team.

The banner in step 1 looks like this:

![GitHub repository page with a banner saying the branch had recent pushes, and a Compare & pull request button](images/compare-pull-request-banner.png)

**Result:** the pull request shows a green **Open** label and the reviewer's name under **Reviewers**.

### C. Respond to review

#### C1. Read the review comments

GitHub notifies you when the reviewer comments. Open the pull request and read each comment, on the **Conversation** tab and next to the lines on **Files changed**.

#### C2. Make the requested changes

1. In VS Code, check that the bottom-left corner shows your branch, not main.
2. Make the changes, then check your work (B4), stage and commit (B6), and click **Sync Changes**.

Your new commits are added to the same pull request automatically. Don't open a new one.

#### C3. Reply and resolve

1. On GitHub, reply to each comment, saying what you changed, or why you didn't.
2. Under each comment on a line in **Files changed** that you've addressed, click **Resolve conversation**. General comments on the **Conversation** tab can't be resolved: a reply is enough.

The reviewer then approves and merges, or adds more comments. Repeat C1 to C3 until the pull request is approved.

#### C4. If the review stalls

If the reviewer hasn't responded within two working days:

1. Mention the reviewer in a comment on the pull request, for example `@reviewer-name`.
2. If there's still no response after another working day, ask in the team channel.
3. If that doesn't help, contact the maintainer.

### D. After the merge

#### D1. Update your local main

1. In VS Code, click your branch name in the bottom-left corner and choose **main**. Until you sync, the files show the old version, and new files may seem to be missing.
2. Click the sync icon (two circular arrows) next to **main** in the bottom-left corner. If VS Code asks you to confirm, click **OK**.

**Result:** in the Graph, the **main** label sits on the top line, next to the merge commit, with a cloud icon beside it. The files show the merged version.

#### D2. Delete your local branch

1. Press **Ctrl + Shift + P** to open the Command Palette. Keep the `>` at the start of the box: without it, the box searches file names instead of running commands.
2. Type `Git: Delete Branch` and choose it.
3. Choose your branch from the list.

If VS Code warns that the branch isn't fully merged, the branch has commits that aren't on GitHub. Stop and contact the maintainer. Don't force the deletion.

**Result:** your branch no longer appears in the branch list.

## 11. Troubleshooting

### In VS Code

| Problem | Cause | Fix |
| --- | --- | --- |
| Source Control shows **Initialize Repository** and **Publish to GitHub** | The open folder doesn't have a Git repository | Don't click either. If you've already cloned the repository, open its folder with **File > Open Recent**. If not, click **File > Close Folder**, then clone it (part A). |
| The clone box closed before you pasted the address | You clicked away from the box | Copy the address on GitHub first, then click **Clone Git Repository** again. |
| A blue **Restricted Mode** label appears in the bottom-left corner | VS Code doesn't trust the folder yet | Click the label. On the **Workspace Trust** page that opens, click **Trust**. Don't click **Add Folder** at the bottom of the page. Trust only your team's repositories. |
| The bottom-left corner shows **main\*** (with an asterisk) | You changed files on main before creating a branch | Click **main\***, then **Create new branch**. Your changes come with you to the new branch. |
| A tab you didn't expect shows a white dot | The tab holds unsaved edits | If you're not sure what they are, close the tab and click **Don't Save**. If you already saved them, open the file in Source Control to see the changes, and choose **Discard Changes** to restore the committed version. |
| You deleted a file by mistake | The file was deleted in the Explorer | In Source Control, point at the file (marked **D**), click **Discard Changes**, then **Restore File**. |
| A table displays as plain text | The separator row has a different number of columns from the header | Give the separator row one `---` cell per column, so it matches the header. Check the preview. |
| A table row is split across two lines | **Enter** was pressed in the middle of a wrapped line | Join the lines again. On long lines, press **End** twice before **Enter**. |
| Text displays as raw code | A code block is missing its closing fence | Add three backticks on their own line where the code block should end. |
| Part of a page is missing from the preview | An HTML comment (`<!--`) was never closed | Find the `<!--` above the missing part and add `-->` where the comment should end. |
| Headings or paragraphs display as code or don't format after pasting | Pasted text brought hidden spaces at the start of lines | Select the lines and press **Shift + Tab** until they start at the left edge. If a line doesn't move, click just before its first word and press **Backspace** until it does. |
| A correct word is underlined as a spelling mistake | The word isn't in the spell checker's dictionary | Click the light bulb and choose the option that adds the word to **User Settings**. Don't choose Workspace Settings: that creates a settings file in the repository. |
| "There are no staged changes to commit" | The staging step was skipped | Click **Cancel**, stage the files, then commit. Don't click **Always**: VS Code then commits all your changes without asking whenever nothing is staged. |
| The Command Palette shows file names or **No matching results** instead of commands | The `>` at the start of the box is missing | Type `>` at the start, or press **Ctrl + Shift + P** again. |

### On GitHub

| Problem | Cause | Fix |
| --- | --- | --- |
| The **Compare & pull request** banner doesn't appear | The banner only appears for a short time after a push, and not if a pull request is already open for the branch | On GitHub, open the repository and click **Pull requests**, then **New pull request**. Set **base** to **main** and **compare** to your branch. Click **Create pull request** to open the form, then continue from B8 step 3. |
| GitHub says **There isn't anything to compare** | The branch in **compare** has no changes that aren't already on main: it's already merged, it's the wrong branch, or your commits haven't reached GitHub | Check that **compare** shows your branch. Then, in VS Code, check your commits are published: the bottom-left corner shows a sync icon, not a cloud icon (B7). |
| The pull request banner appears on the wrong repository | The commit was made in another repository's folder | Don't open a pull request. Contact the maintainer. Next time, check the title bar before committing. |
| Your commits on GitHub have no **Verified** badge | Commits made on your computer aren't signed | Nothing is wrong. Signing commits isn't covered by this procedure; follow your onboarding instructions if your team requires it. |

## 12. Escalation

| Situation | Contact | Include |
| --- | --- | --- |
| **On GitHub:** the pull request reports a merge conflict | Maintainer | The pull request link and the files named in the conflict |
| **On GitHub:** no review after two working days | Reviewer, then the team channel, then the maintainer (see C4) | The pull request link |
| **On GitHub:** you and the reviewer can't agree on a requested change | Maintainer, after you've replied to the comment with your reasons (C3) | The pull request link and the comment you disagree about |
| **In VS Code or on GitHub:** you can't clone, push, or see the repository | Maintainer | Your GitHub username and the repository name |
| **In VS Code:** an error message appears when you publish or sync | Maintainer | A screenshot of the message (press **Windows + PrtScn** before you click anything), and your branch name |
| **In VS Code or on GitHub:** you committed on main, or published to the wrong repository | Maintainer | The repository name, the branch name, and what you committed |
| **In VS Code:** a warning says a branch isn't fully merged | Maintainer | The branch name and the warning text |
| **Any time:** a step in this procedure doesn't match what you see, or seems wrong | Maintainer | The step number (for example, B6 step 3), what you expected, what you saw, and a screenshot |
| **Any time:** you added confidential information (such as a password, a key, or personal data) to a commit | Maintainer, straight away. Don't publish or sync until they reply. | The repository name, the branch name, and the file name. Don't copy the confidential information into your message. |
| **Any time:** a question this procedure doesn't answer | Reviewer or maintainer | What you were doing and what you saw |

## 13. Completion criteria

The procedure is complete when:

- The pull request description has every section of the template completed, with the Checks ticked.
- The pull request is approved and merged, with every line comment resolved.
- For a content change, the merged pull request includes a `CHANGELOG.md` entry.
- Your branch is deleted on GitHub, and you've deleted your local branch (D2).
- Your local main is up to date with GitHub: the bottom-left corner shows **main** with no asterisk, and Source Control shows no changes.

## 14. Records

| Record | Where it's kept |
| --- | --- |
| The change, its description, the review, and the approval | The pull request on GitHub |
| Every commit, with author, date, and exact changes | The repository's commit history |
| Content changes, newest first | `CHANGELOG.md` |
| Versions of this procedure | [Revision history](#16-revision-history), at the end of this document |

GitHub keeps pull requests and commit history automatically, for as long as the repository exists. Apart from the changelog entry (B5), you don't need to keep any other record of your change.

## 15. Related documents

- Documentation team style guide (internal)
- [Pull request template](.github/pull_request_template.md), in this repository
- [CHANGELOG.md](CHANGELOG.md), in this repository
- [About pull requests](https://docs.github.com/en/pull-requests/get-started/about-pull-requests), GitHub documentation
- [Creating a pull request](https://docs.github.com/en/pull-requests/how-tos/create-pull-requests/creating-a-pull-request), GitHub documentation
- [Setting your commit email address](https://docs.github.com/en/account-and-profile/how-tos/email-preferences/setting-your-commit-email-address), GitHub documentation
- [Basic writing and formatting syntax](https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax), GitHub documentation
- [Source control in VS Code](https://code.visualstudio.com/docs/sourcecontrol/overview), VS Code documentation
- [Working with repositories and remotes](https://code.visualstudio.com/docs/sourcecontrol/repos-remotes), VS Code documentation
- [Workspace Trust](https://code.visualstudio.com/docs/editing/workspaces/workspace-trust), VS Code documentation
- [markdownlint rules](https://github.com/DavidAnson/markdownlint/blob/main/doc/Rules.md), markdownlint documentation

## 16. Revision history

| Version | Date | Author | Changes |
| --- | --- | --- | --- |
| 1.0 | YYYY-MM-DD | Georgia Lainiotis | First version. Drafted and tested in October 2026, and revised after a full review before approval. |

© 2026 Georgia Lainiotis. All rights reserved.

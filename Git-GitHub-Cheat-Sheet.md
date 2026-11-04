# Git & GitHub Cheat Sheet

> A beginner-friendly, practical reference to the most commonly used Git and GitHub commands — from creating your first repository to collaborating with a team.

![Git](https://img.shields.io/badge/Git-Version%20Control-orange?logo=git)
![GitHub](https://img.shields.io/badge/GitHub-Code%20Hosting-black?logo=github)
![Level](https://img.shields.io/badge/Level-Beginner%20to%20Intermediate-brightgreen)

---

## Table of Contents

1. [Git vs GitHub](#1-git-vs-github)
2. [Understand the Git Workflow](#2-understand-the-git-workflow)
3. [Installation and Initial Setup](#3-installation-and-initial-setup)
4. [Create or Download a Repository](#4-create-or-download-a-repository)
5. [Stage and Commit Changes](#5-stage-and-commit-changes)
6. [Connect and Sync with GitHub](#6-connect-and-sync-with-github)
7. [Branching and Merging](#7-branching-and-merging)
8. [Inspect and Compare History](#8-inspect-and-compare-history)
9. [Undo and Recover Changes](#9-undo-and-recover-changes)
10. [Temporarily Save Work with Stash](#10-temporarily-save-work-with-stash)
11. [Track, Move and Remove Files](#11-track-move-and-remove-files)
12. [Ignore Files with `.gitignore`](#12-ignore-files-with-gitignore)
13. [GitHub Collaboration Commands](#13-github-collaboration-commands)
14. [Common Git and GitHub Terms](#14-common-git-and-github-terms)
15. [Common Errors and Troubleshooting](#15-common-errors-and-troubleshooting)
16. [Complete Git Workflow](#16-complete-git-workflow)
17. [20 Commands to Remember](#17-20-commands-to-remember)
18. [Useful Learning Resources](#18-useful-learning-resources)

---

## 1. Git vs GitHub

| Git | GitHub |
|---|---|
| A distributed version control system | An online platform for hosting Git repositories |
| Installed and used on your computer | Accessed through a website or its tools |
| Tracks changes and saves project history | Helps share code and collaborate with others |
| Works locally without an internet connection for most operations | Provides remote storage, pull requests, issues and collaboration tools |

**In simple words:** Git manages version history. GitHub hosts and shares Git repositories.

## 2. Understand the Git Workflow

Git uses three important local areas:

1. **Working Directory:** Where you create, edit or delete project files.
2. **Staging Area:** Where you select changes to include in your next commit.
3. **Local Repository:** Where Git stores committed snapshots and history.

A typical workflow:

```text
Working Directory
       |
       | git add
       v
  Staging Area
       |
       | git commit
       v
 Local Repository
       |
       | git push
       v
Remote Repository (GitHub)
```

The four commands to remember:

| Command | Purpose |
|---|---|
| `git status` | Check the current state of your files |
| `git add` | Stage changes |
| `git commit` | Save a snapshot locally |
| `git push` | Upload commits to GitHub |

## 3. Installation and Initial Setup

Download Git: https://git-scm.com/downloads

Check whether Git is installed:

```bash
git --version
```

Configure your identity (usually done once):

```bash
git config --global user.name "Your Name"
git config --global user.email "your-email@example.com"
```

Enable colored output:

```bash
git config --global color.ui auto
```

View your configuration:

```bash
git config --list
```

Configuration scopes:

| Option | Meaning |
|---|---|
| `--global` | Applies to your user account across repositories |
| `--local` | Applies only to the current repository |
| `--system` | Applies system-wide |

## 4. Create or Download a Repository

| Command | What it does |
|---|---|
| `git init` | Initialize Git in the current directory |
| `git clone <url>` | Download an existing repository |
| `git clone <url> <folder>` | Clone into a folder with a chosen name |

Examples:

```bash
# Initialize a repository in the current folder
git init

# Clone a GitHub repository
git clone https://github.com/username/repository.git

# Clone into a specific folder
git clone https://github.com/username/repository.git Demo1
```

**Remember:** `git init` creates a new local repository. `git clone` downloads an existing repository and configures its remote connection.

## 5. Stage and Commit Changes

These commands help prepare changes and save them in Git history.

| Command | Explanation |
|---|---|
| `git status` | Show modified, staged and untracked files |
| `git add <file>` | Stage a particular file |
| `git add .` | Stage changes in the current directory |
| `git add -A` | Stage all changes across the repository |
| `git reset <file>` | Unstage a file without deleting its changes |
| `git diff` | Show unstaged changes |
| `git diff --staged` | Show staged changes |
| `git commit -m "message"` | Commit staged changes |
| `git commit -am "message"` | Stage and commit modified tracked files |
| `git commit --amend` | Modify the most recent commit |

Example:

```bash
# Check current changes
git status

# Stage a file
git add index.html

# Review staged changes
git diff --staged

# Commit changes
git commit -m "Added index page"

# Verify
git status
```

Important notes:

- `git add` does not upload files to GitHub.
- `git commit` saves changes locally; it does not push them to GitHub.
- `git commit -am` does not automatically include new, untracked files.
- A commit is a snapshot of the staged content, not necessarily every file in your project.

## 6. Connect and Sync with GitHub

A **remote** is a connection to another repository, commonly hosted on GitHub. `origin` is the conventional name for the default remote.

| Command | Explanation |
|---|---|
| `git remote -v` | View configured remote URLs |
| `git remote add origin <url>` | Connect local repository to GitHub |
| `git remote remove origin` | Remove the remote named `origin` |
| `git remote rename origin upstream` | Rename a remote |
| `git fetch origin` | Download remote updates without integrating them |
| `git pull origin main` | Fetch and integrate changes from remote `main` |
| `git push origin main` | Push local `main` commits to remote `main` |
| `git push -u origin main` | Push and set upstream tracking |
| `git push` | Push to the configured upstream branch |

### Fetch vs Pull vs Push

| Command | What happens |
|---|---|
| `git fetch` | Downloads remote updates but does not integrate them into your current branch |
| `git pull` | Fetches and integrates remote changes into your current branch |
| `git push` | Uploads your local commits to the remote repository |

### Connect a local project to GitHub

Create an empty repository on GitHub, then run these commands in your project folder:

```bash
# Add your GitHub repository URL
git remote add origin https://github.com/username/Demo1.git

# Verify the remote
git remote -v

# Rename the current branch to main
git branch -M main

# Push for the first time and set upstream
git push -u origin main
```

After the upstream is configured, you can usually use:

```bash
git push
```

If the remote repository already contains commits (for example, a README created on GitHub), you may need to fetch and integrate those changes before pushing.

## 7. Branching and Merging

Branches let you work on features or bug fixes separately from the main development line.

| Command | Explanation |
|---|---|
| `git branch` | List local branches |
| `git branch -a` | List local and remote-tracking branches |
| `git branch <name>` | Create a branch |
| `git switch <branch>` | Switch to an existing branch |
| `git switch -c <name>` | Create and switch to a new branch |
| `git checkout <branch>` | Switch branches (older command, still supported) |
| `git checkout -b <name>` | Create and switch branches |
| `git branch -d <name>` | Delete a merged local branch |
| `git branch -D <name>` | Force-delete a local branch |
| `git branch -m <new-name>` | Rename the current branch |
| `git merge <branch>` | Merge the named branch into the current branch |

### Practical branching example

```bash
# Create and switch to a feature branch
git switch -c feature-login

# Make changes, then stage and commit
git add .
git commit -m "Added login feature"

# Switch back to main
git switch main

# Merge feature branch into main
git merge feature-login

# Push the updated main branch
git push origin main
```

A simplified view:

```text
main:     A ----- B -------- M
                   \        /
feature:            C ---- D
```

The feature branch contains separate commits (`C` and `D`). The merge commit (`M`) brings the work into `main`.

## 8. Inspect and Compare History

| Command | Explanation |
|---|---|
| `git log` | Show commit history |
| `git log --oneline` | Show compact commit history |
| `git log --oneline --graph --all` | Visualize commit and branch history |
| `git log -5` | Show the latest five commits |
| `git show <SHA>` | Show details of a commit |
| `git diff` | Compare working changes |
| `git diff --staged` | Compare staged changes |
| `git diff main..feature` | Compare the two branch tips |
| `git diff main...feature` | Compare feature changes since the common ancestor with `main` |
| `git log main..feature` | Show commits in `feature` that are not in `main` |
| `git log --follow -- <file>` | Track a file's history, including renames |
| `git log --stat` | Show commits with file-change statistics |

Example:

```bash
git log --oneline
```

Example output:

```text
9a262a5 Added index page
7b123c4 Created README
3a567d8 Initial commit
```

A commit hash (SHA) identifies a commit.

## 9. Undo and Recover Changes

Be careful: some commands can permanently discard local work.

| Command | Explanation |
|---|---|
| `git restore <file>` | Discard unstaged changes in a file |
| `git restore --staged <file>` | Unstage a file while preserving its changes |
| `git revert <SHA>` | Create a new commit that reverses an earlier commit |
| `git reset --soft HEAD~1` | Move branch back one commit; keep changes staged |
| `git reset --mixed HEAD~1` | Move branch back one commit; keep changes unstaged |
| `git reset --hard HEAD~1` | Move branch back one commit and discard associated tracked changes |
| `git reflog` | View recent movements of HEAD and branch references |

### Understand the reset options

| Command | What happens to changes from the undone commit? |
|---|---|
| `--soft` | Kept staged |
| `--mixed` | Kept unstaged |
| `--hard` | Discarded from the working tree and staging area |

Examples:

```bash
# Undo the last commit but keep changes staged
git reset --soft HEAD~1

# Undo the last commit and keep changes unstaged
git reset --mixed HEAD~1

# DANGEROUS: discard associated tracked changes
git reset --hard HEAD~1
```

**Important:**

- Avoid `git reset --hard` if you have work you have not backed up.
- Avoid rewriting commits that teammates may already have pulled.
- Prefer `git revert` when undoing a commit that has already been shared.

## 10. Temporarily Save Work with Stash

Use `git stash` when you need to switch branches but are not ready to commit your current changes.

| Command | Explanation |
|---|---|
| `git stash` | Temporarily save tracked changes |
| `git stash -u` | Save tracked and untracked files |
| `git stash list` | List saved stashes |
| `git stash show` | Show a summary of the latest stash |
| `git stash apply` | Restore the latest stash and keep it in the list |
| `git stash pop` | Restore the latest stash and remove it if successful |
| `git stash drop` | Delete the latest stash |
| `git stash clear` | Delete all stashes |

Example:

```bash
# Save unfinished work
git stash

# Switch branch
git switch main

# Return to the feature branch
git switch feature-login

# Restore unfinished work
git stash pop
```

## 11. Track, Move and Remove Files

| Command | Explanation |
|---|---|
| `git rm <file>` | Remove a file and stage its deletion |
| `git rm --cached <file>` | Stop tracking a file but keep it locally |
| `git mv <old> <new>` | Move or rename a tracked file |
| `git status` | Check file changes |
| `git diff --summary` | Show change summaries |

Examples:

```bash
# Remove a file from the project and stage its deletion
git rm old.html

# Rename a file
git mv index.html home.html

# Stop tracking a file but keep it on your computer
git rm --cached config.txt
```

## 12. Ignore Files with `.gitignore`

A `.gitignore` file tells Git which untracked files and directories it should ignore.

Create a file named `.gitignore` in your repository.

Example:

```gitignore
# Log files
*.log
logs/

# Environment variables and secrets
.env
.env.*
!.env.example

# Python
__pycache__/
*.pyc
venv/

# Node.js
node_modules/

# Build files
dist/
build/

# IDE settings
.vscode/
.idea/

# Operating system files
.DS_Store
Thumbs.db
```

Useful commands:

```bash
# Show ignored files too
git status --ignored

# Check why a file is ignored
git check-ignore -v .env
```

**Important:** `.gitignore` does not stop tracking files that were already committed. To stop tracking a file while keeping it locally:

```bash
git rm --cached .env
git commit -m "Stop tracking environment file"
```

Never commit passwords, API keys, AWS access keys, private SSH keys or other secrets. If a secret has already been pushed, revoke or rotate it; deleting the file alone does not make the secret safe.

## 13. GitHub Collaboration Commands

These commands are useful when working with a team.

| Command | Explanation |
|---|---|
| `git fetch --all` | Fetch updates from all configured remotes |
| `git pull --rebase` | Fetch and replay local commits on top of updated remote history |
| `git push origin <branch>` | Push a branch to GitHub |
| `git push -u origin <branch>` | Push and configure upstream |
| `git push origin --delete <branch>` | Delete a remote branch |
| `git cherry-pick <SHA>` | Apply a specific commit to the current branch |
| `git remote show origin` | Show information about a remote |

### Typical team workflow

```bash
# Get the latest changes from main
git pull origin main

# Create a feature branch
git switch -c feature-payment

# Make changes
git add .
git commit -m "Added payment feature"

# Push your feature branch
git push -u origin feature-payment
```

Then open GitHub and create a **Pull Request (PR)** to merge `feature-payment` into `main`.

A Pull Request lets teammates review, discuss and approve changes before they are merged.

## 14. Common Git and GitHub Terms

| Term | Simple meaning |
|---|---|
| Repository (repo) | Project tracked by Git |
| Local repository | Repository on your computer |
| Remote repository | Repository hosted on GitHub or another server |
| Commit | Saved snapshot of changes |
| Branch | Separate line of development |
| `main` | Common name for the primary branch |
| `origin` | Conventional name for the default remote |
| HEAD | Reference to the current checkout/commit |
| Staging area | Place where changes are prepared for a commit |
| Merge | Combine changes from branches |
| Merge conflict | Git cannot automatically combine some changes |
| Pull Request | Request to review and merge code |
| Fork | Your own GitHub copy of another repository |
| Clone | Download a repository to your computer |
| Fetch | Download remote updates without integrating them |
| Pull | Fetch and integrate remote changes |
| Push | Upload local commits |
| README | File explaining a project |
| `.gitignore` | Rules for excluding untracked files |

## 15. Common Errors and Troubleshooting

| Error or situation | What to check / do |
|---|---|
| `fatal: not a git repository` | Navigate to the correct folder or run `git init` |
| `Author identity unknown` | Configure `user.name` and `user.email` |
| `nothing to commit` | Check whether there are new changes to commit |
| `Your branch is ahead by 1 commit` | Check your remote and push the unpushed commit |
| `rejected (fetch first)` | Fetch and integrate remote changes, resolve conflicts, then push |
| `Permission denied (publickey)` | Check your SSH key and GitHub SSH configuration |
| `Authentication failed` | Check GitHub authentication or saved credentials |
| `src refspec main does not match any` | Check the branch name and whether a commit exists |
| `CONFLICT (content)` | Open the conflicted files, resolve the changes, then stage and continue |

### Troubleshooting a push that does not work

If Git says:

```text
Your branch is ahead of 'origin/main' by 1 commit.
```

Git believes your local branch has one commit that is not in its tracked remote branch.

Run:

```bash
# Check remote URLs
git remote -v

# Check branch and upstream tracking
git branch -vv

# Inspect recent commits
git log --oneline -5

# Push with detailed output
git push -v origin main

# Check status again
git status
```

If the push returns without output but your branch still says it is ahead, investigate the remote configuration and push result instead of assuming it succeeded.

## 16. Complete Git Workflow

A practical workflow for creating a new local project and uploading it to GitHub:

```bash
# 1. Create a project folder
mkdir Demo1
cd Demo1

# 2. Initialize Git
git init

# 3. Create your project files
# Example: index.html and README.md

# 4. Check status
git status

# 5. Stage files
git add .

# 6. Commit changes
git commit -m "Initial project commit"

# 7. Connect your GitHub repository
git remote add origin https://github.com/username/Demo1.git

# 8. Set the branch name
git branch -M main

# 9. Push to GitHub
git push -u origin main
```

For subsequent updates:

```bash
git status
git add .
git commit -m "Updated project files"
git push
```

## 17. 20 Commands to Remember

| No. | Command | Purpose |
|---:|---|---|
| 1 | `git init` | Initialize repository |
| 2 | `git clone <url>` | Clone repository |
| 3 | `git status` | Check status |
| 4 | `git add .` | Stage changes |
| 5 | `git commit -m "msg"` | Commit changes |
| 6 | `git push` | Upload commits |
| 7 | `git pull` | Download and integrate changes |
| 8 | `git fetch` | Download remote updates |
| 9 | `git remote -v` | Check remote URLs |
| 10 | `git log --oneline` | View commit history |
| 11 | `git branch` | List branches |
| 12 | `git switch -c branch` | Create and switch branch |
| 13 | `git switch main` | Switch branch |
| 14 | `git merge branch` | Merge a branch |
| 15 | `git diff` | View unstaged changes |
| 16 | `git stash` | Temporarily save changes |
| 17 | `git stash pop` | Restore stashed changes |
| 18 | `git restore <file>` | Discard unstaged file changes |
| 19 | `git revert <SHA>` | Reverse a commit |
| 20 | `git reflog` | View recent HEAD movements |

## 18. Useful Learning Resources

| Resource | What you can learn | Link |
|---|---|---|
| Git Documentation | Official commands and concepts | [git-scm.com/doc](https://git-scm.com/doc) |
| GitHub Skills | Interactive GitHub exercises | [skills.github.com](https://skills.github.com/) |
| Atlassian Git Tutorials | Beginner-friendly explanations and examples | [Atlassian Tutorials](https://www.atlassian.com/git/tutorials) |
| Learn Git Branching | Visual, interactive branching practice | [learngitbranching.js.org](https://learngitbranching.js.org/) |

---

## Final Tips

- Learn the difference between `git add`, `git commit` and `git push`.
- Always check `git status` before committing.
- Write meaningful commit messages.
- Use branches for new features and bug fixes.
- Pull or fetch remote updates regularly when collaborating.
- Review changes before committing with `git diff`.
- Never push passwords, tokens or private keys.
- Be careful with destructive commands such as `git reset --hard`.

**For aspiring DevOps engineers:** Once you are comfortable with Git, learn branching strategies, Pull Requests, merge conflict resolution, GitHub Actions and CI/CD pipelines. These concepts are used regularly in real-world DevOps workflows.

---

*Created as a quick-reference learning resource. Contributions and corrections are welcome!*

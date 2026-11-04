🚀 Git & GitHub Cheat Sheet

<p align="center">
  <img src="https://readme-typing-svg.demolab.com?font=Fira+Code&size=28&pause=1000&color=2F81F7&center=true&vCenter=true&width=850&lines=Git+%26+GitHub+Cheat+Sheet;Learn+Git+One+Command+at+a+Time;From+Beginner+to+Team+Collaboration" alt="Animated Git and GitHub heading" />
</p>

<p align="center">
  A beginner-friendly, practical reference to the most commonly used Git and GitHub commands — from creating your first repository to collaborating with a team.
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Git-Version%20Control-F05032?logo=git&logoColor=white" />
  <img src="https://img.shields.io/badge/GitHub-Collaboration-181717?logo=github&logoColor=white" />
  <img src="https://img.shields.io/badge/Level-Beginner%20to%20Intermediate-blue" />
  <img src="https://img.shields.io/badge/Documentation-Open%20Source-green" />
</p>

📊 Repository Statistics

Replace USERNAME and REPOSITORY with your actual GitHub username and repository name.

<p align="center">
  <img src="https://img.shields.io/github/stars/USERNAME/REPOSITORY?style=social" />
  <img src="https://img.shields.io/github/forks/USERNAME/REPOSITORY?style=social" />
  <img src="https://img.shields.io/github/watchers/USERNAME/REPOSITORY?style=social" />
  <br/>
  <img src="https://img.shields.io/github/last-commit/USERNAME/REPOSITORY" />
  <img src="https://img.shields.io/github/issues/USERNAME/REPOSITORY" />
  <img src="https://img.shields.io/github/license/USERNAME/REPOSITORY" />
</p>

📑 Table of Contents

Introduction

What is Git and GitHub?

Git Installation and Configuration

Git Workflow

Essential Git Commands

Branching and Merging

GitHub Collaboration Workflow

Undoing Changes

Stashing Changes

GitHub Commands

Common Git Errors and Solutions

Useful Git Tips

Quick Command Reference

📌 Introduction

Git is one of the most widely used version control systems in software development.

This cheat sheet is designed to help developers understand Git commands, manage repositories, track code changes, work with branches and collaborate using GitHub.

Who is this for?

Beginners learning Git for the first time.

Developers working on individual projects.

Engineers collaborating with development teams.

Anyone preparing for technical interviews.

🔍 What is Git and GitHub?

Git

GitHub

Distributed version control system

Cloud-based code hosting platform

Tracks changes in source code

Hosts Git repositories

Works locally

Enables remote collaboration

Manages branches and commits

Supports Pull Requests and code reviews

Simple explanation:

Git tracks changes in your code.

GitHub stores and shares your Git repositories online.

⚙️ Git Installation and Configuration

Install Git

Download Git: https://git-scm.com/downloads

Verify installation:

git --version

Configure your Git identity

git config --global user.name "Your Name"

git config --global user.email "your@email.com"

View configuration:

git config --list

🔄 Git Workflow

Git follows a three-stage local workflow before changes are pushed to GitHub.

Basic Git Workflow

flowchart TD
    A["Working Directory<br/>Edit files"] -->|"git add"| B["Staging Area<br/>Stage changes"]
    B -->|"git commit"| C["Local Repository<br/>Save changes"]
    C -->|"git push"| D["Remote Repository<br/>GitHub"]

    style A fill:#dbeafe,stroke:#2563eb,color:#1e3a8a
    style B fill:#dcfce7,stroke:#16a34a,color:#14532d
    style C fill:#f3e8ff,stroke:#9333ea,color:#581c87
    style D fill:#ffedd5,stroke:#ea580c,color:#9a3412

Understanding the stages

Stage

Meaning

Working Directory

Where you modify files

Staging Area

Where you prepare changes for commit

Local Repository

Where committed changes are stored

Remote Repository

Repository hosted on GitHub

💻 Essential Git Commands

1. Repository Commands

<details>
<summary><b>Click to expand repository commands</b></summary>

Initialize a new repository

git init

Clone an existing repository

git clone <repository-url>

Check repository status

git status

View repository information

git remote -v

Check current branch

git branch

</details>

2. Add and Commit Commands

<details>
<summary><b>Click to expand add and commit commands</b></summary>

Stage a specific file

git add filename

Stage all modified files

git add .

Commit changes

git commit -m "Your commit message"

Commit all tracked changes without separately staging

git commit -am "Your commit message"

View commit history

git log

View compact commit history

git log --oneline

</details>

3. Remote Repository Commands

<details>
<summary><b>Click to expand remote commands</b></summary>

Add a remote repository

git remote add origin <repository-url>

View remote repositories

git remote -v

Push changes to GitHub

git push origin main

Push and set upstream branch

git push -u origin main

Pull latest changes

git pull origin main

Fetch changes without merging

git fetch origin

</details>

4. File Management Commands

<details>
<summary><b>Click to expand file management commands</b></summary>

View changed files

git status

Compare working directory changes

git diff

Compare staged changes

git diff --staged

Rename or move a file

git mv oldname newname

Remove a file from Git and the working directory

git rm filename

View tracked files

git ls-files

</details>

🌿 Branching and Merging

Branches allow developers to work on different features without directly modifying the main branch.

Branching workflow

flowchart TD
    A["Main Branch"] --> B["Create Feature Branch"]
    B --> C["Make Code Changes"]
    C --> D["Commit Changes"]
    D --> E["Push Feature Branch"]
    E --> F["Create Pull Request"]
    F --> G["Code Review"]
    G --> H["Merge into Main"]

    style A fill:#dbeafe,stroke:#2563eb,color:#1e3a8a
    style B fill:#dcfce7,stroke:#16a34a,color:#14532d
    style F fill:#f3e8ff,stroke:#9333ea,color:#581c87
    style H fill:#ffedd5,stroke:#ea580c,color:#9a3412

Branch commands

<details>
<summary><b>Click to expand branch commands</b></summary>

List all local branches

git branch

Create a new branch

git branch feature-login

Switch to another branch

git switch feature-login

Create and switch to a new branch

git switch -c feature-login

Delete a merged branch

git branch -d feature-login

Force delete a branch

git branch -D feature-login

List remote branches

git branch -r

</details>

Merge commands

<details>
<summary><b>Click to expand merge commands</b></summary>

Switch to main

git switch main

Merge feature branch into main

git merge feature-login

Abort an ongoing merge

git merge --abort

View merge history

git log --oneline --graph --all

</details>

Merge vs Rebase

Git Merge

Git Rebase

Combines branch histories

Replays commits onto another base

Can create a merge commit

Creates rewritten commits

Preserves branch history

Creates a more linear history

Good for collaborative integration

Useful for cleaning up local feature branches

Rebase example:

git switch feature-login
git rebase main

Avoid rebasing shared branches unless your team explicitly agrees to it.

🤝 GitHub Collaboration Workflow

A typical team collaboration process looks like this:

flowchart TD
    A["Clone Repository"] --> B["Create Feature Branch"]
    B --> C["Write or Modify Code"]
    C --> D["Stage and Commit Changes"]
    D --> E["Push Feature Branch"]
    E --> F["Open Pull Request"]
    F --> G["Code Review"]
    G --> H{"Approved?"}
    H -->|Yes| I["Merge Pull Request"]
    H -->|Changes Required| C
    I --> J["Update Local Main Branch"]

    style A fill:#dbeafe,stroke:#2563eb,color:#1e3a8a
    style F fill:#f3e8ff,stroke:#9333ea,color:#581c87
    style H fill:#fef3c7,stroke:#d97706,color:#92400e
    style I fill:#dcfce7,stroke:#16a34a,color:#14532d

Practical team workflow

<details>
<summary><b>Click to see the complete collaboration commands</b></summary>

Step 1: Clone the repository

git clone <repository-url>
cd <repository-name>

Step 2: Get the latest changes

git pull origin main

Step 3: Create a feature branch

git switch -c feature-login

Step 4: Make changes and stage them

git add .

Step 5: Commit changes

git commit -m "Added login feature"

Step 6: Push the feature branch

git push -u origin feature-login

Step 7: Create a Pull Request

Open your GitHub repository and select:

Compare & pull request

Step 8: Review and merge

After code review and approval, merge the Pull Request into the main branch.

Step 9: Update your local main branch

git switch main
git pull origin main

Step 10: Delete your local feature branch

git branch -d feature-login

</details>

↩️ Undoing Changes

Git provides different commands to undo changes depending on where those changes exist.

<details>
<summary><b>Click to expand undo commands</b></summary>

Discard changes in a file (not staged)

git restore filename

Unstage a file

git restore --staged filename

Undo the latest commit but keep changes staged

git reset --soft HEAD~1

Undo the latest commit but keep changes unstaged

git reset HEAD~1

Create a new commit that reverses an earlier commit

git revert <commit-id>

View commit history

git log --oneline

Warning: git reset --hard permanently discards uncommitted changes. Use it carefully.

</details>

📦 Stashing Changes

Stashing temporarily saves your uncommitted changes so you can work on something else.

<details>
<summary><b>Click to expand stash commands</b></summary>

Save current changes

git stash

Save with a message

git stash push -m "Work in progress"

View saved stashes

git stash list

Apply latest stash and keep it saved

git stash apply

Apply and remove latest stash

git stash pop

Delete a stash

git stash drop

Delete all stashes

git stash clear

</details>

🌐 GitHub Commands

GitHub CLI

GitHub CLI (gh) allows you to interact with GitHub directly from your terminal.

Install: https://cli.github.com/

<details>
<summary><b>Click to expand GitHub CLI commands</b></summary>

Authenticate with GitHub

gh auth login

Check authentication status

gh auth status

Create a repository

gh repo create

View repository details

gh repo view

Create a Pull Request

gh pr create

List Pull Requests

gh pr list

Check out a Pull Request

gh pr checkout <number>

View issues

gh issue list

</details>

🛠️ Common Git Errors and Solutions

1. Everything up-to-date

Message:

Everything up-to-date

Reason: There are no new committed local changes to push.

Solution:

git status
git add .
git commit -m "Updated files"
git push origin main

2. Your branch is ahead of origin/main

Message:

Your branch is ahead of 'origin/main' by 1 commit.

Reason: You committed locally but haven't pushed the commit.

Solution:

git push origin main

3. Your branch is behind origin/main

Message:

Your branch is behind 'origin/main'.

Reason: The remote repository has commits that your local branch doesn't have.

Solution:

git pull --rebase origin main

Resolve any conflicts if they occur.

4. Failed to push some refs

Message:

! [rejected] main -> main (fetch first)

Reason: The remote branch contains changes that are missing locally.

Solution:

git pull --rebase origin main
git push origin main

5. Source refspec main does not match any

Message:

error: src refspec main does not match any

Reason: Your local branch may have a different name or no commit exists yet.

Solution:

git branch -M main
git add .
git commit -m "Initial commit"
git push -u origin main

6. Not a Git repository

Message:

fatal: not a git repository

Reason: Your terminal is not inside a Git repository.

Solution:

cd <repository-folder>
git status

7. Merge conflicts

Message:

CONFLICT (content): Merge conflict in filename

Reason: Git cannot automatically combine changes made to the same part of a file.

Solution:

git status

Open the conflicted file.

Find the conflict markers.

Choose or combine the correct changes.

Remove the conflict markers.

Stage the resolved file.

git add filename
git commit -m "Resolved merge conflict"

8. Permission denied / Authentication failed

Reason: Your GitHub authentication or repository permissions may be incorrect.

Solution:

Check your repository access.

Verify your remote URL.

Configure SSH authentication or use Git Credential Manager.

For HTTPS, use an appropriate authentication method such as a Personal Access Token when prompted.

Check your remote:

git remote -v

💡 Useful Git Tips

Create a .gitignore file

A .gitignore file tells Git which untracked files and directories to ignore.

Example:

.env
node_modules/
__pycache__/
*.log
.DS_Store

Important: Never commit passwords, API keys, private tokens or other secrets.

Useful aliases

git config --global alias.st status
git config --global alias.co checkout
git config --global alias.br branch
git config --global alias.cm "commit -m"
git config --global alias.lg "log --oneline --graph --all"

Now you can use:

git st
git br
git lg

View a visual commit history

git log --oneline --graph --decorate --all

⚡ Quick Command Reference

Command

Purpose

git init

Initialize repository

git clone URL

Clone repository

git status

Check status

git add .

Stage all changes

git commit -m "msg"

Commit changes

git push origin main

Push changes

git pull origin main

Pull changes

git fetch origin

Fetch remote updates

git branch

List branches

git switch -c branch

Create and switch branch

git merge branch

Merge a branch

git stash

Temporarily save changes

git log --oneline

View commit history

git diff

Compare changes

git restore file

Discard unstaged changes

git revert ID

Reverse a commit

🎯 Recommended Learning Path

If you're new to Git, learn these concepts in order:

Understand Git and GitHub.

Install and configure Git.

Learn init, clone and status.

Understand add, commit and push.

Learn branches and merging.

Understand Pull Requests.

Practice resolving merge conflicts.

Learn advanced commands like rebase, stash and revert.

📚 Useful Resources

Official Git Documentation

Git Book

GitHub Documentation

GitHub Skills

GitHub CLI Documentation

<p align="center">
  <b>⭐ If this cheat sheet helped you, consider giving this repository a star!</b>
</p>

<p align="center">
  Made with ❤️ by <b>Devanshi Sharma</b>
</p>

<p align="center">
  <i>Learn. Practice. Commit. Push. Repeat. 🚀</i>
</p>
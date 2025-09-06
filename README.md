# Introductory_-Git-Cheat-Sheet

Git Cheat Sheet (Extended Guide)

A concise yet detailed guide for developers and DevOps engineers. It covers installation, setup, core commands, branching, merging, history management, collaboration, recovery, and advanced workflows. Perfect for quick reference during development and deployment.

1️⃣ Installing Git

Install Git depending on your operating system.

Command	Description
Windows	Download Git for Windows
 (includes Git Bash).
brew install git	Install Git with Homebrew (macOS).
sudo port selfupdate && sudo port install git	Install Git with MacPorts (macOS).
sudo apt-get install git	Install Git (Debian/Ubuntu Linux).
sudo yum install git	Install Git (RHEL/CentOS Linux).
git --version	Check the installed Git version.
2️⃣ Git Configuration & Setup

Before using Git, configure your identity and preferences.

Command	Description
git config --global user.name "Your Name"	Set username globally.
git config --global user.email "you@example.com"	Set email globally.
git config --global color.ui auto	Enable colored output.
git config --global init.defaultBranch main	Set default branch name (main instead of master).
git config --global alias.st status	Create an alias (shortcut). Example: git st.
git config --list	List all configuration values.
git config --get <key>	Get a specific config (e.g., user.name).
git help	Show Git help.
3️⃣ Initializing a Repository

Start tracking your project with Git.

Command	Description
git init	Initialize a repository in the current directory.
git init <dir>	Create a new repo in <dir>.
git clone <repo-url>	Clone a remote repository.
git clone --branch <branch> <repo-url>	Clone a specific branch.
4️⃣ Basic Git Commands

Work with files and track changes.

Command	Description
git add <file>	Stage a specific file.
git add .	Stage all changes.
git status	Show file states (staged, unstaged, untracked).
git diff	Show unstaged changes.
git diff --staged	Show staged changes.
git commit -m "message"	Commit staged changes.
git commit -am "message"	Stage + commit all tracked files.
git rm <file>	Delete a file and stage deletion.
git mv <old> <new>	Rename/move a file.
git restore <file>	Discard changes in working directory.
5️⃣ Conventional Commit Messages

Use structured commit messages for clarity.

feat: add new feature

fix: resolve a bug

chore: maintenance task

refactor: code improvement

docs: update documentation

style: formatting changes

test: add/update tests

perf: performance improvement

ci: update CI/CD pipeline

build: build process changes

revert: undo previous commit

6️⃣ Branching & Merging

Work with multiple development lines.

Command	Description
git branch	List local branches.
git branch -a	List local + remote branches.
git branch <name>	Create new branch.
git branch -d <name>	Delete branch.
git checkout <branch>	Switch branch.
git checkout -b <branch>	Create + switch branch.
git merge <branch>	Merge a branch into current branch.
git log --oneline --graph	Visualize branch history.
7️⃣ Stashing

Save work-in-progress temporarily.

Command	Description
git stash	Stash changes.
git stash list	List stashes.
git stash pop	Apply last stash and remove it.
git stash apply	Apply stash without removing.
git stash drop	Delete most recent stash.
8️⃣ Tags & Releases

Mark specific points in history.

Command	Description
git tag	List tags.
git tag <name>	Create lightweight tag.
git tag -a <name> -m "msg"	Create annotated tag.
git show <tag>	Show tag details.
git push origin <tag>	Push tag to remote.
9️⃣ Working with Remotes

Collaborate with remote repositories.

Command	Description
git remote -v	List remote URLs.
git remote add origin <url>	Add remote repository.
git fetch	Fetch updates (no merge).
git pull	Fetch + merge updates.
git pull --rebase	Fetch + reapply commits (clean history).
git push origin <branch>	Push branch to remote.
git push --all	Push all branches.
git push --tags	Push tags.
🔟 Logging & Reviewing History

Investigate commits and changes.

Command	Description
git log	Full commit history.
git log --oneline	Short form.
git log --graph --all	Graph view of branches.
git log --author="name"	Filter commits by author.
git log --since="2 weeks ago"	Filter by date.
git show <commit>	Show commit details.
git blame <file>	See who last modified each line.
1️⃣1️⃣ Managing History

Rewriting and cleaning commits.

Command	Description
git commit --amend	Edit last commit.
git reset --soft <commit>	Reset HEAD, keep changes staged.
git reset --mixed <commit>	Reset HEAD, keep changes unstaged.
git reset --hard <commit>	Reset HEAD, discard all changes.
git revert <commit>	Undo a commit by creating a new commit.
git rebase <branch>	Reapply commits onto another branch.
git rebase -i HEAD~n	Interactive rebase (edit, squash commits).
1️⃣2️⃣ Recovering Lost Work (Reflog)

Reflog tracks HEAD movement—even resets.

Command	Description
git reflog	Show history of HEAD changes.
git checkout HEAD@{n}	Go back to a previous state.
git reset --hard HEAD@{n}	Restore repo to a past state.
1️⃣3️⃣ Collaboration Workflow (Best Practices)

Clone repository: git clone <url>

Create feature branch: git checkout -b feature-xyz

Make changes & commit: git add . && git commit -m "feat: add xyz"

Pull latest updates: git pull origin main --rebase

Push branch: git push origin feature-xyz

Open a Pull Request (PR) on GitHub/GitLab.

Code review & merge into main.

1️⃣4️⃣ Troubleshooting Git
Problem	Solution
Accidentally deleted file	git restore <file>
Undo last commit (keep changes)	git reset --soft HEAD~1
Undo last commit (discard changes)	git reset --hard HEAD~1
Merge conflict	Edit conflicting files → git add . → git commit
Detached HEAD	git checkout <branch> to return.
Want clean history	git rebase -i (interactive rebase).

✅ This makes the Git Cheat Sheet a full reference—installation → daily commands → collaboration → recovery → troubleshooting.

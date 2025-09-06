# Introductory - Git Cheat Sheet

A concise yet detailed Git reference for developers and DevOps engineers. Installation, setup, daily commands, branching, history management, collaboration, recovery, and troubleshooting — organized for quick lookup.

## Table of Contents
| Section | Description |
|---|---|
| [1. Installing Git](#installing-git) | How to install Git on common platforms and check version. |
| [2. Configuration & Setup](#configuration--setup) | Configure identity, defaults, and useful aliases. |
| [3. Initializing a Repository](#initializing-a-repository) | Create or clone repositories and clone specific branches. |
| [4. Basic Commands](#basic-commands) | Stage, commit, move, restore files and view diffs. |
| [5. Conventional Commit Messages](#conventional-commit-messages) | Recommended commit message types for consistency. |
| [6. Branching & Merging](#branching--merging) | Create, list, switch and merge branches; visualize history. |
| [7. Stashing](#stashing) | Temporarily save work-in-progress and apply later. |
| [8. Tags & Releases](#tags--releases) | Create and push tags for releases. |
| [9. Working with Remotes](#working-with-remotes) | Add, fetch, pull and push to remote repositories. |
| [10. Logging & Reviewing History](#logging--reviewing-history) | Inspect commit history, blame and show commits. |
| [11. Managing History](#managing-history) | Amend, reset, revert and rebase to rewrite history. |
| [12. Recovering Lost Work (Reflog)](#recovering-lost-work-reflog) | Use reflog to recover lost HEAD states. |
| [13. Collaboration Workflow (Best Practices)](#collaboration-workflow-best-practices) | Suggested workflow for feature branches and PRs. |
| [14. Troubleshooting Git](#troubleshooting-git) | Quick fixes for common problems. |

---

## 1. Installing Git
| Platform / Command | Description |
|---|---|
| Windows | Download and install "Git for Windows" (includes Git Bash). |
| macOS (Homebrew) | brew install git |
| macOS (MacPorts) | sudo port selfupdate && sudo port install git |
| Debian/Ubuntu | sudo apt-get install git |
| RHEL/CentOS | sudo yum install git |
| Verify | git --version — check installed Git version |

---

## 2. Configuration & Setup
| Command | Description |
|---|---|
| git config --global user.name "Your Name" | Set global username |
| git config --global user.email "you@example.com" | Set global email |
| git config --global color.ui auto | Enable colored output |
| git config --global init.defaultBranch main | Use `main` as default branch |
| git config --global alias.st status | Example alias: `git st` |
| git config --list | List all configuration |
| git config --get <key> | Get a specific config value |

---

## 3. Initializing a Repository
| Command | Description |
|---|---|
| git init | Initialize a repo in current directory |
| git init <dir> | Create a new repo in <dir> |
| git clone <repo-url> | Clone a repository |
| git clone --branch <branch> <repo-url> | Clone a specific branch |

---

## 4. Basic Commands
| Command | Description |
|---|---|
| git add <file> | Stage a specific file |
| git add . | Stage all changes |
| git status | Show file states (staged, unstaged, untracked) |
| git diff | Show unstaged changes |
| git diff --staged | Show staged changes |
| git commit -m "msg" | Commit staged changes |
| git commit -am "msg" | Stage tracked files + commit |
| git rm <file> | Remove file and stage deletion |
| git mv <old> <new> | Rename or move a file |
| git restore <file> | Discard working-directory changes |

---

## 5. Conventional Commit Messages
Use structured prefixes to communicate intent:
| Prefix | Meaning |
|---|---|
| feat: | Add a new feature |
| fix: | Bug fix |
| chore: | Maintenance |
| refactor: | Code change without behavior changes |
| docs: | Documentation updates |
| style: | Formatting or whitespace |
| test: | Add or update tests |
| perf: | Performance improvements |
| ci: | CI/CD changes |
| build: | Build system changes |
| revert: | Revert a previous commit |

---

## 6. Branching & Merging
| Command | Description |
|---|---|
| git branch | List local branches |
| git branch -a | List local + remote branches |
| git branch <name> | Create new branch |
| git branch -d <name> | Delete branch |
| git checkout <branch> | Switch branch |
| git checkout -b <branch> | Create and switch |
| git merge <branch> | Merge branch into current |
| git log --oneline --graph | Visualize branch history |

---

## 7. Stashing
| Command | Description |
|---|---|
| git stash | Stash changes |
| git stash list | List stashes |
| git stash pop | Apply last stash and remove it |
| git stash apply | Apply stash (keep it) |
| git stash drop | Delete a stash |

---

## 8. Tags & Releases
| Command | Description |
|---|---|
| git tag | List tags |
| git tag <name> | Create lightweight tag |
| git tag -a <name> -m "msg" | Create annotated tag |
| git show <tag> | Show tag details |
| git push origin <tag> | Push tag to remote |

---

## 9. Working with Remotes
| Command | Description |
|---|---|
| git remote -v | List remote URLs |
| git remote add origin <url> | Add remote |
| git fetch | Download updates without merging |
| git pull | Fetch + merge |
| git pull --rebase | Fetch + reapply local commits |
| git push origin <branch> | Push branch |
| git push --all | Push all branches |
| git push --tags | Push tags |

---

## 10. Logging & Reviewing History
| Command | Description |
|---|---|
| git log | Full commit history |
| git log --oneline | Compact history |
| git log --graph --all | Graph view including all branches |
| git log --author="name" | Filter by author |
| git log --since="2 weeks ago" | Filter by date |
| git show <commit> | Show commit details |
| git blame <file> | See last modifier per line |

---

## 11. Managing History
| Command | Description |
|---|---|
| git commit --amend | Edit last commit |
| git reset --soft <commit> | Move HEAD, keep staged |
| git reset --mixed <commit> | Move HEAD, keep unstaged |
| git reset --hard <commit> | Move HEAD, discard changes |
| git revert <commit> | Create commit that undoes another |
| git rebase <branch> | Reapply commits onto branch |
| git rebase -i HEAD~n | Interactive rebase (edit/squash) |

---

## 12. Recovering Lost Work (Reflog)
| Command | Description |
|---|---|
| git reflog | Show HEAD changes history |
| git checkout HEAD@{n} | View a previous state |
| git reset --hard HEAD@{n} | Restore to a past state |

---

## 13. Collaboration Workflow (Best Practices)
A common workflow:
1. git clone <url>  
2. git checkout -b feature/xyz  
3. Make commits: git add . && git commit -m "feat: ..."  
4. Keep up to date: git pull origin main --rebase  
5. Push: git push origin feature/xyz  
6. Open a Pull Request; review and merge to main

---

## 14. Troubleshooting Git
| Problem | Solution |
|---|---|
| Accidentally deleted file | git restore <file> |
| Undo last commit (keep changes) | git reset --soft HEAD~1 |
| Undo last commit (discard changes) | git reset --hard HEAD~1 |
| Merge conflict | Edit conflicting files → git add . → git commit |
| Detached HEAD | git checkout <branch> |
| Want clean history | git rebase -i to squash/edit commits |

---

This README is optimized for quick reference — use the table links above to jump to the section you need.

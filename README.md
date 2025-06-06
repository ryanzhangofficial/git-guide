# git-guide

> **A concise, copy-paste reference for everyday Git commands and workflow tips.**

## 📁 Repository Layout
~~~
git-guide/
├── README.md   ← this guide
├── main.java   ← minimal Java example (ProcessBuilder + Git)
└── main.py     ← minimal Python example (subprocess + Git)
~~~

## 🚀 Quick Start
~~~
# clone & enter
git clone https://github.com/ryanzhangofficial/git-guide.git
cd git-guide

# create a feature branch
git switch -c <feature>

# work → stage → commit
git add .
git commit -m "feat: <message>"

# sync with main before pushing
git fetch origin
git rebase origin/main   # or: git merge origin/main

# push & open PR
git push -u origin <feature>
~~~

## 🔄 Branch Commands

| Goal                     | Command                                      |
|--------------------------|----------------------------------------------|
| List branches            | `git branch -a`                              |
| Rename current branch    | `git branch -M <new>`                        |
| Delete local branch      | `git branch -d <name>`                       |
| Delete remote branch     | `git push origin --delete <name>`            |
| Switch & create (`-b`)   | `git checkout -b <name>` / `git switch -c <name>` |

## 🏷️ Tagging Releases
~~~
# create annotated tag
git tag -a v1.0 -m "First stable release"

# push a single tag
git push origin v1.0

# delete & recreate tag
git tag -d v1.0
git push origin --delete v1.0
git tag -a v1.0 -m "Retagged v1.0"
git push origin v1.0
~~~

## 🧹 History Cleanup
~~~
git rebase -i HEAD~N   # squash or reword last N commits
git commit --amend     # edit most recent commit
git reflog             # recover lost refs / commits
git stash              # shelve uncommitted changes
~~~

## 🛠️ Script Stubs

| File        | Purpose                                                            |
|-------------|--------------------------------------------------------------------|
| **main.py** | Demonstrates calling Git commands from Python via `subprocess`     |
| **main.java** | Same concept using Java’s `ProcessBuilder`                       |

## 📝 Contributing Guidelines

1. **Fork** → **branch** → **PR**.  
2. Keep code **comment-free** (per project preference).  
3. Use commit style: `<type>: <subject>` where type ∈ `feat`, `fix`, `docs`, `refactor`, `chore`.

## 🖋️ License
MIT

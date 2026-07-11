# Git Commands Reference

This file documents commonly used Git commands, organized by category.

## Setup and Configuration

- `git config --global user.name "Your Name"` — set your Git username.
- `git config --global user.email "you@example.com"` — set your email.
- `git config --list` — view current Git settings.
- `git help <command>` — view Git command help.

## Repository and Branch Management

- `git init` — initialize a new Git repository.
- `git clone <repo>` — clone a remote repository.
- `git branch` — list branches.
- `git branch <name>` — create a new branch.
- `git switch <branch>` — switch to an existing branch.
- `git switch -c <branch>` — create and switch to a new branch.
- `git checkout <branch>` — switch branches (legacy).
- `git checkout -b <branch>` — create and switch to a new branch (legacy).
- `git branch -d <branch>` — delete a local branch.
- `git branch -D <branch>` — force delete a local branch.
- `git fetch` — download changes from remote.
- `git pull` — fetch and merge changes from remote.
- `git push` — upload commits to remote.
- `git push origin --delete <branch>` — delete a remote branch.

## Staging and Commit

- `git add <file>` — stage file changes.
- `git add .` — stage all changes.
- `git status` — show changed files and branch status.
- `git diff` — show unstaged differences.
- `git diff --staged` — show staged changes.
- `git commit -m "message"` — record staged changes.
- `git commit -am "message"` — stage and commit tracked files.
- `git commit --amend` — amend the last commit.
- `git reset` — undo staged changes.
- `git reset --soft <commit>` — move HEAD but keep changes staged.
- `git reset --mixed <commit>` — move HEAD and keep changes unstaged.
- `git reset --hard <commit>` — reset working tree and index.

## History and Inspection

- `git log` — view commit history.
- `git log --oneline` — view compact commit history.
- `git log --graph --decorate --all` — view branch history visually.
- `git show <commit>` — show commit details.
- `git blame <file>` — show who changed each line.
- `git tag` — list tags.
- `git reflog` — show local reference history.

## Merging and Rewriting History

- `git merge <branch>` — merge another branch into the current branch.
- `git merge --no-ff <branch>` — create a merge commit even if not required.
- `git rebase <branch>` — reapply commits on top of another branch.
- `git rebase -i <commit>` — interactively rewrite commit history.
- `git cherry-pick <commit>` — apply a commit from another branch.
- `git revert <commit>` — create a new commit that undoes another commit.
- `git stash` — save local changes temporarily.
- `git stash list` — list stash entries.
- `git stash apply` — reapply stashed changes.
- `git stash pop` — reapply and remove the latest stash.
- `git stash drop` — remove a stash entry.
- `git stash clear` — remove all stash entries.

## Tagging and Releases

- `git tag -a v1.0.0 -m "Initial release"` — create an annotated tag.
- `git tag <name>` — create a lightweight tag.
- `git push origin <tag>` — push a specific tag.
- `git push origin --tags` — push all tags.
- `git describe --tags` — show the latest tag reachable.

## Remote and Collaboration

- `git remote -v` — show remote repositories.
- `git remote add origin <url>` — add a new remote.
- `git remote remove origin` — remove a remote.
- `git remote set-url origin <url>` — update remote URL.
- `git fetch origin` — fetch from a specific remote.
- `git pull origin <branch>` — pull from a specific branch.
- `git push origin <branch>` — push to a specific branch.

## Maintenance and Clean-up

- `git gc` — optimize repository data.
- `git clean -f` — remove untracked files.
- `git clean -fd` — remove untracked files and directories.
- `git clean -n` — preview untracked file removal.
- `git bisect start` — begin a binary search for regression commits.
- `git bisect good <commit>` — mark a commit as good.
- `git bisect bad <commit>` — mark a commit as bad.

## Troubleshooting

- `git status --short` — concise status output.
- `git diff HEAD` — compare working tree to last commit.
- `git reset --hard origin/<branch>` — reset local branch to remote state.
- `git merge --abort` — cancel a failed merge.
- `git rebase --abort` — cancel a failed rebase.
- `git rebase --continue` — continue after resolving conflicts.

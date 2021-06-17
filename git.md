# Git Quick Reference Guide

By [Chris Campbell](https://github.com/christophertcampbell)

## Initialize an Empty Repository

Note: This process does NOT delete or modify any files in the folder. You can safely initialize a repository in a folder which already contains source code.

Task | Git Command
--- | ---
Initialize an empty repository | `git init`
Add an origin repository | `git remote add origin https://github.com/your-user-name/repo-name.git`
View the remote repository settings | `git remote -v`
Fix the origin repository url | `git remote set-url origin https://github.com/your-user-name/repo-name.git`

If you already have source files to check-in, you can now stage your files, commit them and push to the remote repository.

## Check Out a Repository

Task | Git Command
--- | ---
Check out a repository | `git clone <repo_url>`

## View Local Changes

Task | Git Command
--- | ---
List un-committed, changed files | `git status` or `git diff --name-only`
Diff changes | `git diff` (use `space` to advance pages, `q` to quit the diff)
Diff pending changes in a file | `git diff HEAD <filename>`

## Stage / Un-Stage Local Changes

Task | Git Command
--- | ---
Stage all changes | `git add -A`
Stage new and modified, without deleted | `git add .`
Stage modified and deleted, without new | `git add -u`
Un-Stage all changes | `git reset`
Un-Stage a particular file or path | `git reset -- <filename>`

## Commit Staged Changes

Task | Git Command
--- | ---
Commit staged changes | `git commit -m "Commit message goes here"`
Undo the last commit (keeping changes) | `git reset --soft HEAD~1` (or SHA-1 hash of the commit to revert to)
Undo the last commit (discarding changes) | `git reset --hard HEAD~1` (or SHA-1 hash of the commit to revert to)
Revert the last commit (if already pushed) | `git revert HEAD` (then do a fresh push)

## Publish Commited Changes to the Remote Repository

Task | Git Command
--- | ---
Publish commited changes to the origin repository | `git push` or `git push origin master` (push local branch `master` to the remote repo `origin`)

## Update Local Repository from the Remote Repository

Task | Git Command | Description
--- | --- | ---
Fetch changes | `git fetch` or `git fetch origin` | Fetches all changes in all branches from the remote origin repository and brings them into the local tracking branches (eg: origin/master). Does NOT merge the changes into your working local branches or alter your files
Preview changes | `git diff master origin/master` | Preview changes before merging
Merge changes | `git merge origin/master` | Merge changes from the local tracking branch (origin/master) into the local working branch (master). May produce merge conflicts at this point which need to be resolved.
Pull changes | `git pull` or `git pull origin master` | Alternate to the fetch/merge process. Fetches and merges in one step. May produce merge conflicts. Does not allow preview of changes before merging.

## Configuration

Task | Git Command
--- | ---
View user name | `git config [--global] user.name`
View user email | `git config [--global] user.email`
Update user name | `git config [--global] user.name <name>`
Update user email | `git config [--global] user.email <email>`
View all settings | `git config [--global] --list`

## Terms

Term | Description
--- | ---
origin | The remote repository (eg: on GitHub)
master | A local branch (eg: on your local computer)
origin/master | A remote-tracking branch (eg: a local copy of the branch named "master" on the remote named "origin")

## Good Articles and Resources

* <https://git-scm.com/book/en/v2/>
* <https://www.atlassian.com/git/tutorials>
* <https://www.git-tower.com/learn/git/ebook/>
* <https://longair.net/blog/2009/04/16/git-fetch-and-merge/>

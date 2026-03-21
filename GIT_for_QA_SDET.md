# GIT commands for QA - SDET engineers

## BASICS

- `git init` <br>
  Create a new Git repository in current folder

- `git clone <url>` <br>
  Download a remote repository to your machine

- `git status` <br>
  See what files changed since last commit

- `git add .` <br>
  Stage all changed files for commit

- `git add <file>` <br>
  Stage a specific file for commit

- `git commit -m 'message'` <br>
  Save staged changes with a description

- `git push` <br>
  Upload your commits to the remote repository

- `git pull` <br>
  Download and merge latest changes from remote

## BRANCHING

- `git branch` <br>
  List all local branches

- `git branch <name>` <br>
  Create a new branch

- `git checkout <branch>` <br>
  Switch to an existing branch

- `git checkout -b <name>` <br>
  Create and switch to a new branch

- `git branch -d <name>` <br>
  Delete a branch (safe, checks merge)

- `git branch -D <name>` <br>
  Force delete a branch (no merge check)

- `git merge <branch>` <br>
  Merge another branch into current one

- `git branch -a` <br>
  List all branches including remote

## SYNCING WITH REMOTE

- `git fetch` <br>
  Download remote changes without merging

- `git pull origin main` <br>
  Pull latest from main branch

- `git push origin <branch>` <br>
  Push your branch to remote

- `git push u origin <branch>` <br>
  Push and set upstream tracking

- `git remote -v` <br>
  Show remote repository URLs

- `git pull --rebase origin main` <br>
  Rebase your work on top of latest main

## UNDOING MISTAKES

- `git checkout -- <file>` <br>
  Discard changes in a specific file
  
- `git reset HEAD <file>` <br>
  Unstage a file (keep changes)
  
- `git reset-soft HEAD~1` <br>
  Undo last commit (keep changes staged)
  
- `git reset --hard HEAD~1` <br>
  Undo last commit (DELETE changes)

- `git revert <commit>` <br>
  Create new commit that undoes a past commit

- `git clean -fd` <br>
  Remove all untracked files and folders

- `git restore <file>` <br>
  Modern way to discard file changes

## STASHING
- `git stash` <br>
  Save uncommitted changes temporarily
  
- `git stash pop` <br>
  Restore stashed changes and remove stash
   
- `git stash apply` <br>
  Restore stashed changes and keep stash
   
- `git stash list` <br>
  Show all saved stashes
   
- `git stash drop` <br>
  Delete the most recent stash
   
- `git stash clear` <br>
  Delete all stashes
   
- `git stash -m 'description'` <br>
  Stash with a descriptive message

## HISTORY & LOGS
- `git log --oneline` <br>
  Compact commit history (one line each)

- `git log --graph --oneline` <br>
  Visual branch/merge history
  
- `git log -5` <br>
  Show last 5 commits
  
- `git log -- <file>` <br>
  Show commits that changed a specific file
  
- `git diff` <br>
  Show unstaged changes

- `git diff --staged` <br>
  Show staged changes

- `git blame <file>` <br>
  Show who last modified each line

- `git show <commit>` <br>
   Show details of a specific commit

## PR WORKFLOW
- `git checkout -b feature/my-tests` <br>
  Create feature branch for your tests

- `git add . && git commit -m 'msg'` <br>
  Stage and commit your changes
  
- `git push -u origin feature/my-tests` <br>
  Push branch to remote
  
- `git pull --rebase origin main` <br>
  Rebase on latest main before PR
   
- `git push --force-with-lease` <br>
  Safe force push after rebase
   
- `git checkout main && git pull` <br>
  Switch to main and get latest
   
- `git branch -d feature/my-tests` <br>
  Clean up merged feature branch

## OH NO FIXES
- Committed to wrong branch?  <br>
  git stash > checkout correct > stash pop

- Need to change last commit msg? <br>
  git commit --amend -m 'new message'

- Forgot to add a file to commit? <br>
  git add file > git commit --amend --no-edit

- Merge conflict? <br>
  Open file > fix conflict markers > add > commit

- Accidentally deleted a branch? <br>
  git reflog > find commit > checkout -b <name> <hash>

- Pushed something you shouldn't? <br>
  git revert <commit> > push (never force push main)

## GIT tips for QA Engineers

- Name branches clearly <br>
Use feature/login-tests or fix/flaky-checkout-test
so anyone can tell what you're working on from the
branch name.

- Commit test files separately from config <br>
Keep test code commits separate from config
changes. Makes code review easier and reverts
safer.

- Pull before you push. Always. <br>
Run git pull before git push every single time.
This one habit prevents 90% of merge conflicts.

- Use .gitignore for test artifacts <br>
Add test-results/, playwright-report/, and
node_modules/ to .gitignore. Never commit
generated files.

- Write meaningful commit messages <br>
"added tests" tells nobody anything. "Add login
validation tests for SSO flow" tells everyone
everything.

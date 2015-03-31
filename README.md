GIT TUTORIAL

https://www.atlassian.com/git/tutorials/rewriting-history

git tag
	See: http://gitimmersion.com/lab_13.html
=======

# TO MERGE A DETACHED HEAD COMMIT:
git checkout -b temp
git log --graph --decorate --pretty=oneline --abbrev-commit master origin/master temp
git diff master temp
git diff origin/master temp
// update master branch to point to temp
git checkout -B master temp
git branch -d temp

# REVERT = SAFE UNDO
git revert <commit> - doesn't change project history, undo by adding new commit

# RESET = DANGEROUS UNDO - NOT FOR PUBLIC REPOS
git reset <commit></commit> - resets staging area to most recent or specific commit, but working directory remains same
git reset --hard <commit> - resets both staging area AND working directory

# REWRITING HISTORY - NOT FOR PUBLIC REPOS
git commit --amend --no-edit // adds current staged files to last commit

REBASE- move a branch to a new base commit to maintain linear history, common for integrating upstream changes into local repo
git checkout feature-branch
git rebase master
git checkout master
git merge feature-branch
// use "git rebase -i master" to clean up commits before rebasing
// use squash to squash old onto new
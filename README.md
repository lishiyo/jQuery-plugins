TEST

App Academy Plugins

git tag
	See: http://gitimmersion.com/lab_13.html
=======


# REVERT = SAFE UNDO
git revert <commit> - doesn't change project history, undo by adding new commit

# RESET = DANGEROUS UNDO
git reset <commit></commit> - resets staging area to most recent or specific commit, but working directory remains same
git reset --hard <commit> - resets both staging area AND working directory
reset ONLY affects tracked files. To remove untracked files:
git clean -n // shows you which files will be removed
git clean -f // removes untracked files in current directory (use -df to remove directors as well)

# TO MERGE A DETACHED HEAD COMMIT:
git checkout -b temp
git log --graph --decorate --pretty=oneline --abbrev-commit master origin/master temp
git diff master temp
git diff origin/master temp
// update master branch to point to temp
git checkout -B master temp
git branch -d temp

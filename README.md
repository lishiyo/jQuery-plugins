TEST

App Academy Plugins

Detached head - tag v1-beta
See: http://gitimmersion.com/lab_13.html

git revert <commit> - doesn't change project history, undo by adding new commit

# TO MERGE A DETACHED HEAD COMMIT:
git checkout -b temp
git log --graph --decorate --pretty=oneline --abbrev-commit master origin/master temp
git diff master temp
git diff origin/master temp
// update master branch to point to temp
git checkout -B master temp
git branch -d temp
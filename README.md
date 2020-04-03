# awesome git commands [![Awesome](https://cdn.rawgit.com/sindresorhus/awesome/d7305f38d29fed78fa85652e3a63e154dd8e8829/media/badge.svg)](https://github.com/sindresorhus/awesome)

🍴 Useful git commands for everyday use

❤️ Support my app ❤️ 

- [Push Hero - pure Swift native macOS application to test push notifications](https://www.producthunt.com/posts/push-hero-2)
- [PastePal - Pasteboard, note and shortcut manager](https://www.producthunt.com/posts/pastepal)
- [Frame recorder - Recorder gif and video with frame](https://www.producthunt.com/posts/frame-recorder)
- [Alias - App and file shortcut manager](https://www.producthunt.com/posts/alias-shortcut-manager)
- [Other apps](https://onmyway133.github.io/projects/)

❤️❤️😇😍🤘❤️❤️

## Checking

### Status

Check the status of working directory and staging area

```
git status
```

Show changes between HEAD and working directory

```
git diff
```

### Log

Show the list of commits in one line format

```
git log --oneline
```

Show commits that make add or remove a certain string

```
git log -S 'LoginViewController'
```

Search commits that contain a log message

```
git log — all — grep=’day of week’
```

### Check out

Checkout a tag

```
    git checkout tagname

    git checkout -b newbranchname tagname
```

Checkout a branch:

    git checkout destination_branch

Use -m if there is merge conflict:

    git checkout -m master // from feature branch to master

Checkout a commit:

    git checkout commit_hash

    git checkout -b newbranchname HEAD~4

    git checkout -b newbranchname commit_hash

    git checkout commit_hash file

Checkout a file:

    git checkout c5f567 -- Relative/Path/To/File

### Diff

Make and apply diff file between 2 branches

```
git diff BRANCH ANOTHER_BRANCH > file.diff
git apply file.diff
```

## Committing

### Tag

List all tags

```
git tag
```

Tag a commit

```
git tag -a TAG -m "TAG MESSAGE"
```

Delete remote tags

```
git push --delete REMOTE TAG
```

```
git push origin :TAG
```

Push tag to remote

```
git push REMOTE TAG
```

Rename tag

```
git tag NEW_TAG OLD_TAG
git tag -d OLD_TAG
```

Move tag from one commit to another commit

```
git push origin :TAG
git tag -fa TAG
git push REMOTE --tags
```

### Remote

List all remote

```
git remote
```

Rename remote

```
git remote rename OLD_REMOTE NEW_REMOTE
```

Remove stale remote tracking branches

```
git remote prune REMOTE
```

### Branch

List all branches

```
git branch
```

Create the branch on your local machine and switch in this branch

```
git checkout -b BRANCH
```

Create branch from commit

```
git branch BRANCH COMMIT_HASH
```

Push the branch to remote

git push REMOTE BRANCH

Rename other branch

```
git branch -m OLD_BRANCH NEW_BRANCH
```

Rename current branch

```
git branch -m NEW_BRANCH
```

Rename remote branch

```
git branch -m old new               # Rename branch locally    
Git push origin :old                 # Delete the old branch    
git push --set-upstream origin new   # Push the new branch, set local branch to track the new remote
```

Delete a branch locally and remote

```
git branch -D BRANCH
git push REMOTE :BRANCH
```

Delete all local branches but master

```
git branch | grep -v "master" | xargs git branch -D
```

### Commit

Undo last commit

```
git reset --hard HEAD~1
```

Squash last n commits into one commit

```
git rebase -i HEAD~5

git reset --soft HEAD~5
git add .
git commit -m "Update"
git push -f origin master
```

Move last commits into new branch:

```
git branch newbranch
git reset --hard HEAD~3 # Go back 3 commits. You *will* lose uncommitted work.*1
git checkout newbranch
```

Make changes to older commit

```
git rebase -i HEAD^^^
// change from pick to edit, then :wq
git add .
git rebase --continue
```

### 🔍 Cherry Pick

Add some commits to the top of the current branch:

    git cherry-pick hash_commit_A hash_commit_B

### Rewriting History

### 🔍 Revert

Revert the previous commit:

    git revert HEAD
    git commit

Revert the changes from previous 3 commits without making commit:

    git revert --no-commit HEAD~3..

### 🔍 Amend

Amend previous commit:

    git commit --amend

    git commit --amend --no-edit

    git commit --amend -m "New commit message"

[Changing git commit message after push](http://stackoverflow.com/questions/8981194/changing-git-commit-message-after-push-given-that-no-one-pulled-from-remote):

    git commit --amend -m "New commit message"
    git push --force <repository> <branch>

### Reflog

Show reflog:

    git reflog

Get commit:

    git reset --hard 0254ea7

    git cherry-pick 12944d8


### 🔍 Stash

Save a change to stash:

    git stash save "stash name"

    git stash

List all stashes:

    git stash list

Apply a stash:

    git stash pop

    git stash apply

    git stash apply stash@{2}

### 🔍 Rebase

Rebase the current branch onto master:

    git rebase master // rebase the current branch onto master

Continue rebase:

    git rebase --continue

Abort rebase:

    git rebase --abort

### 🔍 .gitignore

Un-track files that have just been declared in .gitignore:

    git rm -r --cached .
    git add .
    git commit -am "Remove ignored files"

### 🔍 Index

Remove untracked files:

    git clean

Remove file from index:

    git reset file

Reset the index to match the most recent commit:

    git reset

Reset the index and the working directory to match the most recent commit:

    git reset --hard

### 🔍 Misc

Get their changes during git rebase:

    git checkout --ours foo/bar.java
    git add foo/bar.java

Get their changes during git merge:

    git pull -X theirs

    git checkout --theirs path/to/the/conflicted_file.php

    git checkout --theirs .
    git add .

    git checkout branchA
    git merge -X theirs branchB

Merge commits from master into feature branch:

    git checkout feature1
    git merge --no-ff master

Find bug in commit history in a binary search tree style:

    git bisect start

    git bisect good

    git bisect bad


## Read more

This is just scratching the surface of what git can do, if you want to learn more, here are some links to get started.

* [Atlassian Git Tutorial](https://www.atlassian.com/git/tutorials/setting-up-a-repository): overview of how to set up a repository (repo) under Git version control
* [git-cheat-sheet](https://github.com/arslanbilal/git-cheat-sheet): Git cheat sheet saves you from learning all the commands by heart.
* [Learn Enough Git to Be Dangerous](http://www.learnenough.com/git-tutorial)
* [Git Workflows for Pros: A Good Git Guide](http://www.toptal.com/git/git-workflows-for-pros-a-good-git-guide)
* [Git from the inside out](https://codewords.recurse.com/issues/two/git-from-the-inside-out): The essay focuses on the graph structure that underpins Git
* [git-game](https://github.com/git-game/git-game): terminal game to test git skills
* [Introduction to Git — talk by Scott Chacon](https://www.youtube.com/watch?v=xbLVvrb2-fY)
* [Git Tutorial — Git Fu With The Command Line](http://www.raywenderlich.com/74258/git-tutorial-intermediate)
* [Git Immersion](http://gitimmersion.com/): The surest path to mastering Git is to immerse oneself in its utilities and operations, to experience it first-hand
* [git-flight-rules](https://github.com/k88hudson/git-flight-rules) Flight rules for git
* [gitflow](https://github.com/nvie/gitflow) Git extensions to provide high-level repository operations for Vincent Driessen’s branching model
* [diff-so-fancy](https://github.com/so-fancy/diff-so-fancy) Good-lookin’ diffs with diff-highlight and more
* [github-cheat-sheet](https://github.com/tiimgreen/github-cheat-sheet) A list of cool features of Git and GitHub
* [git tips](https://github.com/git-tips/tips) Most commonly used git tips and tricks
* [Little Things I Like to Do with Git](https://csswizardry.com/2017/05/little-things-i-like-to-do-with-git/)

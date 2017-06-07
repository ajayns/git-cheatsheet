
# Git Commands

Here's a list of basic Git commands that I use daily for dev. 

## Clone
Starting with the basics, this command makes a copy of the remote to the local machine.

```bash
git clone <repo:url>
```
(The repo looks like: https://github.com/ajayns/github-cmds)

## Commit and Push
This set of commands is used to make changes, save them and push them to the remote, better explained step by step:

First, add the files to git
```bash
git add .
```
(`.` will add all files and folders, so file names in its place can be used to add files specifically)

Commit the changes
```bash
git commit -m 'Add commit message here'
```
(A commit message is a brief account of changes made, like 'Minor fixes', 'Added login component')

Add the remote to the Git repo
```bash
git remote add origin <repo:url>
```

Push the changes to the remote
```bash
git push -u origin master
```
(`origin` can be replaced with other remotes depending where you want to push to. `master` refers the main branch, it can be changed to whichever branch you'd like to push)

Pushing commits needn't be done everytime you make a commit, instead, multiple commits can be push together from local to remote.

## Branch

Create a new branch from current one
```bash
git branch <branch-name>
```

Switch to a branch
```bash
git checkout <branch-name>
```

Create new branch and switch to it
```bash
git checkout -b <branch-name>
```

Delete a branch
```bash
git branch -d <branch-name>
```

Merge a branch to master,
```bash
git checkout master
```
(making sure you are in the master branch)
```bash
git merge <branch-name>
```

## Syncing a forked repo
Clone the remote repo to local system and the following setups will bring the local and remote repos up to date with the source repo.

Add the source remote (where you cloned from) to git, calling it upstream
```bash
git remote add upstream <repo:url>
```

Fetch all branches from upstream
```bash
git fetch upstream
```

Switch to master branch
```bash
git checkout master
```

Rewrite your master branch so that any commits of yours that aren't already in upstream/master are replayed on top of that other branch: 
```bash
git rebase master
```
(These same steps can be done for branches other than master also)

Finally, push the repo to your forked remote to make it up to date
```bash
git push -f origin master
```
(Use the `-f` only when first rebase)


## Delete Changes
To delete all changes made to repo since last commit
```bash
git stash -u
```


# Quick list of commands used in this tutorial:

## One liners

To create a new branch and check it out:

```
git checkout -b <new-branch-name>
```

To stash uncommitted changes, pull in remote updates and pop your changes on
top of them:

```
git pull upstream <branch> --rebase --autostash
```

To pull in a single file from a different branch:

```
git checkout <branch> <path/to/file name>
```

## Configure Remote Pointers

To see what remote repositories are currently configured:

```
git remote -v
```

To add an upstream repository to fetch and push too:

```
git remote add upstream https://github.com/ORIGINAL_REPO_CREATOR/REPO_NAME.git
```

## Sync with Upstream

To fetch upstream changes:

```
git fetch upstream
```

To merge upstream changes from <branch name> into current local branch:

```
git merge upstream/<branch name>
```

To interactively rebase your local commits on top of the updated state of upstream/master:

```
git rebase -i upstream/master
```

To completely reset your branch to the current state of upstream/master and blow away any changes you made locally:

```
git reset --hard upstream/master
git reset --hard SHA
```

## Merge Conflicts

For a custom solution like including parts of a file from the branch you have
and parts of the same file from the branch you are trying to merge with, you will need
to manually edit the file. There are one line commands for favouring a file
as it's represented in one branch or the other.

To select the file as it exists in the branch you are currently in:

```
git checkout --ours <filename>
```

To select the file as it exists in the branch you are attempting to merge into
your branch:

```
git checkout --theirs <filename>
```

Then you would continue by:

```
git add <filename>
git merge --continue
```

### NOTE:

If you are starting out with a rebase instead of a merge, the ours and
theirs flags are reversed. [This](https://nitaym.github.io/ourstheirs/)
explanation makes things pretty clear.

## Cherry-picking

To merge a single commit to a branch you are working within, find the hash of
the commit you want to merge with `git log` and cherry-pick it:

```
git cherry-pick <hash of commit>
```

## Utilizing log and reflog

`log` and `reflog` can be incredibly valuable tools when you want to remove
commits, go back in time or recover something you accidentally deleted.

To check out your commit history:

```
git log
```

To checkout git history in this repo:

```
git reflog
```

### Note:

Hashes in either `git log` or `git reflog` can be used in lieu of branch names
to rebase and/or reset and/or cherry-pick.

## Change Local Commit History

### NOTE

Many of these commands will require a push --force when syncing with anything
on github. Be very careful using this command as it can erase your previous
work and destroy PR's/history.  Sometimes it is warranted, just be careful!
Also, consider using
[--force-with-lease](https://developer.atlassian.com/blog/2015/04/force-with-lease/)


To manipulate the history of the last 5 commits interactively:

```
git rebase -i HEAD~5
```
To, for example, squash the last 5 commits non-interactively:

```
git reset --soft HEAD~5
git commit -m 'new commit message'
```

To reset the base of your branch to upstream/master, remove your comit history but keep your local changes in their current state:

```
git reset upstream/master
```
* you will need to add your changes back and commit them again once you do this.

# For Big Oopsies

Check the logs and see if you can reset (--HARD or --soft) to a previous SHA:

```
git log
```

# For Even Bigger Oopsies

If all else fails, git reflog can probably (hopefully) save you:

```
git reflog
```

You can use it to reset to the state of your repo before the bad thing
happened.


## More Git Resources

- If you're in a situation you don't know how to fix, see if you can find a
soltuion in [Git Choose Your Own Adventure](https://sethrobertson.github.io/GitFixUm/fixup.html)


- It's always good to [Avoid Git Disasters](https://randyfay.com/content/avoiding-git-disasters-gory-story)

- Visual learners may enjoy [Common commands and visual representations](https://marklodato.github.io/visual-git-guide/index-en.html)

- Here's a useful [flow chart to git-pretty](https://www.dev-metal.com/made-mess-git-heres-flowchart-guideline-fix/)

- For a laugh, check out some [Terrible ideas in git](https://www.linuxjournal.com/content/terrible-ideas-git) or
[watch the video](https://www.youtube.com/watch?v=Ya5ZSNGl3G4)



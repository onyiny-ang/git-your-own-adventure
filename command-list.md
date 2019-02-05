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
git reset --HARD upstream/master
```

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



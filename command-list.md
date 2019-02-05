# Quick list of commands used in this tutorial:

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



## More Git Resources

#### If you're in a situation you don't know how to fix, see if you can find a
soltuion in [Git Choose Your Own Adventure](https://sethrobertson.github.io/GitFixUm/fixup.html)


#### [Avoiding Git Disasters](https://randyfay.com/content/avoiding-git-disasters-gory-story)

#### [Common commands and visual representations](https://marklodato.github.io/visual-git-guide/index-en.html)

#### Useful [flow chart to git-pretty](https://www.dev-metal.com/made-mess-git-heres-flowchart-guideline-fix/)

#### For a laugh, check out some [Terrible ideas in
git](https://www.linuxjournal.com/content/terrible-ideas-git) for a laugh or
[watch the video](https://www.youtube.com/watch?v=Ya5ZSNGl3G4)



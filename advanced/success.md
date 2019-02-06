# Your Merge was Successful

Congratulations once again!

![Woo](https://media.giphy.com/media/TdfyKrN7HGTIY/giphy.gif)

But keep in mind, this state could change. If another PR (pull request) is
merged before yours, it could still result in a merge conflict.

Anyway, we'll come back to that in a little while.
For now, let's move on to cherry-picking and some other fun things.

Create a new branch, let's call it `cherry`.

```
git checkout -b cherry
```

Now make a whole bunch of random files and commit them one by one.
For example:

```
cd story
touch once upon a time
```

Make sure you have at least 5 random files with at least one character in each file, add each file and commit it.
For example:

```
echo this is just an example > a
git add a
git commit -m "do not actually push this"
```

In a real life, you would have made actual changes on an actual branch that perhaps even took a long time. When you were working on these changes, they seemed totally unrelated and/or maybe were just indicators of where you stopped before lunch or dinner. Whatever that case, now there's a lot of unneccessary bulk in your git history, and some commits that don't really make much sense. Let's clean that up before we try to push it to upstream.

First, take a look at all those unorganized commits

```
git log
```
Notice that each commit has a unique sha. Also the author and time as well as the commit message are all
recorded for all of your history in this branch. That seems handy! Cound how
many commits you've had since your started this branch? Remember that number. (tip: q exits out of
the log)

Now let's try an interactive rebase.

```
git rebase -i HEAD~<that number>
```

Since these files are completely independent of one another and were committed
individually, you have free reign over your rebase. Try dropping a commit, try
squashing a commit (replace `pick` with `d` and `s` respectively on any given
lines) read the other options and try some others out too if you like. Make
sure you leave some of your commits alone for the latter part of the exercise.

Save and exit the editor, edit, save and exit the commit messages.
You should have a message that your rebase was successful. Now, let's check out
the log again:

```
git log
```

Notice anything different?

Well, now that your branch is all cleaned up, you're good to push it upstream,
right?

It seems that in the time since you made those changes, someone else committed
something else that changed the direction of what the upstream branch looked
like and now you'd be embarassed to commit this branch upstream.

There's still one commit that's good though!!

Let's go back to master and get that commit synced before anything else
happens.

```
git checkout master
```

Now we want to use the `cherry-pick` command to pull in our single commit.
Choose the SHA from your favourite commit from the `cherry` branch and type the
following command:

```
git cherry-pick <SHA>
```

Now, check out your log again. You should see that your commit from the cherry
branch is at the top of the log on master.

Easy Peasy.

![cherry-pick](https://media.giphy.com/media/Gj8qB0PsQgBuE/giphy.gif)



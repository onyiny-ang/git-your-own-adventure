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
touch once upon a time in git
```

Make sure you have at least 5 random files with at least one character in each file. Add each file and commit it.
For example:

```
echo this is just an example > a
git add a
git commit -m "do not actually push this"
```

In real life, you would have made actual changes on an actual branch that perhaps even took a long time. When you were working on these changes, your commits may have seemed to happen at logical points in the development or maybe were just indicators of where you stopped before a break. Whatever that case, now there's a lot of unneccessary bulk in your git history, and some commits that won't really make much sense when they're merged upstream. Ideally, you want your commits to be indicative of a particular feature, bug fix or change so that it's easy to review and roll-back to if there are problems later on in development. Let's clean up your commit history before we try to push it upstream.

First, take a look at all those unorganized commits

```
git log
```
Notice that each commit has a unique SHA. The author and time as well as the commit message are also all
recorded for each commit and all of your history in this branch. That seems handy! Count the number of commits you've made since you checked out this branchr. Remember that number. (protip: q exits out of
the log)

Now let's try an interactive rebase.

```
git rebase -i HEAD~<that number>
```

Since the files you just committed to this branch are completely independent of one another and were committed
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

If you squashed or dropped any of your commits, you _should_ notice that there
are less commits in your log. Now that your branch is all cleaned up, you're good to push it upstream,
right?

Unfortunately, it seems that in the time since you made those changes, your arch-nemesis committed
something else that changed the direction of what the upstream branch looked
like and now you'd be embarassed to commit this branch upstream.

There's still one commit that's good though!! Get it in there before your
arch-nemesis ruins that just like everything else they ruin.

Let's go back to master and get that commit synced!!

```
git checkout master
```

Now we want to use the `cherry-pick` command to pull in our single commit.
Choose the SHA of your favourite commit from the `cherry` branch and type the
following command:

```
git cherry-pick <SHA>
```

Now, check out your log again. You should see that your commit from the cherry
branch is at the top of the log on master.

Easy Peasy.

![cherry-pick](https://media.giphy.com/media/Gj8qB0PsQgBuE/giphy.gif)



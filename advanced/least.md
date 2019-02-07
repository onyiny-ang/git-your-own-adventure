# OOPS

Oh. Did you forget to commit that?

I could of sworn I wrote the commit line. . .why don't you navigate to your
pull request and see what happened. It's still there right? No?

Well, poop.

![fine](https://media.giphy.com/media/NTur7XlVDUdqM/giphy.gif)

This situation isn't even _that_ bad. You still have all your commits, they're
just not committed and now your PR is gone forever, but it's not the end of
the world, it just makes you look like a bit of a n00b.

So, let's really get oursevles into trouble:

```
git reset --HARD upstream pull/5/head:arch-nemesis
```

Now all of our commits are gone and we're back at the start of that evil
branch.

Let's pretend that's not what you wanted to do. In this case, `git log` isn't
going to help you very much because, well, check it out.
This time we need to do something different.

```
git reflog
```

See if you can find the hash that corresponds to the point in history just before you did the
`push --force-with-lease` on the previous page. Got it?

Now, try this:

```
git reset --hard <the-aforementioned-hash>
git status
```

![Ta da!](https://media.giphy.com/media/12NUbkX6p4xOO4/giphy.gif)

Now if you really wanted to, you would just add, commit and push these again,
and you'd be right back where you were supposed to be.

And in the worst case scenario, you have your backup branch, right?
So you could have just made a new pull request from that branch.

Instead, lets stash our changes and start again at master.

```
git stash
git checkout master
git fetch upstream
git merge upstream/master
git checkout -b my-story
git stash apply
```

Remove the "This line is very important and can't be overwritten." line from
`/story/once-upon-a-git-repo.md` and
then add and commit your changes.

[HOORAY!](congratulations.md)

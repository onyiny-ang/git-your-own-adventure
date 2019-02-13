# OOPS

Oh. Did you forget to commit that?

I could of sworn I wrote the commit line. . .why don't you [navigate to your
pull
request](https://github.com/onyiny-ang/git-your-own-adventure/pulls) and see what happened. It's still there right? No? Is it in the [closed list](https://github.com/onyiny-ang/git-your-own-adventure/pulls?q=is%3Apr+is%3Aclosed)

Well, poop.

![fine](https://media.giphy.com/media/NTur7XlVDUdqM/giphy.gif)

Remember what I said about `--force` having destructive power?
This situation isn't even _that_ bad. You still have all your commits, they're
just not committed and now your PR is gone forever, but it's not the end of
the world, it just makes you look like a bit of a n00b.

So, let's really get oursevles into trouble:

```
git reset --hard 1e0b2107924d321ba742985b1f45f973b27f0fb7
```

Now all of our commits are gone and all that's left is the stuff we didn't want
from that evil branch.

Let's pretend that's not what you wanted to do. In this case, `git log` isn't
going to help you very much because, well, check it out.

<details>
  <summary>Assuming you know how to check logs at this point</summary>

```
git log
```

</details>

This time we need to do something different.

```
git reflog
```

See if you can find the hash that corresponds to the point in history just before you did the
`push --force-with-lease` on the previous page. This is probably going to
appear as the first 7 characters of the commit on the left hand of the screen. Got it?

Now, try this:

```
git reset --hard <the-aforementioned-hash>
git log
```

![Ta da!](https://media.giphy.com/media/12NUbkX6p4xOO4/giphy.gif)

Now you just need to redo what you had done on the previous page.

<details>
  <summary>In case you don't remember--but don't actually do it!</summary>

```
git log (to get the commit SHA)
git reset <appropriate SHA>
git add <the files you want to add>
git commit -m "appropriate commit message"
git push --force-with-lease arch-nemesis
```

</details>


If you really wanted to, you would just add, commit and push these again,
and you'd be right back where you were before the big OOPS.

And in the worst case scenario, you have your backup branch, right?
So you could have just made a new pull request from that branch.

Instead, lets reset to the commit just before the one we `--hard reset` to.
This will pop our most recent commit off the top. Then we can stash it and start again at master.

```
git reset <SHA just under the most recent commit>
git stash
git checkout master
git fetch upstream
git merge upstream/master
git checkout -b my-story
git stash apply
```

Remove the "This line is very important and can't be overwritten." line from
`/story/once-upon-a-git-repo.md` or ensure that your original
`once-upon-a-git-repo.md` changes are incorporated with a `git checkout` from
your `new-story` branch
then add and commit your changes to the my-story branch.
Once you've done this, open a PR against the upstream master branch.

[HOORAY!](congratulations.md)

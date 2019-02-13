# The Ending

Every good story has an ending.

Now that you've fixed up the arch-nemesis branch, without changing your branch or anything about your branch, write an ending to
your story or to a story someone else wrote!

(You can see if anything you like has been merged to the upstream new-story
branch, cherry pick that commit and start there if you want a challenge)

Create a new file in the `story` directory, call it something like `the-volcano-ending.md`. Write an appropriate
ending to the story and then create a relative link to it in the file that the
first story branches to. You could also make a [relative link (#4 in the list)](https://github.com/brock-women/git-your-own-adventure/blob/master/advanced/story-time.md) in the original
`once-upon-a-git-repo.md` story so the person reading the story can choose to
go straight to the end if they want.


<details>
  <summary>Add it onto your branch, commit the changes and push to your branch</summary>

```
git add .
git commit -m "ending"
git push origin arch-nemesis
```

</details>

Now, there might be a lot of commits at this point. Let's clean up this branch.

Before you do anything, let's make a backup.

```
git checkout -b backup
```

Wait. Didn't that just create a new branch? Yep. But the key is, that branch is
at exactly the point that arch-nemesis is at. If you continue to develop on
arch-nemesis, you still have this back up from this moment in development. If
your backup is really really important, you could also push it to `origin` so
there is a backup on the internet too, but this isn't really necessary for our
example.

Switch back to arch-nemesis:

Let's just pretend that all the additions to the story we made were ours and not potentially from
other people (they may all be ours anyway).

But you know what? We don't need to incorporate Stomae Lamelle's changes at
all. We should probably just delete them and pretend they didn't happen. Don't
feed the trolls, right?

So, let's reset our branch to the commit just before stroma-lamellae's changes.
Find stroma-lamellae's commit and select the one just before it.

```
git log
git reset  1e0b2107924d321ba742985b1f45f973b27f0fb7

```

Keep in mind that you can use `upstream/<branch name>` to reset or the hash
associated with the point in the repo you want to reset to.

If you do

```
git status
```

You should see that all of your changes are now unstaged and sitting on top of
your branch which is rolled back to stroma-lamellae's changes. This allows you
to easily commit all of your changes in one go.

So add back only the files you want to appear in your PR:

```
git add <specific files you want to add>
git push --force-with-lease origin arch-nemesis
```

[Good job](least.md)


# The Ending

Every good story has an ending.

Without changing your branch or anything about your branch, write an ending to
your story or to a story someone else wrote! You should link to your ending from the story line who's ending you are writing.
(You can check out if anything you like has been merged to the upstream new-storyline
branch, cherry pick that commit and start there if you want a challenge)

Create a new file, call it something like `the-volcano-ending.md`. Write an appropriate
ending to the story and then create a relative link to it in the file that the
first story branches to. You could also make a relative link in the original
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
arch-nemesis, you still have this back up from this moment in development.

Switch back to arch-nemesis:

Let's just pretend that all the commits we made were ours and not potentially from
other people (they may all be ours anyway).

Now, let's reset our branch back to the start of stroma-lamellae's changes.

```
git reset upstream pull/5/head:arch-nemesis

```

Keep in mind that you should be able to do the same thing by finding the hash
associated with this point in the repo.

If you do

```
git status
```

You should see that all of your changes are now unstaged and sitting on top of
your branch which is rolled back to stroma-lamellae's changes. This allows you
to easily commit all of your changes in one go.

So:

```
git add .
git push --force-with-lease origin arch-nemesis
```

[Good job](least.md)


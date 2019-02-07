# Arch-nemesis Branch

Navigate in your browser to the [upstream
repo](https://github.com/onyiny-ang/git-your-own-adventure/pulls)

What the. . . .checkout pull request
[#5](../pull/5)

Who the heck is Stromae Lamelle? How dare they speak so poorly of github! They
are an insult to house plants everywhere!

Click on the `Files Changed` tab at the top of their pull request.
You can see that they have removed the command-list of useful commands AND the
story about Indigo that you contributed to earlier.

![I know](https://media.giphy.com/media/E7iIfUlWHBmh2/giphy.gif)

Well. Two can play at this game Stromae Lamelle, if that _is_ your real name.
First of all, thumbs down that PR. Let the repo owner know what you think of
these shenanigans.

Then you can actually checkout Stromae Lamelle's branch locally.

```
git fetch upstream pull/5/head:arch-nemesis
git checkout arch-nemesis
```

Check to make sure that the files in your new branch match the arch-nemesis
branch that the PR is on.

Ok. First of all, we need to put the command-list back in there. You can
actually do this easily by checking out a particular file.

```
git checkout master command-list.md
```

This will select the command-list from the master branch and put it in the
arch-nemesis branch.

Do the same for the other files Stromae Lamelle has destroyed, and cherry pick
your last commit onto the cherry branch on top of it.

<details>
  <summary>You don't still need the instructions do you?</summary>

```
git checkout master story/
git cherry-pick SHA
```

</details>

Now, to top it off, why don't you also cherry pick your commit from your first
pull request as well? You might as well roll everything into a final commit.

<details>
  <summary>Hint: It's another cherry pick</summary>

```
git cherry-pick SHA
```

</details>


Great. Now, push it and  navigate to github and open a Pull request, name it something snarky and
tag @stroma-lamellae in it. That jerk.


<details>
  <summary>git command spoiler</summary>

```
git push origin arch-nemesis
```

</details>


[One more thing](last-but-not-least.md)

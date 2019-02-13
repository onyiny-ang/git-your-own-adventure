# Arch-nemesis Branch

Navigate in your browser to the [upstream
repo](https://github.com/onyiny-ang/git-your-own-adventure/pulls)

What the. . . .checkout pull request
[#5](https://github.com/onyiny-ang/git-your-own-adventure/pull/5)

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
Navigate to the root of the directory and then type:

```
ls -l
```

Ok. We've confirmed this matches what we saw in Stromae Lamelle's branch. First of all, we need to put the command-list back in there. You can
actually do this easily by checking out a particular file. Since the
command-list.md still exists in your master branch, you can move it to this
branch like this:

```
git checkout master command-list.md
```

This will select the command-list from the master branch and put it in the
arch-nemesis branch. You can list the files in the directory again to verify if
you want.

Do the same for the other files Stromae Lamelle has destroyed. Add and commit
them. This should include the changes you just made with your cherry pick.

<details>
  <summary>If you still need the instructions click the arrow</summary>

```
git checkout master story/
git add .
git commit -m "Fighting evil one git checkout at a time"
```

</details>


Now, to top it off, why don't you also cherry pick your commit from your first
pull request as well? You might as well roll everything into a final commit.

<details>
  <summary>Hint: It's another cherry pick</summary>

```
git checkout new-story
git log
<copy the commit SHA>
git checkout arch-nemesis
git cherry-pick SHA
```

</details>



Great. Now, push it. You should get a message that tells you where to navigate to on github to see your commits. It will probably be something like: `https://github.com/<your-user-name>/git-your-own-adventure/pull/new/arch-nemesis`. Navigate there on github and open a Pull request, name it something snarky and
tag @stroma-lamellae in it. That jerk.


<details>
  <summary>git command spoiler</summary>

```
git push origin arch-nemesis
```

</details>



[One more thing](last-but-not-least.md)

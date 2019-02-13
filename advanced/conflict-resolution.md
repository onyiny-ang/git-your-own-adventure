# You Have A Conflict

This shouldn't be a problem. Probably someone beat you to the punch and has
already added to the story. You can resolve this by pulling in the changes from
upstream and rebasing on top of them.

```
git fetch upstream
git rebase -i upstream/new-storyline
```
This will open an editor with your commit message. You can simply save and
close the editor, or if you want to change your commit message, you can do that
too.

When you close the editor, you should see a message like this:

```
Auto-merging story/once-upon-a-git-repo.md
CONFLICT (content): Merge conflict in story/once-upon-a-git-repo.md
error: could not apply <your commit hash... your commit message>
Resolve all conflicts manually, mark them as resolved with
"git add/rm <conflicted_files>", then run "git rebase --continue".
You can instead skip this commit: run "git rebase --skip".
To abort and get back to the state before "git rebase", run "git rebase --abort".
```

Congratulations, you've got your first merge conflict!

![MERGE](https://cdn-images-1.medium.com/max/1600/1*McV_rylg2T2Y6dOb1x3wCw.gif)


To resolve this, you will need to read the message and find out which file or
files are causing the problem. In this case, it's
story/once-upon-a-git-repo.md. So open it with your editor.

Inside the file, if you scroll down, you will eventually come to:

```
<<<<<<<<<< HEAD

somebody else's code code code
======
my code code code

>>>>>>>>>> <commit sha> ... <commit message>
```

The code in between that block is where the problem is. You and someone else
have both altered the same line. To resolve the merge conflict, you need to
select the code that you want to keep within the block and remove the `<<<`,
`===` and `>>>` tags. In our case, we probably want to keep both our code and
their code, so go ahead and edit the file to keep both lines of code and remove
the indicators. When you're done, add the changes with:

```
git add .
```

With the merge conflict resolved, you should be able to continue your rebase.

```
git rebase --continue
```

Which will allow you to once again, edit your commit message. In this case,
because we kept the changes upstream, we could change our commit message to
reflect that.
If there are no errors, you can push to your branch at origin again. . .

```
git push origin new-story
```

## Perfect!

--wait, what? it didn't work?? Oh. Did you get this pesky error?

```
 ! [rejected]        new-story -> new-story (non-fast-forward)
error: failed to push some refs to 'https://github.com/<your-user-name>/git-your-own-adventure.git'
hint: Updates were rejected because the tip of your current branch is behind
hint: its remote counterpart. Integrate the remote changes (e.g.
hint: 'git pull ...') before pushing again.
hint: See the 'Note about fast-forwards' in 'git push --help' for details.
```

Right. This calls for the heavy artillery.

Before we proceed.

BE WARNED. THIS COMMAND CAN BE DESTRUCTIVE.

It's time to force that push.

`--force` is kind of like the sudo of git. So consider this the obligatory:
"With great power comes great responsibility."

![don't try this at home](https://cdn-images-1.medium.com/max/1600/1*h_k_S8AKyK84BHrNZsaQOA.png)

Try that again, but this time:

```
git push --force-with-lease origin new-story
```
Now open or refresh the window pointed to the upstream PR you made.

Wooo! No more merge conflicts!

![Yes](https://memegenerator.net/img/instances/68506713.jpg)

[Look at me, conflict free!](success.md)

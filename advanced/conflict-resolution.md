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

To resolve this, you will need to read the message and find out which file or
files are causing the problem. In this case, it's
story/once-upon-a-git-repo.md. So open it with your editor.

Inside the file, if you scroll down, you will eventually come to:

```
>>> HEAD

code code code

<<< TAIL
```

The code in between that block is where the problem is.
In our case, we probably want to keep both.


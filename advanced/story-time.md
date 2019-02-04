# Story Time

To exemplify some of the more advanced git commands, we're going to
collectively write a story.

The rules for adding to the story are simple.

1. From the root of your cloned git repo, in your terminal, navigate to the
   story directory.

   ```
   cd story
   ```

2. Open the `once-upon-a-git-repo.md` file with your favourite text editor or
   IDE.

3. Be creative. Do not remove anything from the story but add at least 1
   relative link to a new file within the `story` directory. Within the
   `once-upon-a-git-repo.md` file, this is done with the following markdown:

   ```
   [Relative Link Name](file-name.md)
   ```

4. Close the file and create a new file with the name you linked to. Add at
   least one sentence to the file to continue the story. Try to keep the story
   at least somewhat consistent. Note: Inappropriate storylines will be
   moderated at upstream.

5. When you have completed the story in your file, save it and close it.

6. Now you will push your changes to your fork.

```
git add .
git commit -m "Adds a new path to the story"
git push origin master
```

7. Open a duplicate window in your web browser to see your commits.

8. Click on the `pull request button`

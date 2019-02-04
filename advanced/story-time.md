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

3. Be creative. Do not remove anything from the story except the line "<What happens next? Give Indigo some options>
". In its place, add at least 1 relative link to a new file within the `story` directory. In the
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

7. Open a duplicate window in your web browser and navigate to the root of the
   git-your-own-adventure repo in your fork to see your commits. This should
   show up as something like "This branch is 1 commit ahead of
   onyiny-ang:master" and you should see the name of the pull request beside
   the 'story' directory.

8. Click on the `pull request` button on the right, just above the files in the
   repo. You will see a Green `Create pull request` button on the next page.
   Click on that.

9. Leave a concise but descriptive comment about why your pull request is an
   important or necessary addition to the repo and click the green button to
   create a pull request again.

10.

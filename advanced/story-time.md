# Story Time

To exemplify some of the more advanced git commands, we're going to
collectively write a story.

The rules for adding to the story are simple.

1. From the root of your cloned git repo, in your terminal, navigate to the
   story directory.

   ```
   cd story
   ```

2. Create a new branch where you will be making your commits. You can do this
   with one command:

   ```
   git checkout -b new-story
   ```

3. Open the `once-upon-a-git-repo.md` file with your favourite text editor or
   IDE.

4. Be creative. Do not remove anything from the story except the line "<What happens next? Give Indigo some options>
". In its place, add at least 1 relative link to a new file within the `story` directory. In the
   `once-upon-a-git-repo.md` file, this is done with the following markdown:

   ```
   [Relative Link Name](file-name.md)
   ```

   So, as an example, you could add:

   ```
   [Indigo clicks the notification icon](icon.md)
   ```


5. Close the file and create a new file in the `story` directory with the name you linked to. Add at
   least one sentence to the file to continue the story. 
   
   In keeping with the above example, you could create a new file called icon.md: `touch
   icon.md`
   Try to keep the story at least somewhat consistent. Note: Inappropriate storylines will be
   moderated upstream.

6. When you have completed the story in your file, save it and close it.


7. Now you will push your changes to your fork.

```
git add .
git commit -m "Adds a new path to the story"
git push origin new-story
```

8. Open a duplicate window in your web browser and navigate to the root of the
   git-your-own-adventure repo in your fork. Click on the `Branch` menu button
   just above your source code and select the `new-story` branch to see your commits. This should
   show up as something like "This branch is 1 commit ahead of
   onyiny-ang:master" and you should see the name of the pull request beside
   the 'story' directory.

9. Click on the `pull request` button on the right, just above the files in the
   repo. You will see a Green `Create pull request` button on the next page.
   Make sure your base repository is: `onyiny-ang/git-your-own-adventure` and
   base is: `new-storyline` and the head repository is
   `your-account/git-your-own-adventure` and compare is: `new-story`. It should
   say `Can't automatically merge`, but don't worry about that for now.

10. Change the title and leave a concise but descriptive comment about why your pull request is an
   important or necessary addition to the repo.

11. Click on the green Create pull request button.
After doing this, there are two possibilities:

1. The pull request is ready to merge. In this case, wait patiently until the
   PR merges. You may need to get the attention of the original author of the
   repo to take a look at the PR's that are ready to merge.
   ![please merge
   me](http://null.perl-hackers.net/wp-content/uploads/2015/01/19228517.jpg)

   Anyway, [CONGRATULATIONS ON YOUR SUCCESSFUL PR](success.md)

2. The pull request has conflict. This is a pretty common scenario and most
   often occurs because you are trying to make a PR over top of code that has
   become out of date while you were working on it.
   ![merge conflicts](https://img.devrant.com/devrant/rant/r_477918_w6Khj.jpg)

   Never fear, we can mitigate
   this problem. [MERGE CONFLICT RESOLUTION](conflict-resolution.md)

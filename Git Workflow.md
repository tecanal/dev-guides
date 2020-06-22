# TeCanal Git Workflow

If you want to learn more about Git, try this [interactive tutorial](https://learngitbranching.js.org/). It might teach you a bit more than what will be needed during your internship, but Git is a great thing to know anyway.

**Remember: Never push directly to master.**  
This will always be done by creating a pull request, so that Rees can review your code before it gets merged into the project.

## Workflow
1. If your branch has not been created yet, create one with ```git branch insert-project-name-here```.
2. To go to your branch in Git, use ```git checkout branch-name```.
3. When you are on your branch, do not modify any other files other than the ones in your project folder. Otherwise you will have merge conflicts, which will be confusing and annoying to fix.
4. Use ```git add file-name.ext``` to "track" files with Git. This means that the files are ready to be committed.
5. Then use ```git commit -m "Brief description of changes"```, to commit your changes. The -m flag stands for message, as in commit message. When files are committed, this means the changes are ready to be "pushed" to the server.
6. If you are pushing your branch for the first time, use ```git push -u origin branch-name```, otherwise just use ```git push```. This will upload your changes to the server.
7. To keep your branch up-to-date, use ```git fetch -p origin && git merge master```. 
    * The first part will pull down any changes made to origin (the repository). The -p flag stands for prune which means that it will get rid of any branches that get removed around the repository.
    * The second part will merge code from master into your branch, to keep it up-to-date.
8. When you're ready for your changes to go int othe master branch, you can create a pull request in the "Pull Requests" tab. This means that someone will review your changes and approve it, or tell you to go back and make a few more changes.

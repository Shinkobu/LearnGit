# LearnGit

How to Squash Commits in Git?

https://www.geeksforgeeks.org/how-to-squash-commits-in-git/




# how to delete all commit history in github? #

https://stackoverflow.com/questions/13716658/how-to-delete-all-commit-history-in-github
Deleting the .git folder may cause problems in your git repository. If you want to delete all your commit history but keep the code in its current state, it is very safe to do it as in the following:

Checkout/create orphan branch (this branch won't show in git branch command):

git checkout --orphan latest_branch
Add all the files to the newly created branch:

git add -A
Commit the changes:

git commit -am "commit message"
Delete main (default) branch (this step is permanent):

git branch -D main
Rename the current branch to main:

git branch -m main
Finally, all changes are completed on your local repository, and force update your remote repository:

git push -f origin main
PS: This will not keep your old commit history around. Now you should only see your new commit in the history of your git repository.
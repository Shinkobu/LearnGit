# LearnGit

How to Squash Commits in Git?

https://www.geeksforgeeks.org/how-to-squash-commits-in-git/

1. Есть история с лишними коммитами, которые нужно схлопнуть
2. git rebase -i HEAD~4
3. где 4 это глубина по количеству затрагиваемых коммитов, а -i это интерактивный режим
4. в интерактивном режиме напротив коммитов, которые нужно схлопнуть указываем s или squash
5. далее пишем :wq
6. Далее редактируем комментарии, которые будут в коммите, куда всё схлопнется
7. далее пишем :wq
8. git push -f origin main
9. это принудительный push на гитхаб репозиторий, который перепишет историю коммитов



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
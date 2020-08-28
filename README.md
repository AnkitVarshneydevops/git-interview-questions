# git-interview-questions
Q-1 Why we need git? What makes git unique from other tools like SVN?

Answer: Git is the most commonly used version control system. 
Git tracks the changes you make to files, so you have a record of what has been done, 
and you can revert to specific versions. 
Git also makes collaboration easier, allowing changes by multiple people to all be merged into one source.

Q-2 Let's say I have maven repo cloned on to my local, did some changes and I have build the code now 
target folder will be generated. So now when I do git operations like git add, git commit or 
any other git operation target folder should not be considered, how would you achieve the same?

Answer: you can achieve by gitignore, the target folder which has artifacts can be ignore.

Q-3 How clone specific branch in git?
Answer: git clone -b <branch-name> --single-branch <git-url> ; git branch -a

Q-4 git push vs git fetch with scenario

Answer: Git pull command basically pulls any new changes or commits from a branch from your central
repository and updates your target branch in your local repository.
Git fetch is also used for the same purpose, but its slightly different form Git pull. When you trigger a
git fetch, it pulls all new commits from the desired branch and stores it in a new branch in your local
repository. If we want to reflect these changes in your target branch, git fetch must be followed with a
git merge. Our target branch will only be updated after merging the target branch and fetched
branch. Just to make it easy for us, remember the equation below:
Git pull = git fetch + git merge

Q-5 How to delete branch locally?

Answer: git branch -d localBranchName

Q-6 How to delete branch remotely?
Answer: git push origin --delete remoteBranchName

Q-7 How can I determine the URL that a local Git repository was originally cloned from?
Answer: git config --get remote.origin.url or git remote show origin

Q-8 What is Git Cherry-Pick?
Answer: git cherry-pick is a powerful command that enables arbitrary Git commits to be picked by reference and appended to the current working HEAD. 
Cherry picking is the act of picking a commit from a branch and applying it to another. git cherry-pick can be useful for undoing changes. 
For example, say a commit is accidently made to the wrong branch. You can switch to the correct branch and cherry-pick the commit to where it should belong.

Q-9 What is Git Blame?

Answer: git blame is a very good tracking command for Git. 
git blame shows the author information of each line of the project’s last modified source file. 
You can find the author name, author email, the commit hash etc of the last modified source file line by line.


Q-10) How do we know in Git if a branch has already been merged into master?
Answer: git branch --merged
        The above command lists the branches that have been merged into the current branch.
        git branch --no-merged
        This command lists the branches that have not been merged.

Q-11) What is difference between git Rebase and git Merge?

Answer: Rebasing and merging are both designed to integrate changes from one branch into another branch but in different ways.
For ex. let’s say we have commits like below, the merge will result as a combination of commits, 
whereas rebase will add all the changes in feature branch starting from the last commit of the master branch:
When you do rebase a feature branch onto master, you move the base of the feature branch to master branch’s ending point.
Merging takes the contents of the feature branch and integrates it with the master branch. 
As a result, only the master branch is changed. The feature branch history remains same.
Merging adds a new commit to your history.

Q-12) When to rebase? When to Merge?
Answer: If the feature branch you are getting changes from is shared with other developers, rebasing is not recommended, 
because the rebasing process will create inconsistent repositories. For individuals, rebasing makes a lot of sense.
If you want to see the history completely same as it happened, you should use merge. Merge preserves history whereas rebase rewrites it.
Rebasing is better to streamline a complex history, you are able to change the commit history by interactive rebase. 
You can remove undesired commits, squash two or more commits into one or edit the commit message.
Rebase will present conflicts one commit at a time whereas merge will present them all at once. 
It is better and much easier to handle the conflicts but you shouldn’t forget that 
reverting a rebase is much more difficult than reverting a merge if there are many conflicts. 
You can find details of a basic rebase process from git — Basic Rebase .

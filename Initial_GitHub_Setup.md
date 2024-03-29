------------------------------------------------------------------------------------------------------
First we have to make the path or folder should be git enabled for that we need to initialize first

cd c:\gitHubProjectPath 
git init

then to Config our Email and  password Globally
1) git config --global user.name "John Doe"
2) git config --global user.email johndoe@example.com

then if you want to change the user name and email then you can change the user name and email

1) git config user.name "John Doe"
2) git config user.email johndoe@example.com

Now we  can create the project and push to git (or)
Clone the repository 

git clone gitUrltobecloned
ex: git clone https://github.com/venk120soft/github-learnings-commands.git
That means we are taking the whole project into our local Computer. Once the clone is done we can able to see all the files in our local system 

Now do the changes, add the files modified the files delete the files what ever you do 
git add fileName (or)
To add all files at a time
git add -a 

what ever we do the changes to files we are indexing them then once we indexed everything we are making the commit
```
git commit -m "Describe what you did in this commit" 
```
then push to the repository by using below command
```
git push
```
if it ask for credentials we have to mention then it will be pushed into 

# Working with branches
Creating branch
```
git branch sampleBranchName
```
Now the branch is created, then now all the master code is available in sampleBranchName branch
we can check all the branches for the repository by using below command

```
git branch 
```
this will list out all the branches for that repository,  in this the current working branch name will be heighlated in grean color

How do you switch to the branches?
Once the branch is created then want to work on that branch we have to switch to that branch. for that 
```
    git checkout branchWeWantToWork
    ex: git checkout sampleBranchName
```
// creating new branch from current branch and switched to that branch
```
git checkout -b newBranchName
```
// creating the new branch from perticular branch(origin/release/2019.5.2) nad switching to that branch
```
git checkout -b user/v-vechun/FixForCustomerLockboxPageLoadingInReactV2 origin/release/2019.5.2
```
C:\PAP\M365AdminUX>git push
fatal: The upstream branch of your current branch does not match
the name of your current branch.  To push to the upstream branch
on the remote, use

    git push origin HEAD:release/2019.5.2

To push to the branch of the same name on the remote, use

    git push origin user/v-vechun/FixForCustomerLockboxPageLoadingInReactV2

To choose either option permanently, see push.default in 'git help config'.
"
We have to use git push origin user/v-vechun/FixForCustomerLockboxPageLoadingInReactV2

Then  if you do git push origin HEAD:release/2019.5.2 it will directly pushed to that branch we dont do that.
This will switch the branch to sampleBranchName branch  do the changes you need .
Then push the newly created branch to the upstream by using below command

 git push --set-upstream origin testBranch

Every newly created needs to pushed to the Origin

this may ask for the credentials we have to keyin the credentials, 
Then We can commit and push our changes to the newly created branch.
git branch newBranch2

Fork Means Having full copy of source code into our own account, So that even though the original code is deleted, we will have a copy of it in our code.

How to undo the changes for a file(s)?
To undo the changes for a specific file we can use 
git checkout fileName

For all files we can use
git checkout .
---------------------------------------------------------------------------------------------------------------------------------------
How to delete or undo the changes you have done on the specific branch?
by using git stash command we can delete all the changes we have made, these changes will be saved in one place we can also apply these changes to same branch.

How to apply the undo changes to your branch?
by using git stash apply

how to list out all the git stash history?
by using git stash list

how to re write or ammend the file changes to the just created commit?
by using git commit --amend -m "updated commit message here".
git commit --amend lets you take the most recent commit and add new staged changes to it. You can add or remove changes from the Git staging area to apply with a --amend commit

To Remove Untracked files from the Local repository
git clean -f -d (or) git clean -fd
To remove ignored files, run git clean -f -X or git clean -fX.
To remove ignored and non-ignored files, run git clean -f -x or git clean -fx

To remove local commits 
```
git reset --soft HEAD^ // this is for last commit we got 
git reset --soft "HEAD^"// this is on windows
git reset --soft "asdf"
git reset --hard origin/master // this will reset your changes to origin master
```
To get one file from git repository
git checkout <file name>// git checkout test.txt
Note: this will override the changes you did for the file.

To discard the changes in working directory

    git checkout -- <file name>

To check the changes or differences in the working file 
```
    git diff <file name>
```

To get the latest changes in the master 
```
    git pull
```
it works sometimes we need to get from the origin master then.
```
    git pull origin master
```
to get from the specific branch
```
   git  pull origin <branch name>
```

## What the difference  between git pull and git pull origin master?
    ```
Git pull origin <branchname>: This will pull the changes made to the perticular branch.
Git pull origin master: This will pull all the changes made to the master.
Git pull: This will pull all the changes made to the master as well it will pull all the branches from the remote repository.
```
What is the difference between git pull and git fetch?
In the simplest terms, git pull does a git fetch followed by a git merge.
git pull = git fetch + git merge.

To check predefined shortcuts for the git is alias,  Go to the project folder then 
C:\PAP\M365AdminUX>alias

The below command checks out the remote branch, and your local branch name will be same as the remote branch.
git checkout -t origin/future_branch (for example)

If you want to override your local branch name on checkout:
git checkout -t -b enhancement origin/future_branch

Now your local branch name is enhancement, but your remote branch name is future_branch.

-------------------------------------------------------------------------------------------------
For updating the comment from previous comment and add our latest changes to existing commit(local)

git commit --amend -m "New commit message"

## How to ber sync with forked Repo into your user repo
 First Fork the repo, then clone the repo into local

// Setting the upstream as forkedParentRepo to the local repo
c:/mylocalforkedRepo> git remote add upstream git@github.com:abc-github/forkedParentRepository

git fetch upstream

// Below command will set our local master is synced with forked Parent Repository (where all others contributions are merged)
git branch --set-upstream-to=upstream/master master

from now on when we do the fetch/pull all the changes are merged into parent repo will come into local master

Create a new branch
git checkout -b branchName (you can )
```
-------------------------------------------------------------------------------------------------
## For pointing to the remote branch
```
    git remote -v
    git push origin head -u
```

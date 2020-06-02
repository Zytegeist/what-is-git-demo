# Git Merge Conflict

As a developer I want to manage code conflicts so that I know how to manage my code effectively.

## Exercise 

### Step One: Fetch all branches 
```
$ git fetch --all 
```

### Step Two: Review all branches 
```
$ git branch -a
```

### Step Three: Check out the remote feature branch
To work on our changes locally, check out the remote branch `JIRA-005-merge-conflict`. Then checkout the branch `JIRA-005-merge-conflict-two`

```
$ git checkout JIRA-005-merge-conflict
$ git checkout JIRA-005-merge-conflict-two
```

### Step Four: Rebase your two branches. 
Since it will be common that other developers on your team will be working on the same code we always want to rebase from the latest. 
In this case we will use the two branches provided in this repo. `JIRA-005-merge-conflict` and `JIRA-005-merge-conflict-two`. 
```
$ git rebase JIRA-005-merge-conflict-two/JIRA-005-merge-conflict
```




## Step Four: Rebase your branch with the master branch.
Once we have checked out the JIRA-005-merge-conflict we will want to try and rebase the branch with the master branch. \
Rebasing replays changes from one line of work onto another in the order they were introduced, whereas merging takes the endpoints and merges them together.
```
$ git rebase upstream/master
```

## Step Five: Review your merge conflicts 
```
<<<<<<< Updated upstream
=======
<<<<<<< HEAD
The purpose of this file is only to demonstrate a git merge conflict. Edit number two from the JIRA-005-merge-conflict-two branch.
=======
The purpose of this file is only to demonstrate a git merge conflict. I am going to edit this file to cause a merge conflict.
>>>>>>> JIRA-005: Adding text to later cause a merge conflict.
```

You can think of the HEAD as the "current branch". When you switch branches with git checkout, \
the HEAD revision changes to point to the tip of the new branch.

## Step Six: Fix your conflicts
Review what changes you need to make. Git will only ever know that changes occurred. \
It is up to the developer to determine what needs to stay or be removed. \
For the purposes of this demo we are going to say the commit from ` JIRA-005: Adding text to later cause a merge conflict.` \
Is the most current code changes that we want to keep. Therefore we will remove everything between `<<<<<<< HEAD and =======`.  Also remove the git message `>>>>>>> JIRA-005: Adding text to later cause a merge conflict.` \
Go back to your terminal and type 
```
$ git status
```

You should see something along the lines

```
[allierays/what-is-git-demo (JIRA-005-merge-conflict|REBASE 1/1)]$ git status
rebase in progress; onto cc06a94
You are currently rebasing branch 'JIRA-005-merge-conflict' on 'cc06a94'.
  (fix conflicts and then run "git rebase --continue")
  (use "git rebase --skip" to skip this patch)
  (use "git rebase --abort" to check out the original branch)

Unmerged paths:
  (use "git reset HEAD <file>..." to unstage)
  (use "git add <file>..." to mark resolution)

	both modified:   005b-git-merge-conflict.md

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

	modified:   005-git-merge-conflict.md

no changes added to commit (use "git add" and/or "git commit -a")

```

Navigate to your 005-git-merge-conflict.md 

We want to add and commit these changes. 
```
$ git add . 
$ git commit -m"JIRA-005: Resolving merge conflict for merge file."
$ git rebase --continue
```

Try to rebase again 
```
$ git rebase upstream/JIRA-005-merge-conflict-two
```

You should see a message along the lines of 
```
[allierays/what-is-git-demo (JIRA-005-merge-conflict)]$ git rebase origin/JIRA-005-merge-conflict-two
Current branch JIRA-005-merge-conflict is up to date.   
```


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

### Step Three: Check out the remote branch
You always want to start your branches from the main branch. In this case it is master. In most cases that will be develop. \
* Notice when we checkout out a branch that already exists we do not need the `-b` argument.

```
$ git checkout master
$ git checkout JIRA-005-merge-conflict
```
Navigate and review the changes to the 005-git-merge-conflict-md file. 

## Step Four: Rebase your branch with the master branch.
Once we have checked out the JIRA-005-merge-conflict we will want to try and rebase the branch with the master branch. \
Rebasing replays changes from one line of work onto another in the order they were introduced, whereas merging takes the endpoints and merges them together. \
```
$ git rebase upstream/develop
```

## Step Five: Review your merge conflicts 


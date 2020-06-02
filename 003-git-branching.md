# Git Branching

As a developer, every time I need to create a new feature I want to create a new branch so I can segregate my work.

## Exercise 

### Step One: Create a branch 
You must use the `-b` command when creating a new branch. Once the branch has been created, you no longer use the `-b` command. \
Get use to adding a Jira ticket number to each feature branch. When you don't have a jira ticket number just add JIRA-001. \
All branch names must have a dash and no spaces. Please replace the <your-name> value with your own name.
 
```
$ git checkout -b JIRA-001-<your-name>-create-branch
```

### Step Two: Push the branch to your origin 
```
$ git push origin JIRA-001-y<our-name>-create-branch
```

### Step Three: Try to Push to your upstream 
*This will fail* You do not have permissions to push to your upstream. Please see [Github's Managing the forking policy for your organization](https://help.github.com/en/github/setting-up-and-managing-organizations-and-teams/managing-the-forking-policy-for-your-organization) for more information about github's forking strategy.
```
$ git push upstream JIRA-001-<your-name>-create-branch
```

### Step Four: Create another branch
You always want to start your branches from the main branch. In this case it is master. In most cases that will be develop. \
* Notice when we checkout out a branch that already exists we do not need the `-b` argument, but when we want to create a new branch we use the `-b` command.

```
$ git checkout master
$ git checkout -b JIRA-004-my-new-branch
```

### Step Five: Delete your second branch
The purpose of this step is to understand how to delete a branch. 
```
$ git checkout master
$ git branch -D JIRA-004-my-new-branch
```


### Step Six: Review 
You should have only one new branch locally. 
The git branch command will show you your local branches 
```
$ git branch
```
and `git branch -a` will show you all of your local and remote branches
```
$ git branch -a 
```

Nothing to commit and no need to create a pull request. 
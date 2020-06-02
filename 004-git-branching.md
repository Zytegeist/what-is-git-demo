# Git Branching

As a developer, every time I need to create a new feature I want to create a new branch so I can segregate my work.

## Exercise 

### Step One: Create a branch 
You must use the -b command when creating a new branch. Once the branch has been created you no longer use the -b command. \
Get use to adding a Jira ticket number to each feature branch. When you don't have a jira ticket number just add JIRA-001. \ 
All branch names must have a dash and no spaces. Please replace the <your-name> value with your own name.
 
```
$ git checkout -b JIRA-001-<your-name>-create-branch
```

### Step Two: Push the branch to your origin 
```
$ git push origin JIRA-001-y<our-name>-create-branch
```

## Step Three: Try to Push to your upstream 
*This will fail* You do not have permissions to push to your upstream. Please see [Github's Managing the forking policy for your organization](https://help.github.com/en/github/setting-up-and-managing-organizations-and-teams/managing-the-forking-policy-for-your-organization) for more information about github's forking strategy.
```
$ git push upstream JIRA-001-<your-name>-create-branch
```
# Add a new file to your version control system git and push to Github 

As a developer, I want to be able to add new files locally, push files to a cloud repository on Github so that I can create a pull request. 

### Step One: Create a new branch 
You must use the `-b` command when creating a new branch. Once the branch has been created, you no longer use the `-b` command. \
Get use to adding a Jira ticket number to each feature branch. When you don't have a jira ticket number just add JIRA-###. \
All branch names must have a dash and no spaces. Please replace the <your-name> value with your own name.

Always start from the main branch. In this case it is master, on most active projects it will be develop. 
```
$ git checkout master 
$ git checkout -b JIRA-004-<your-name>-new-file
```

### Step Two: Create a new file. 
Create a new file with your name. For example, 001-allie-git-initialize.md. 
Use git status to see what changes have been made to the repo.

```
$ nano 001-<your-name>-git-initialize.md
```
Add the text hello world. \
control x and y to save.  \
Run git status to see your new file. 

```
$ git status
```

### Step Three: Add the new file to the git repository. 
We are going to use git add `001-<your-name>-git-initialize.md` to make sure we are only adding the file we want to the repository.
```
$ git add 001-<your-name>-git-initialize.md
```

### Step Four: Create a commit message to tell the git repo of your changes. 
Best practices is to add a jira ticket number with this commit, but since there is not attached to a jira project for this demo we will a dummy Jira ticket number to this commit message.
```
$ git commit -m"JIRA-001: Adding 001-<your-name>-git-initialize.md to the repo."
```

### Step Five: Add the branch to your origin repository and push your code up to the remote.
```
$ git push origin JIRA-004-<your-name>-new-file
```

#### Step Six: Create a PR
Go to your github repo \
and click create a PR. \
Review your code changes \
Review the base branch is AllieRays:master \
Create a PR \
Review [github's documentation about pull requests](https://help.github.com/en/github/collaborating-with-issues-and-pull-requests/creating-a-pull-request-from-a-fork) if you need more help with creating a PR.

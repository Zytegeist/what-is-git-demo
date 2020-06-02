# Add a new file to your version control system git and push to Github 

As a developer, I want to be able to add new files locally, push files to my origin so that I can create a pull request. 

### Step One: Create a new file. 
Create a new file with your name. For example, 001-allie-git-initialize.md. 
Use git status to see what changes have been made to the repo.

```
$ nano 001-allie-git-initialize.md
```
Add the text hello world. \
command x and y to save.  \
Run git status to see your new file. 

```
$ git status
```

### Step Two: Add the new file to the git repository. 
We are going to use Git add `001-<your-name>-git-initialize.md` to make sure we are only adding the file we want to the repository.
```
$ git add 001-<your-name>-git-initialize.md
```

### Step Three: Create a commit message to tell the git repo of your changes. 
Best practices is to add a jira ticket number with this commit, but since there is not attached to a jira project for this demo we will a dummy Jira ticket number to this commit message.
```
$ git commit -m"JIRA-001: Adding 001-<your-name>-git-initialize.md to the repo"
```

### Step Four: Add the branch to your origin repository and push your code up to the remote.
```
$ git push origin origin master
```

#### Step Five: Create a PR
Go to your github repo \
and click create a PR. \
Review your code changes \
Review the base branch is dev-assessment-exercises \
Create a PR \
Review [github's documentation about pull requests](https://help.github.com/en/github/collaborating-with-issues-and-pull-requests/creating-a-pull-request-from-a-fork) if you need more help with creating a PR.

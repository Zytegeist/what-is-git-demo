# Interactive Git Rebase 

> Commit often & Push less

With git-rebase you can push local commits together into one commit (without force). \
With rebase, you can commit more often and then merge your commits together before pushing back to the shared repo. \
For simplicity, we are only going to talk about rebasing locally.

--- 
As a developer I want to be able to change my git commit message so that I can have a semantic git log history. 

## Exercise 

### Step One: Create a new branch JIRA-006-interactive-rebase
You must use the `-b` command when creating a new branch. Once the branch has been created, you no longer use the `-b` command. 
```
$ git checkout -b JIRA-006-interactive-rebase
```

### Step Two: Add a markdown text to your local repo.
```
$ nano 006-interactive-rebase.md
```
On a new line add the following text 
```
Hello world this will be a rebase commit. 
$ control x
$ y
```

### Step Three: Git add and git commit
Use `git add -p` to step through your code to see what has changed. 
```
$ git add -p 
```

Git add -p gives us the following options. 
```
y - stage this hunk
n - do not stage this hunk
q - quit; do not stage this hunk or any of the remaining ones
a - stage this hunk and all later hunks in the file
d - do not stage this hunk or any of the later hunks in the file
g - select a hunk to go to
/ - search for a hunk matching the given regex
j - leave this hunk undecided, see next undecided hunk
J - leave this hunk undecided, see next hunk
s - split the current hunk into smaller hunks
e - manually edit the current hunk
? - print help
```
Use the `y` to stage all of your changes. 
```
$ y 
$ git commit -m"My git commit message." 
```

What did we forget? - A jira ticket number and a more semantic git commit message. We will fix this later.

### Step Four: Create a second commit 
```
$ nano 006-interactive-rebase.md
```
On a new line add the following text 
```
This is my second commit equally as important.
$ control x
$ y 
$ git commit -m"JIRA-006: Adding text to my interactive rebase markdown file." 
```

### Step Five: Review and rebase your commits. 
Review your last commit messages. 
```
$ git log 
```
Create a rebase using the `-i` argument to rebase your commits with the interactive shell. 

```
$ git rebase -i HEAD~2 
```
If you are using vim type `a` to insert.
Review the options

```
# Commands:
# p, pick <commit> = use commit
# r, reword <commit> = use commit, but edit the commit message
# e, edit <commit> = use commit, but stop for amending
# s, squash <commit> = use commit, but meld into previous commit
# f, fixup <commit> = like "squash", but discard this commit's log message
# x, exec <command> = run command (the rest of the line) using shell
# b, break = stop here (continue rebase later with 'git rebase --continue')
# d, drop <commit> = remove commit
# l, label <label> = label current HEAD with a name
# t, reset <label> = reset HEAD to a label
# m, merge [-C <commit> | -c <commit>] <label> [# <oneline>]
# .       create a merge commit using the original merge commit's
# .       message (or the oneline, if no original merge commit was
# .       specified). Use -c <commit> to reword the commit message.
#
# These lines can be re-ordered; they are executed from top to bottom.
#
# If you remove a line here THAT COMMIT WILL BE LOST.
#
# However, if you remove everything, the rebase will be aborted.
#
# Note that empty commits are commented out

``` 

We want to reword our first commit to be more semantic and we want to fix "like "squash", but discard this commit's log message". 

```
r 8c8f770 JIRA-006: My git commit message.
f eddbd73 JIRA-006: Adding text to my interactive rebase markdown file.
esc 
:x
```

You will see a message similar to 
```
hint: Waiting for your editor to close the file... 
My git commit message.
  
# Please enter the commit message for your changes. Lines starting
# with '#' will be ignored, and an empty message aborts the commit.
```

Type the `a` to change your message to `JIRA-006: Adding text to my interactive rebase markdown file.`
```
esc 
:x
```

Use git log again to see your commit history
```
git log
```

You should now see one git message of `JIRA-006: Adding text to my interactive rebase markdown file.` 
Use git to push back to your origin. 
```
$ git push origin JIRA-006-interactive-rebase
```

### Step Six: Create a PR
Go to your github repo \
and click create a PR. \
Review your code changes \
Review the base branch is AllieRays:master \
Create a PR \
Review [github's documentation about pull requests](https://help.github.com/en/github/collaborating-with-issues-and-pull-requests/creating-a-pull-request-from-a-fork) if you need more help with creating a PR.

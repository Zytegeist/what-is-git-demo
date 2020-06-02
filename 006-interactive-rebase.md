# Interactive Git Rebase 

> Commit often & Push less

With git-rebase you can push local commits together into one commit (without force). \
With rebase, you can commit more often and then merge your commits together before pushing back to the shared repo. \
For simplicity, we are only going to talk about rebasing locally. This is a little more complicated to explain, so I think it is easier to just show a simple example. For example:

```
Commands:

# p	pick = use commit
# r	reword = use commit, but edit the commit message
# e	edit = use commit, but stop for amending
# s	squash = use commit, but meld into previous commit
# f	fixup = like "squash", but discard this commit's log message
# x	exec = run command (the rest of the line) using shell
```


--- 
As a developer I want to be able to change my git commit message so that I can have a semantic git log history. 

## Exercise 


### Step One: Checkout branch 
```
$ git checkout JIRA-006-interactive-rebase
```

### Step Two: Add text to this file 
```
$ nano 006-interactive-rebase.md
```
On a new line add the following text 
```
Hello world this will be a rebase commit. 
$ cmd x
$ y
```

## Step Three: Git add and git commit
Use `git add -p` to step through your code to see what has changed. 
```
$ git add -p 
$ y 
$ git commit -m"My git commit message." 
```

What did we forget? - A jira ticket number and a more semantic git commit message. 

## Step Four: Create a second commit 
```
$ nano 006-interactive-rebase.md
```
On a new line add the following text 
```
This is my second commit equally as important.
$ cmd x
$ y 
$ git commit -m"JIRA-006: Adding text to my interactive rebase markdown file." 
```

## Step Five: Rebase your commits. 
Use the `-i` argument to rebase your commits with the interactive shell. 
```
$ git log 
```
Review your last commit messages. 

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

What we want to use is fix and reword. \ 
Change the first commit to `r` and the second commit to `f`
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
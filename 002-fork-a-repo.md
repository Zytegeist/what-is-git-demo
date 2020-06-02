## Create a fork 

As a developer I want to work from a forked repository so that I can work locally, push to the cloud and not affect the master branch. 
* Prerequisite you must create and add your ssh keys to your github account. \
** [Setup GitHub SSH Keys](https://help.github.com/articles/adding-a-new-ssh-key-to-your-github-account/) \
** [Setup Acquia Cloud SSH Keys](https://docs.acquia.com/acquia-cloud/ssh/generate)

## Step One: Go to this repository and create a fork 
Navigate to https://github.com/AllieRays/what-is-git-demo

## Step Two: Create a fork 
Go to the  github repository https://github.com/AllieRays/what-is-git-demo \
and in the top-right corner of the page, click Fork.

## Step Three: Clone your forked repository
Clone your forked repository. By default, Git names this "origin" on your local 
```
$ git clone https://github.com/<your-github-username>/what-is-git-demo
```

## Step Four: Add an upstream 
To ensure that upstream changes to the parent repository may be tracked, add the upstream locally as well.
```
$ git remote add upstream git@github.com:AllieRays/what-is-git-demo.git
```

## Step Five: Review your origin and upstream remote 
```
$ git remote -v
```

--- 
If your output look similar to this you have successfully completed this exercise. 
```
[allierays/what-is-git-demo (master)]$ git remote -v
origin	git@github.com:<your-github-username>/what-is-git-demo.git (fetch)
origin	git@github.com:<your-github-username>/what-is-git-demo.git (push)
upstream  git@github.com:AllieRays/what-is-git-demo.git (fetch)
upstream  git@github.com:AllieRays/what-is-git-demo.git (push)
```

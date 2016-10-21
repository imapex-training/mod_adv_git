[item]: # (slide)

## Introduction

This module will provide you with an introduction to some basic to intermediate github workflows.

It is assumed that you already have a basic understanding of:

* What git is
* When/why you would use it


The official tutorial for Github is a useful resource and can be find [Here](https://guides.github.com/activities/hello-world/)

[item]: # (/slide)
[item]: # (slide)
## Basic Refresher

There are three states in a github repo.

* Modified - any files that you have modified in your working directory
* Staged - a snapshot of files, ready to be commited
* Commited - permentantly stored in your git repository

[item]: # (/slide)

[item]: # (slide)
## "Checkout"
The ability to move your current working directory to a point in time.

This is a point in time in time at a particular branch.

To see the git history you can use:

```
git log
```

To work on the code from a specific point in time

```
git checkout <COMMIT>
```

[item]: # (/slide)

[item]: # (slide)
## Other commands to try

Show commit info + files that changed
```
git log --stat
```
A single line view of each commit
```
git log --pretty=oneline
```
To compare two commits
```
git diff commit1 commit2
```

[item]: # (/slide)

[item]: # (slide)
## Tags

* reference to a specific commit
* human friendly
* typically used for managing releases
Show Tags:
```
git tag
```
Create a new tag:
```
git tag -a v1.0 -m "version 1.0 release"
```
Tag a previous commit:
```
git tag -a v1.2 9fcd202
```

[item]: # (/slide)

[item]: # (slide)
## HEAD

* The latest commit in a particular branch.
* used as a reference when checking out a particular branch

You can see what the latest commit is with
```
cat .git/HEAD
```

[item]: # (/slide)
## Forking / Branching

Forking and Branching are mechanisms used by Git to diverge from the main code line for feature development, or bug
fixes. Branches are seperate trains within the same repository, whereas a fork, creates a copy of the entire repository in
a different location (user account). From the perspective of a single developer the two are very similar, however, it
is important to consider what other developers are doing relative to the project. The fork based workflow is dominant in
opensource projects as contributors likely would not have access to push code to the main repository.

For more information see this [Stack Overflow Post](http://stackoverflow.com/questions/3611256/forking-vs-branching-in-github)
[item]: # (slide)
## Branches

* Used to develop features
* isolate changes
* repos maintain a default branch, usually master
* can be merged into other branches
Create a new branch:
```
git branch -m mynewfeature
```

![branch](img/branch.png)

[item]: # (/slide)
[item]: # (slide)
## Forking

* a copy of a repository
* make changes w/o impacting source repo
* long lived
  * a new project based on existing work
* short lived
  * proposing changes to someone elses repo

[Tell me more!!](https://help.github.com/articles/working-with-forks/)

[item]: # (/slide)

[item]: # (slide)
## Stashing

* moves changes out of the staging area temporarily
* useful when navigating between branches
* create a tempory "stash" of **staged** files
* apply them to another branch
Stash Changes:
```
git stash
```
Unstash Changes:
```
git stash apply
```

List Stashed changes:
```
git stash list
```

[Tell me more!!](https://git-scm.com/book/en/v1/Git-Tools-Stashing)

[item]: # (/slide)

Stashing provides ability to temporarily store local changes prior to performing other operations on the
repository - a good example of this is that you've been working on some changes and want to pull the latest changes that
others have committed.

*NOTE* One important thing to remember is that git stash will not save files in the working directory unless they have been
added to the index (git add)

A detailed explanation of git stash can be found [Here](https://git-scm.com/book/en/v1/Git-Tools-Stashing)


[item]: # (slide)
## Merge

* incorporate changes between branches


```
	  A---B---C feature
	 /
 D---E---F---G master
```

```
git checkout master
git merge feature
```

```
	  A---B---C feature
	 /         \
 D---E---F---G---H master
```
To undo a merge that has conflicts:
```
git merge --abort
```


[item]: # (/slide)

[item]: # (slide)
## Rebase

* another way to merge changes between branches
* apply all commits from one branch to another
* syncing changes to a a feature branch

![image](img/rebase.png)

[item]: # (/slide)
[item]: # (slide)
## Remotes

A git repo may have many copies in various locations called remotes:

* URL reference to other copies of the repository
* most commonly github
* `origin` - automatically created remote when a repo is cloned
To view remotes configuration
```
cat .git/config
```
To add additional remote:
```
git add remote <name> <url>
```
Additional remote operations:
```
git remote --help

```

[item]: # (/slide)

[item]: # (slide)
## Push
Push your local changes to a remote:
```
git push <remote> <branch>
```
* when used w/ multiple remotes you can quickly work across branches and forks

[item]: # (/slide)
[item]: # (slide)

## Pull Requests

Pull requests are the way of notifying others about changes that you've checked in and you want incorporated into the
main project.  Pull requests can be issued from a forked repository, or from a branch within a single repository.

* notify others of your changes
* request that they "pull" those changes into their work and merge them
* issued from:
  * forked repository
  * branches in the same repository

[item]: # (/slide)
[item]: # (slide)

## Issues / Milestones / Labels

Issues are an important collaboration tool within github

Issues allow you to
* Keep track of bugfixes
* Track enhancements
* Provide a forum for discussion about your code
  * supports github flavored markdown for references to PR's, code, mentions, etc

Asignment, Milestones and Labels allow you to organize issues in a meaningful way

[item]: # (/slide)


Issues are the primary vehicle by which feature enhancements and bug fixes are tracked.

Labels are used to categorize the the issue. Examples of tags are enhancement, bug, question, help wanted.

 A detailed explanation of Issues, Labels, and Milestones can be found [Here](https://guides.github.com/features/issues/)

*TIP:* To close an issue in the same repository, use one of the keywords in the list below followed by a
reference to the issue number in the commit message. For example, a commit message with Fixes #45 will close issue 45
in that repository once the commit is merged into the default branch.

If the commit is in a non-default branch, the issue will remain open and the issue will be referenced with a tooltip.

For more information and similar tips see [https://help.github.com/articles/closing-issues-via-commit-messages/]

[item]: # (slide)



README Standards and Expectations
----------------------------------

A good README file is important for outlining the motivation behind a particular project repository, as well
as providing the reader with an overview of how to effectively utilize the project repository.


[http://stackoverflow.com/questions/2304863/how-to-write-a-good-readme](http://stackoverflow.com/questions/2304863/how-to-write-a-good-readme)


* ASCII characters only, if the README is written in English
* write it in English if possible, and ship translated version with two-letter
  language code extension like README.ja
* 80 characters or less per line
* single empty line between paragraphs
* dashes under the headers
* indent using whitespace (0x20) not tab

[item]: # (/slide)

[item]: # (slide)

## Discussion Items for kickoff

* Production deployments will be done from the master branch
* All feature development should be done via the developers fork / branch
* All feature development should have an open issue tagged enhancement for tracking purposes
* All bug fixes should have an open issue for tracking purposes

[item]: # (/slide)

[item]: # (slide)

## Sample Workflow

1. Fork an existing repository
2. Clone your fork
3. Add 'upstream' remote
4. Create a feature branch
5. develop cool feature
6. incorporate any upstream changes to your fork / branch
7. merge your feature branch
8. Open pull request to existing repostiory

[item]: # (/slide)

Lab Exercise
=============================

For the lab exercise of this module we will be combining these steps into a real-world workflow.


# Instructions

1. Open an Issue against the imapex/101-github-lab referencing the fact that your email is missing from the CONTRIBUTORS.txt
file. As you are now going to be contributing to the project - this is obviously and enhancement, so label it as such!!!

2. Assign yourself to the issue

3. Create a fork of your /101-github-lab repository

	```
   git clone https://github.com/<your_git_id>/101-github-lab
   ```

4. Create and checkout a new branch for your enhancement

	```
   git branch -m adding-email-addr
    git checkout adding-email-addr
   ```

	* **_NOTE_ If your branch is going to exist for a longer period of time why you are developing your feature you could add the upstream repo as a remote for your repository as well.**

		```
	   git remote add --track master upstream git://github.com/upstreamname/projectname.git
	   ```

	* Now you can get updates from the main project as well by using:

		```
	   git fetch upstream
	   git merge upstream/master
	   ```

5. Make the appropriate changes to add your email address to the CONTRIBUTORS.txt file.

6. Commit your changes, be sure to indicate the issue number that you are working on in your commit message

	```
    git add CONTRIBUTORS.txt
   git commit -m "added email address - closes #XXX"
   ```
7. Push your changes from local to your forked repository
    ```
    git push -u origin adding-email-addr
    ```

5. From your web browser, go to the github page of your fork, and open a pull request.

6. Navigate to the upstream repository [IMAPEX/101-github-lab](https://github.com/imapex/101-github-lab) and
verify that the pull request was issued.  From here discussion can occur on the proposed changes, and the owner
of the repository can merge the changes in once completed.
	* **_Note_ An opened PR is often a trigger for a something to
happen in the build pipeline, such as automated testing of the proposed changes.**


# Git and GitHub Tutorial

###### Credits: Mark Davis, Greg Harmon

## Learning Goals:
* [Track progress and assignments with Trello](#trello-tracking)
* [Understand Git and Github](#git-explainer)
* [Fork a repository](#forking)
* [Clone it locally](#cloning)
* [Commit work that they did](#tracking-work)
* [Change branches and create new ones](#branch-management)
* [Pull in work from other contributors](#git-collaboration)
* [Resolve merge conflicts with concurrent work](#merge-conflicts)
* [Undo common mistakes and maintain a clean git history](#troubleshooting)
* [Deploy their work to Github Pages](#deployment)
* [Make a pull request from their fork](#sharing-your-work)

### Introduction
Welcome to the Project Management Bootcamp! The purpose of this bootcamp is to familiarize you with using the Trello and GitHub technologies. This bootcamp is going to be centered around developing your own website. We are going to use Trello to break down this task into smaller sub-tasks, and GitHub to keep track of your code and host your website. 


### Trello Tracking
To begin using Trello, go to Trello.com and click either the create an account button in the center of the screen, or the Sign Up button in the top right corner of the screen. Once you have created your account, paste this [link](https://trello.com/b/jKd6uW68/project-management-bootcamp) into your browser: 

This board serves as a brekdown of our project. However, you are unable to edit this board; you must clone your own version of it. To do this, click on the ... More button in the Menu on the right side of your screen, and click Copy Board. You can name your version of the board whatever you would like. Once you are on your new board, take a look at your To Do list. You should see a card called 'Setup Trello and move my first card'. Drag this card from To Do to completed, and you're first task is complete!


### Git Explainer
//TODO what is git

 Before you can start working, you are going to need to create a GitHub account, which can be done by going to https://github.com/ and following the on screen instructions. Once you have your account set up and ready to go, you are going to go ahead and copy some files that have already been created for you to work with by forking an existing repository.

### Forking
  * What is forking?

Forking is a process by which you copy someone elses (remote) project in to your own (remote) repository. This allows you to make changes to your personal copy without compromising their project. 

For this activity, we are going to start with forking this repository: https://github.com/markd315/GitTutorial

To do this, click the link above, and then look for the Fork button highlighted below in red.
![Click the red button to fork the repository](/tutimg/fork.png)

Great! We've forked the repository so that you can make whichever changes you want.

### Cloning

However, we aren't ready to work on it just yet. Right now, the forked repository only exists on GitHub. In order to make changes on your machine, we are going to need to clone the repository.
  * What is cloning?

Cloning is the process of creating a local version of a repository to work on. While there are multiple ways to clone a repository, we are going to use Git to do this. You are going to need to download Git, which can be found at https://git-scm.com/downloads 

Once you have Git installed, go ahead and open it and type in the following command to clone your newly forked repository:

```
$ git clone https://github.com/YOUR_GITHUB_NAME/REPOSITORY_NAME
```

You are going to have to replace the two vague fields in this link with your personal GitHub account Name, and the repository name GitTutorial.

### Tracking Work

Now that we have a local copy of the repository, we can make our first change. 

Open your file explorer and navigate to the folder that was created when you cloned the repository. This is going to be located in
C:/Users/(your_user_name_on_your_computer)/GitTutorial. Once you have navigated to that folder, go ahead and make a new text file. You can call it whatever you'd like, and you can type any content you would like in the text file. Once you are done with that, we are going to head back to Git to push our local changes to the GitHub repository.

If you type git status, you can see the name of the file that you added. In order to add the file, you can type 
```
$ git add --all.
```

Once you have done that, you have to do git commit -m "My first commit". You can replace the text inside the quotations with anything you'd like, but it is required to put some message in there.

After you have added and committed, you can type git push. If you did everything correctly, you can go to your online repository to view your changes! 


### Branch Management
The problem we are solving is the need to create parallel versions of your codebase so that multiple people can work on different features at the same time.

Given that each commit represents a "difference" between old and new versions of the codebase, we need to represent these parallel code versions with alternate histories.

These histories *can* have some changes in common with each other (especially prior to the branch time), but must handle having different commits from each other.
In the following diagrams, a movement to the right constitutes a passage of time, and a circle constitutes a single commit to the branch.

A new row+color should be interpreted as being on a distinct branch.

![Create a new branch and check it out](/tutimg/gitcheckout.png)

As we can infer from the diagram, both branches have the first commit in common, but after they branch they each contain 2-3 different commits (representing work on different features).

A major goal of branch management is to combine work that *was* done in parallel by multiple authors to a single, releasable version with all of the features and bugfixes included.

In order to do this, we need to merge a target branch into a base branch.

The way to do this is by switching to the base branch and running

```
$ git merge <target-name>
```

as shown below.

![Merge in work from a different branch](/tutimg/gitmerge.png)

If we divided work appropriately in the first place (no changes to the same part of the same file in the two branches) our merge will process uninterrupted.

If we have different changes affecting the same section, we'll face merge conflicts in which we have to select which version of the code section we want to use.

Now that we've merged code from the <target-name> branch, we can delete it if we want to so that we only store copies of the codebase that remain relevant.

To kill a branch locally, we can simply run
```
$ git branch -D 
```

But if you've pushed it, deleting a remote copy will involve navigating to github>code>branches and deleting the desired branch.


Another way to combine work on multiple branches is with a rebase, which does have the consequence of rewriting project history.

As such, the golden rule is to never rebase while you have a main branch checked out, like develop, test, or master. The opposite is generally true for merging.

```
$ git checkout <feature-branch>
$ git rebase <base-branch>
```

The result of this is a single, linear commit history on the feature branch, with the base branch unchanged.

It will start with the commits from base (in order), and then include all of the commits from the target (in order).


### Git Collaboration
A major rule of thumb for working with multiple people on a remote repository is to always 
```
$ git pull
```
BEFORE making any new branches, merges, changes or commits.

See the [troubleshooting section](#troubleshooting) for what to do if you fail to pull in time.

We also want our branches to show up on the remote repository so that other users can pull them when they need to.

The first time we push to our remote, we need to set the target location out in the cloud.

We should already have a remote called *origin* from when we cloned, and so we'll be pushing there.

```
$ git push --set-upstream origin <feature-name>
```
From now on for this branch, a simple 

```
$ git push
```

should do the trick since the local and remote branches are already linked.

If you do this or at least resolve the issues when you don't, merging the work of others should be just as straightforward as merging your own feature branches as described above.

For our example, try merging the branch "feature-add-thai-food" into your master branch, and then reload the website.

```
$ git pull
$ git checkout master
$ git pull
$ git merge feature-add-thai-food
$ git push
```

This all assumes that the user can read and write to all of the necessary branches.

In many cases, an organization will write-protect their master, test and develop branches so that the leadership can perform code reviews, unit and integration testing, and other quality controls for their codebase.

In all of these cases, merges must be handled on the remote repository through ***pull requests***.

These are a forum thread of sorts, where affected users can review the changes, request new ones, comment on style, and approve the details of the merge before it hits the main branches of their codebase.

See the [sharing your work section](#sharing-your-work) on how to create one.

As a project manager, configuring your repository to require pull requests is simple, we just need to protect certain branches with a *rule*.

Navigate to Settings>Branches>Add new rule in your Github repository and change the settings as desired. Make sure to save them before leaving.

![Project branch settings](/tutimg/branchprot.png)

### Merge Conflicts


### Troubleshooting

A common mistake is to make the changes on the wrong branch, and then notice before making a commit that your checked out branch was wrong.

We can investigate this with 
```
$ git status
```

which will show us changed files (whether they've been staged with git add or not).

This is simple to fix, and lucky for us because it really is very common.

The git tools contains a stack data structure on which we can store 

The only two necessary operations of a stack data structure are to "push" (store a stack frame worth of changes) and "pop" (retrieve the latest frame worth of changes and remove it from the stack).

As such, a stack is described as being LIFO ordered: Last-In is the First-Out.

```
$ git stash (to store the changes on the stack)
$ git checkout <desired branch>
$ git stash pop (to replay the stored changes and delete them from the stack)
add/commit/push correct branch if and when desired
```


Maybe sometimes you'll accidentally enter some changes, or a git commit that you want to undo.

If you haven't pushed it to the remote repository yet, this is quite easy! We still have a valid copy of the branch stored *on* the remote repository, so we can just access it by [resetting to the remote repository](#remote-undo).

If you've also already pushed it, you're in a little bit more trouble just because we don't want to rewrite the history on remote branches once it's established. The best way to revert a single bad commit locally is to employ the [git revert](#synchronize-revert-and-push).

#### Remote undo
Simply run this command
$ git reset --hard origin/master

(replacing the master branch if necessary)


#### Synchonize revert and push
First, synchronize the remote and local branches with

$ git checkout <branch> (if necessary)
$ git pull

We need to find the identifier of the commit we want to revert. Go to your remote history and find the faulty commit. Look for the identifier (you can just click the copy button next to it)

This example is for the "weird character" commit.
![Commit number example](/tutimg/commitNum.png)

$ git revert 57e8718c41d0b67201ec809fc4aaa5cd707ade39

At this point, vim should come up and allow you to edit the reversion commit message. If you don't want to do that, it's okay! Just press the : key (shift + ;) and then q (for quit). Press enter to quit vim and complete the revert.

And finally
$ git push
again.

Now on your git log, you will see one commit with the changes you wanted to get rid of, and another commit that exactly reverses this commit.

This same strategy will work if you haven't pushed as well, but it's a lot of trouble to go through for not much purpose.

Sometimes, to keep a clear log of features and bugfixes in our commit log, it is good practice to rewrite local history, especially by reducing the amount of commits to reflect individual units of work. This is called a "squash", in which you combine several commits into one.

Doing this before you push your work will save your colleagues reading time by grouping all relevant work into one commit and not spreading linked work across several commits, clogging the git log.

This is a good way to make reverts (described above) disappear too: since we're already rewriting history. If you do something in one commit and then undo it in another commit our log will still reflect both of those changes, but if we squash the work into one commit then both will disappear.

There doesn't appear to be a single, industry-standard way to make a git squash from the command line and instead there are a couple techniques that will vary by situation. In a case where you want to rebase every commit since the target branch was created, I would use the [soft reset method](#soft-reset-squash).

In any other case (or if you just want to learn one technique, I would use the [interactive rebase method](#interactive-rebase-squash)

#### Soft reset squash
First, we need to undo all of the commits from our history, *without* actually losing the work.
This is called a soft reset and it's very important to not confuse it with a hard reset.

Once again, in a soft reset we undo every commit since the reset point, but a hard reset means that we *also* throw away all our work since that point.
```
$ git reset --soft origin/master

$ git add --all
```
to track all of the changed files
```
$ git commit -m "Your commit message here"
```
to make a new commit
```
$ git push
```
to update the remote branch corresponding to our local.

#### Interactive rebase squash
This method can rewrite remote history and is therefore not advisable without a backup.

So let's leave that branch the way it is and make a new one.
```
$ git branch squashing_<your branch name here>
$ git checkout -b squashing_<your branch name here>
```

Or to combine those into one step, 
```
$ git checkout -b squashing_<your branch name here>
```

Now run
```
$ git rebase -i master
```

where master is the base branch. Vim will come up, and we actually need to use it this time. All commits *since* your branch left the base branch will show up in this log, with the most recent ones at the bottom.

If you only want to see n commits, try this version instead of -i master:
```
$ git rebase -i HEAD~n
```

Press the 'i' key to change the following text shown in vim.
```
pick fda59df commit 'stuff'
pick x536897 commit 'things'
pick c01a668 commit 'hello mom'
```
Right now, all of the commits shown will be saved if we quit vim (no changes). 
If we want to squash a commit into the commit above it, simply change 'pick' to 'squash' (or just 's').



When you're done, we need to save our changes.
Press 'esc' to exit the Vim Insert mode, and write the file with : w (and enter).

Then quit vim like before: just press the : key (shift + ;) and then q and enter (for quit).

Since we did this on a backed up version of the branch, make sure that this squashed version is working (perhaps run any unit tests you might have, or use git log) and then replace the target branch with it.

```
git branch -D target_branch (to delete it)
git checkout -b target_branch (to recreate it from the backup)
```

It's usually a good idea to squash local work *before* we push.
According to [git-scm.com](https://git-scm.com/book/en/v2/Git-Tools-Rewriting-History)
```
One of the cardinal rules of Git is that, since so much work is local within your clone, you have a great deal of freedom to rewrite your history locally. However, once you push your work, it is a different story entirely, and you should consider pushed work as final unless you have good reason to change it. In short, you should avoid pushing your work until you’re happy with it and ready to share it with the rest of the world.
```


### Deployment
In order to deploy our project, we need to change two settings, so on the main page for your repository click settings.
![Change the name](/tutimg/pagesSetting1.png)

First, make sure to name the project exactly the same as YOUR github username. The example above is for a user (or organization) named CEN3031-10A.

Save the rename, and secondly, scroll all the way down to the Github Pages section of this settings page.

Make sure the dropdown box is set to build from master, save your changes again and refresh the page.

If you did everything right, it should look like the following and your link will redirect to your site!

![Set the branch to Master](/tutimg/pagesSetting2.png)

### Sharing Your Work

Now that you've made your changes, and shared them publicly, it's time to let others know that your work is ready to be incorporated (merged).

Navigate to the original repository (https://github.com/markd315/GitTutorial)
and click the highlighted Pull Request button.

![Make your PR](/tutimg/newPR.png)

There will be two dropdowns shown and it's important to not scramble them!

The one on the left is the target/base branch that we are modifying, or pulling the new code into.

The one on the right is the compare branch that has new changes.

Sometimes, there will also be changes (from a seperate Pull Request) in the base branch that will conflict with ours, but that presents a challenge for another day.

For now, set your base branch to markd315/GitTutorial/master and your compare branch to whatever you made independently.

Leave a useful comment describing the work you've done, and submit your work to be reviewed!

Before long, the owner of the open-source repository, or your boss if this is an enterprise setting will review your work.

She may then choose to
* Merge it without changes
* Leave comments asking questions
* Request specific changes
* Reject it outright (if it is unneeded).

Congratulations on all your hard work!

//TODO Add borders to images so we can tell where they start and the github readme begins etc.

### References

https://www.atlassian.com/git/tutorials/using-branches/git-merge

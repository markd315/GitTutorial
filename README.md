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
* [Deploy their work to Github Pages](#deployment)
* [Make a pull request from their fork](#sharing-your-work)
* [Undo common mistakes and maintain a clean git history](#troubleshooting)
* [Common terms](#glossary)

### Introduction
Welcome to the Project Management Bootcamp! The purpose of this bootcamp is to familiarize you with using the Trello and GitHub technologies. This bootcamp is intended for first semester computer science students to complete at the beginning of their first programming course. The bootcamp is going to be centered around developing your own website. We are going to use Trello to break down this task into smaller sub-tasks, and GitHub to keep track of your code and host your website. Please note that this bootcamp consists of two activities, and that you can complete them in separate sittings. However, the second activity is a continuation of the first, so you will need to complete the first one in order to work on the second one. 


### Trello Tracking
To begin using Trello, go to Trello.com and click either the create an account button in the center of the screen, or the Sign Up button in the top right corner of the screen. Once you have created your account, open this [link](https://trello.com/b/jKd6uW68/project-management-bootcamp) in a new tab.

This board serves as a breakdown of our project. However, you are unable to edit this board; you must clone your own version of it. To do this, click on the '... More' button in the Menu on the right side of your screen, and click Copy Board. You can name your version of the board whatever you would like. Once you are on your new board, take a look at your To Do list. You should see a card called 'Setup Trello and move my first card'. Drag this card from To Do to completed, and your first [issue](#issue) is complete!

Now that we have Trello all set up, we are going to get into Git and GitHub. 


### Git Explainer
 * What is Git?

Git is a version control system. Essentially, what this means is that Git tracks changed files and helps coordinate collaboration between multiple people that are working on the same thing. 

Before you can start working, you are going to need to do a couple of things. First, you need to download Git, which can be found at https://git-scm.com/downloads. Next, you need to create a GitHub account. This can be done by going to https://github.com/ and following the on screen instructions. Once you have your account set up and ready to go, you are going to go ahead and copy some files that have already been created for you to work with by forking an existing repository. However, before you do this, make sure to go back to your Trello board and move your 'Setup Github Account' card to completed! It is a good habit to mark things as complete as soon as they are finished to keep track of your progress.

Note: There is also an 'in-progress' section on the Trello board which we haven't used yet. Essentially, this is because the tasks we are doing are relatively quick, and we are the only person working on them so we don't need to keep people updated. If you were on a team, people would need to know what is in progress so that they don't repeat work that is currently in the process of being completed.

### Forking
  * What is forking?

[Fork](#fork)ing is a process by which you copy someone elses (remote) project in to your own (remote) repository. This allows you to make changes to your personal copy without compromising their project. 

For this activity, we are going to start with forking this repository: https://github.com/markd315/GitTutorial

To do this, click the link above, and then look for the Fork button highlighted below in red.
![Click the red button to fork the repository](/tutimg/fork.png)

Great! We've forked the repository so that you can make whichever changes you want.

### Cloning

However, we aren't ready to work on it just yet. Right now, the [fork](#fork)ed repository only exists on GitHub. In order to make changes on your machine, we are going to need to clone the repository.
  * What is cloning?

[Cloning](#clone) is the process of creating a local version of a repository to work on. While there are multiple ways to [clone](#clone) a repository, we are going to use Git to do this.

Open Git and navigate to /c/Users/your_username, which may just show up as a ~. If you are having trouble finding it, you can use ls to look at the available choices for where you are currently. If you see Users or your_username, use the cd (change directory) command to get to the desired destination. This means you should type 'cd Users' or 'cd your_username' to change to these locations. If you don't see either of them, you can use 'cd ..' to just move back one level and then try ls again until you find where you need to be.
Once you have made it to the correct location, type in the following command to clone your newly forked repository:

```
$ git clone https://github.com/YOUR_GITHUB_NAME/REPOSITORY_NAME
```

You are going to have to replace the two vague fields in this link with your personal GitHub account Name, and the repository name GitTutorial. Once you have successfully cloned this, do cd GitTutorial to change your directory to the GitTutorial. 

### Tracking Work

Now that we have a local copy of the repository, we can make our first change. 

Open up your notepad and type some text; anything you'd like. Now go ahead and save the file (call it whatever you'd like, as long as it isn't the same name as a text file in your project folder), and when prompted to choose the destination to save the file to, navigate to the folder that was created when you cloned the repository. This is going to be located in C:/Users/(your_user_name_on_your_computer)/GitTutorial
Once you have navigated to that folder and saved your file, we are going to head back to Git to push our local changes to the GitHub repository.

If you type git status, you can see the name of the file that you added. In order to add the file to the staging area, you can type 
```
$ git add --all.
```

Alternatively, when adding files you could just specify the file name e.g. 'git add "filename"' However, using git add --all just adds every single new or changed file to the staging area. Once you have done that, you have to do git commit -m "My first commit". Make sure to include quotations around your message following the -m. You can replace the text inside the quotations with anything you'd like, but it is required to put some message in there.

After you have added and [commit](#commit)ted, you can type 'git push'. If you did everything correctly, you can go to your online repository to view your changes! Also, make sure to go on your Trello and move the "Push a file to my GitHub" card to the completed section.

You are probably thinking to yourself, "wow, that was pretty easy." However, the purpose of Git (and what differentiates it from a more naive way of simply backing up your work) is for release management and conflicts that arise when multiple people are working on a project. With that being said, let's take a look at some ways to manage working with multiple people.

### Branch Management
Now that we have our tools all set up, we can begin to work on the actual project. Go ahead and take a moment to look at how your site is currently going to end up looking (if no changes were to be made) by going to your browser and going to the markd315.github.io/GitTutorial Notice that there are multiple parts of the page, and take a look at the favorite cuisine section. Right now, there are four tasty things listed. However, imagine that you are a lover of Thai food, and it slipped your mind that you forgot to add it to the list! Luckily for you, we have made it easy for you to do so. Just go ahead and go into your cloned GitHub repository and merge the feature-add-thai-food branch into the master branch... but wait, what's a branch?

A [branch](#branch) is just a starting [commit](#commit) (prior to which all other commits are common), followed by a list of commits exclusive to the branch (as well as any children).

It's a way of tracking alternate versions of file history, for example you could:

```
Make commit A on master (the starting branch)

Create branch 2 and check it out (meaning new commits go here).

Make commit B.

Create branch 3 and check it out.

Make commit C.

Check out branch 2 again.

Create branch 4 and check it out.

Make commit D
```

The (ordered) list of commits each branch would have following this exercise (from oldest to newest) are:
master(A)
2(A, B)
3(A, B, C)
4(A, B, D)

Refer to the diagram for a visualization.

![console](/tutimg/branches.png)

Each [commit](#commit) could represent a different feature, or parts of a feature, like A is starting the project, B is adding contact info, C is a bugfix that improves security, and 


Given that each commit represents a "difference" between old and new versions of the codebase, we need to represent these parallel code versions with alternate histories.

These histories *can* have some changes in common with each other (especially prior to the branch time), but must handle having different commits from each other.

Given the similarities between branches, it's very important to keep them straight in your head! Check out the [troubleshooting section](#troubleshooting) if you make a mistake, but these tips can help you keep it straight.

Any implementation of git bash should tell you exactly what branch you're on in parentheses when you view it in the console, and we can change between them with a git checkout as we show below.

![console](/tutimg/console.png)

Branch naming conventions dictate that we always branch off of (when we start a feature) and merge back into (when we deliver a feature) a main branch, usually named develop or master (many projects will have both).

This means that the main branch should be the base for any merges or pull requests, and the feature branch will be the target/comparison branch.

In the following diagrams, a movement to the right constitutes a passage of time, and a circle constitutes a single commit to the branch.

A new row+color should be interpreted as being on a distinct branch.

![Create a new branch and check it out](/tutimg/gitcheckout.png)

As we can infer from the diagram, both branches have the first commit in common, but after they branch they each contain 2-3 different commits (representing work on different features).

A major goal of branch management is to combine work that *was* done in parallel by multiple authors to a single, releasable version with all of the features and bugfixes included.

In order to do this, we need to merge a target branch into a base branch.

The way to do this is by switching to the branch we want to merge, and then switching back to the base branch and running

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

As such, the golden rule of rebasing is the *exact opposite* of the one for merges or pull requests. One is to never rebase while you have a main branch checked out, like develop, test, or master. Always check out the feature first.

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

Back to our example, try merging the branch "feature-add-thai-food" into your master branch, and then reload the website. If you are getting an error, make sure that you changed to the branch (by doing git checkout feature-add-thai-food), and then changed back to master afterwards. Refer to the code below:

```
$ git checkout feature-add-thai-food
$ git checkout master
$ git merge feature-add-thai-food
```
When a page pop ups after this, just type :wq. This essentially just saves and quits this pop up. After that, do
```
$ git push
```

This all assumes that the user can read and write to all of the necessary branches.

If all of this worked, go ahead and move the 'Create webpage content (Add links by merging branch)' card on your Trello board to complete. If you take a look at your GitHub repository on the GitHub website, you'll see that the index.html file on master has been updated with our new choice of food! If you ran into an issue, please refer to the [troubleshooting section](#troubleshooting)

In many cases, an organization will write-protect their master, test and develop branches so that the leadership can perform code reviews, unit and integration testing, and other quality controls for their codebase.

In all of these cases, merges must be handled on the remote repository through ***pull requests***.

These are a forum thread of sorts, where affected users can review the changes, request new ones, comment on style, and approve the details of the merge before it hits the main branches of their codebase.

See the [sharing your work section](#sharing-your-work) on how to create one.

As a project manager, configuring your repository to require pull requests is simple, we just need to protect certain branches with a *rule*.

Navigate to Settings>Branches>Add new rule in your Github repository and change the settings as desired. Make sure to save them before leaving.

![Project branch settings](/tutimg/branchprot.png)

This was the end of activity 1! We hope that you gained some insight into branches, commits, forking and cloning. However, these are just some of the basic parts of version control and project management. Additionally, we haven't encountered any issues yet.. move forward onto the next activity and you will learn how to deal with merge conflicts, some other general troubleshooting, and even learn how to turn this repository into a webpage!

### Merge Conflicts

Now that we have our favorite food listed, we still have a pretty ugly part of our website: the creators note. Luckily, there is another branch in your GitHub repository called creators-note. In this branch, the placeholder creator's note text is replaced with something else. Additionally (and this will cause our issues), the favorite cuisines are updated, just like in the thai food branch. Let's go ahead and make these changes.

Go on Git, and head over to the creators-note branch (git checkout creators-note) Once we are on this branch, we are going to change right back to master (git checkout master), and simply merge the creators-note branch into master like we did for the features-add-thai-food branch, by running (git merge creators-note) However, it appears we have run into a 'merge conflict'

* What is a merge conflict?

A merge conflict occurs when a user tries to make a change to an outdated version of master. In this case, master started out with only four cuisines. In branch features-add-thai-food, we added Thai Food to our list of cuisines, and made this become master's list of cuisines by doing git push. However, in the creators-note branch, we are still on a list with only four cuisines. The main problem here is that we are trying to add American food where Thai Food has already been placed. To deal with the merge conflict, we are going to start by opening up a tool to help us, by opening up the file.

```
<<<<<<< HEAD
<a href="https://en.wikipedia.org/wiki/American_cuisine">American food.. because Thai food isn't as good</a>
=======
<a href="https://en.wikipedia.org/wiki/Thai_cuisine">Thai food</a>

>>>>>>> feature-add-thai-food
```

You should see something more or less like this, with branch names (HEAD and feature-add-thai-food) and lines of code that are separated by the ===== divider. What we need to decide is which versions of the line of code we are going to keep.

If you want to only keep one, you can just highlight the other (from the <<<< branch name all the way to the ==== divider), delete it, and delete the other branch name line as well.

Basically, you're expected to remove all of the dividers and branch names, leaving only the exact code you want.

If you want to try adding both American and Thai food, you'll have an additional formatting issue.

HTML seperates lines of text with 

```
</br>
```

so make sure to enter a new one between the two links if you want to maintain the line spacing.

Once all the dividers, branch names, and any unwanted code are gone, run 

```
$ git add --all
$ git commit -m "Fixed merge conflict"
```

in the console window to update the master branch with the merge resolution.


If this worked succesfully for you, go ahead to your Trello Board and move the creators note card to the completed section. If you had any trouble, refer to the [troubleshooting section](#troubleshooting) 

### Deployment
Now that our favorite cuisines are properly documented and there is only good ol' English on our site, we are ready to order deploy our project to the world. To do this, we need to change two settings, so on the main page for your repository on GitHub click settings.
![Change the name](/tutimg/pagesSetting1.png)

First, make sure to name the project exactly the same as YOUR github username. The example above is for a user (or organization) named CEN3031-10A.

Save the rename, and secondly, scroll all the way down to the Github Pages section of this settings page.

Make sure the dropdown box is set to build from master, save your changes again and refresh the page.

If you did everything right, it should look like the following and your link will redirect to your site! Please move your final card on your Trello board to complete.

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

Press the 'i' key to change any of the following text shown in vim.
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

### Glossary

###### Branch
A branch is a parallel version of a repository. It is contained within the repository, but does not affect the primary or master branch allowing you to work freely without disrupting the "live" version. When you've made the changes you want to make, you can merge your branch back into the master branch to publish your changes. For more information, see "About branches."

###### Clone
A clone is a copy of a repository that lives on your computer instead of on a website's server somewhere, or the act of making that copy. With your clone you can edit the files in your preferred editor and use Git to keep track of your changes without having to be online. It is, however, connected to the remote version so that changes can be synced between the two. You can push your local changes to the remote to keep them synced when you're online.
er.

###### Commit
A commit, or "revision", is an individual change to a file (or set of files). It's like when you save a file, except with Git, every time you save it creates a unique ID (a.k.a. the "SHA" or "hash") that allows you to keep record of what changes were made when and by who. Commits usually contain a commit message which is a brief description of what changes were made.

###### Diff
A diff is the difference in changes between two commits, or saved changes. The diff will visually describe what was added or removed from a file since its last commit.

###### Fetch
Fetching refers to getting the latest changes from an online repository without merging them in. Once these changes are fetched you can compare them to your local branches (the code residing on your local machine).

###### Fork
A fork is a personal copy of another user's repository that lives on your account. Forks allow you to freely make changes to a project without affecting the original. Forks remain attached to the original, allowing you to submit a pull request to the original's author to update with your changes. You can also keep your fork up to date by pulling in updates from the original.

###### Issue
Issues are suggested improvements, tasks or questions related to the repository. Issues can be created by anyone (for public repositories), and are moderated by repository collaborators. Each issue contains its own discussion forum, can be labeled and assigned to a user.

###### Merge
Merging takes the changes from one branch (in the same repository or from a fork), and applies them into another. This often happens as a pull request (which can be thought of as a request to merge), or via the command line. A merge can be done automatically via a pull request via the GitHub web interface if there are no conflicting changes, or can always be done via the command line. For more information, see "Merging a pull request."

###### Pull
Pull refers to when you are fetching in changes and merging them. For instance, if someone has edited the remote file you're both working on, you'll want to pull in those changes to your local copy so that it's up to date.

###### Pull request
Pull requests are proposed changes to a repository submitted by a user and accepted or rejected by a repository's collaborators. Like issues, pull requests each have their own discussion forum. For more information, see "About pull requests."

###### Push
Pushing refers to sending your committed changes to a remote repository, such as a repository hosted on GitHub. For instance, if you change something locally, you'd want to then push those changes so that others may access them.

###### Remote
This is the version of something that is hosted on a server, most likely GitHub. It can be connected to local clones so that changes can be synced.

###### Repository
A repository is the most basic element of GitHub. They're easiest to imagine as a project's folder. A repository contains all of the project files (including documentation), and stores each file's revision history. Repositories can have multiple collaborators and can be either public or private.

### References

https://www.atlassian.com/git/tutorials/using-branches/git-merge
https://stackoverflow.com/questions/161813/how-to-resolve-merge-conflicts-in-git/7589612#7589612
https://help.github.com/articles/github-glossary/

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

### Trello Tracking
Welcome to the Project Management Bootcamp!
//TODO trello



### Git Explainer
//TODO what is git

 Before you can start working, you are going to need to create a GitHub account, which can be done by going to https://github.com/ and following the on screen instructions. Once you have your account set up and ready to go, you are going to go ahead and copy some files that have already been created for you to work with by forking an existing repository.

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

git clone https://github.com/YOUR_GITHUB_NAME/REPOSITORY_NAME

You are going to have to replace the two vague fields in this link with your personal GitHub account Name, and the repository name GitTutorial.

### Tracking Work

Now that we have a local copy of the repository, we can make our first change. 

Open your file explorer and navigate to the folder that was created when you cloned the repository. This is going to be located in
C:/Users/(your_user_name_on_your_computer)/GitTutorial. Once you have navigated to that folder, go ahead and make a new text file. You can call it whatever you'd like, and you can type any content you would like in the text file. Once you are done with that, we are going to head back to Git to push our local changes to the GitHub repository.

If you type git status, you can see the name of the file that you added. In order to add the file, you can type git add --all.

Once you have done that, you have to do git commit -m "My first commit". You can replace the text inside the quotations with anything you'd like, but it is required to put some message in there.

After you have added and committed, you can type git push. If you did everything correctly, you can go to your online repository to view your changes! 


### Branch Management
//TODO  Change branches and create new ones
//Should be taught how to create a branch, recall which branch they're on, and checkout existing branches
//Make sure to emphasize that they should pull work that might be on the remote version but not local

### Git Collaboration
//TODO Pull in work from other contributors
//Create a branch with existing changes for the user to merge into his code
//Have him perform the merge and guide him through remembering which branch he's on.

### Merge Conflicts


### Troubleshooting
//TODO Correct common mistakes and maintain a clean git history

//Include what to do if you make changes without pulling first (git stash and git stash pop)


Maybe sometimes you'll accidentally enter some changes, or a git commit that you want to undo.

If you haven't pushed it to the remote repository yet, this is quite easy! We still have a valid copy of the branch stored *on* the remote repository, so we can just access it by [resetting to the remote repository](#remote-undo).

If you've also already pushed it, you're in a little bit more trouble just because we don't want to rewrite the history on remote branches once it's established. The best way to revert a single bad commit locally is to employ the [git revert](#synchronize-revert-and-push).

#### Remote undo
Simply run this command
$ git reset --hard origin/master

(replacing the master branch if necessary)


#### Synchonize revert and push
First, syncronize the remote and local branches with

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

Sometimes, it is good practice to rewrite history, especially by reducing the amount of commits to reflect individual units of work. This is called a "squash", in which you combine several commits into one.

This is a good way to make reversions disappear too: since we're already rewriting history. If you do something in one commit and then undo it in another commit our log will still reflect both of those changes, but if we squash the work into one commit then both will disappear.

There doesn't appear to be a single, industry-standard way to make a git squash from the command line and instead there are a couple techniques that will vary by situation. In a case where you want to rebase every commit since the target branch was created, I would use the [soft reset method](#soft-reset-squash).

In any other case (or if you just want to learn one technique, I would use the [interactive rebase method](#interactive-rebase-squash)

#### Soft reset squash
First, we need to undo all of the commits from our history, *without* actually losing the work.
This is called a soft reset and it's very important to not confuse it with a hard reset.

Once again, in a soft reset we undo every commit since the reset point, but a hard reset means that we *also* throw away all our work since that point.

$ git reset --soft origin/master

$ git add --all
to track all of the changed files

$ git commit -m "Your commit message here"
to make a new commit

$ git push
to update the remote branch corresponding to our local.

#### Interactive rebase squash
This method will rewrite remote history and is therefore not advisable without a backup.



$ git rebase -i master

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

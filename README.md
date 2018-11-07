# Git and GitHub Tutorial

###### Credits: Mark Davis, Greg Harmon

### Learning Goals:
* Track progress and assignments with Trello
* Understand Git and Github
* Fork a repository
* Clone it locally
* Commit work that they did
* Change branches and create new ones
* Pull in work from other contributors
* Resolve merge conflicts with concurrent work
* Undo common mistakes and maintain a clean git history
* Deploy their work to Github Pages
* Make a pull request from their fork, targeting the initial repository.

//TODO trello



//TODO what is git

Welcome to the Project Management Bootcamp! Before you can start working, you are going to need to create a GitHub account, which can be done by going to https://github.com/ and following the on screen instructions. Once you have your account set up and ready to go, you are going to go ahead and copy some files that have already been created for you to work with by “forking” an existing repository.
  * What is forking?

Forking is a process by which you copy someone elses (remote) project in to your own (remote) repository. This allows you to make changes to your personal copy without compromising their project. 

For this activity, we are going to start with forking this repository: https://github.com/markd315/GitTutorial

To do this, click the link above, and then look for the Fork button highlighted below in red.
![Click the red button to fork the repository](/tutimg/fork.png)

Great! We've forked the repository so that you can make whichever changes you want.

However, we aren't ready to work on it just yet. Right now, the forked repository only exists on GitHub. In order to make changes on your machine, we are going to need to clone the repository.
  * What is cloning?

Cloning is the process of creating a local version of a repository to work on. While there are multiple ways to clone a repository, we are going to use Git to do this. You are going to need to download Git, which can be found at https://git-scm.com/downloads 

Once you have Git installed, go ahead and open it and type in the following command to clone your newly forked repository:

git clone https://github.com/YOUR_GITHUB_NAME/REPOSITORY_NAME

You are going to have to replace the two vague fields in this link with your personal GitHub account Name, and the repository name GitTutorial.

Now that we have a local copy of the repository, we can make our first change. 

Open your file explorer and navigate to the folder that was created when you cloned the repository. This is going to be located in
C:/Users/(your_user_name_on_your_computer)/GitTutorial. Once you have navigated to that folder, go ahead and make a new text file. You can call it whatever you'd like, and you can type any content you would like in the text file. Once you are done with that, we are going to head back to Git to push our local changes to the GitHub repository.

If you type git status, you can see the name of the file that you added. In order to add the file, you can type git add --all.

Once you have done that, you have to do git commit -m "My first commit". You can replace the text inside the quotations with anything you'd like, but it is required to put some message in there.

After you have added and committed, you can type git push. If you did everything correctly, you can go to your online repository to view your changes! 



//TODO  Change branches and create new ones
//Should be taught how to create a branch, recall which branch they're on, and checkout existing branches
//Make sure to emphasize that they should pull work that might be on the remote version but not local


//TODO Pull in work from other contributors
//Create a branch with existing changes for the user to merge into his code
//Have him perform the merge and guide him through remembering which branch he's on.


//TODO Correct common mistakes and maintain a clean git history
//Include info on squashing commits and performing resets here.
//Include what to do if you make commits without pulling first
//Include what to do if you commit bad work to master (reverting commits)
//Include git stash and git stash pop

In order to deploy our project, we need to change two settings, so on the main page for your repository click settings.
![Change the name](/tutimg/pagesSetting1.png)

First, make sure to name the project exactly the same as YOUR github username. The example above is for a user (or organization) named CEN3031-10A.

Save the rename, and secondly, scroll all the way down to the Github Pages section of this settings page.

Make sure the dropdown box is set to build from master, save your changes again and refresh the page.

If you did everything right, it should look like the following and your link will redirect to your site!

![Set the branch to Master](/tutimg/pagesSetting2.png)

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

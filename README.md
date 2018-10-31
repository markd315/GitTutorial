# Git and GitHub Tutorial

###### Credits: Mark Davis, Greg Harmon

### Learning Goals:
* Create a GitHub account, 
* Fork a repository
* Clone it locally
* Commit work that they did
* Deploy their work to Github Pages
* Make a pull request from their fork, targeting the initial repository.


Welcome to the Project Management Bootcamp! Before you can start working, you are going to need to create a GitHub account, which can be done by going to https://github.com/ and following the on screen instructions. Once you have your account set up and ready to go, you are going to go ahead and copy some files that have already been created for you to work with by “forking” an existing repository.
  * What is forking?

Forking is a simple process in which you copy someone elses project in to your own repository. This allows you to make changes to your personal copy without compromising their project. 

For this activity, we are going to start with forking this repository: https://github.com/markd315/GitTutorial

To do this, click the link above, and then look for the Fork button highlighted below in red.
![Click the red button to fork the repository](/tutimg/fork.png)


Great! We've forked the repository.

However, we aren't ready to work on it just yet. Right now, the forked repository only exists on GitHub. In order to make changes, we are going to need to clone the repository.
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

In order to deploy our project, we need to change two settings, so on the main page for your repository click settings.
![Change the name](/tutimg/pagesSetting1.png)

//TODO more deploy Mark


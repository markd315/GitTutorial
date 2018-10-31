# Git and GitHub Tutorial

###### Credits: Mark Davis, Greg Harmon

### Learning Goals:
* Create a GitHub account, 
* Fork a repository
* Clone it locally
* Commit work that they did
* Deploy their work to Github Pages
* Make a pull request from their fork, targeting the initial repository.

Activity Instructions:

Fork this repository: https://github.com/markd315/GitTutorial

Click the link, and then look for the Fork button highlighted below in red.
![Click the red button to fork the repository](/tutimg/fork.png)


Great! We've forked the repository.

//TODO greg, show how to clone and make local changes

//TODO greg, show how to make 

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

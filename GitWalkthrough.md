# 1.1 - CHOOSE A GIT MASTER
Choose a Git Master for your team
Since everyone on your team will be pushing code to the same GitHub repository, one
person in your group needs to take on the roll of 'Git Master'. The Git Master will
simply be responsible for merging everyone's code on GitHub, into one single branch
(master branch). We'll talk more about branches in a bit.
Once your team decides on a Git Master, the Git Master is responsible for setting up
the necessary folder structure, and creating the Git repository.
* The Git Master is responsible for the rest of steps in Step One (1.2, 1.3, 1.4, 1.5, 1.6).
Please make sure the Git Master is sharing their screen while completing the next few
steps so the rest of the team can follow along!1.1.1 - FOLDER STRUCTURE
Set up your folder structure
The Git Master needs to set up the initial folder structure and files so they can initialize
a Git repository, and then push their code to GitHub.
Create a new folder on your desktop (or wherever you want to store it), and name it
teamGit.
Once you have created the new folder, open up VSCode, and then open the teamGit
folder in VSCode itself.
In VSCode
Create an index.html file in the parent teamGit folder
Use the '!+tab' shortcut to generate your boilerplate HTML, and then add the
following line of code to the body:
<h1>Master Branch</h1>
Your index.html file should look like the image belowCommand prompt/terminal
Open a new command prompt or terminal window, and navigate (cd/ls) to the teamGit
folder we created earlier (You can also open a terminal in VSCode if that's easier for
you)
Once you are in the teamGit directory, run the following commands in the command
prompt/terminal to initialize a new Git repo:
git init
git add .
git commit -m "message"
After running the above commands, run a
git status
and make sure your console reads, "nothing to commit, working tree clean".1.1.2 - CREATE GITHUB REPOSITORY
Create a new GitHub repository
Navigate to https://github.com/ (https://github.com/) and sign in if necessary.
Name the repository 'teamGit', and then create the repository.
Copy the 2 lines of code from the ". ..or push an existing repository from the command line" section
into your command prompt/terminal, and hit enter.
git remote add origin https://github.com/<your user name>/teamGit.git
git push -u origin master
After hitting enter, your code should push, and you're good to go!
In the upper right hand corner of the screen, click the '+' icon, and then select New Repository to
create a new repository. When you clone you will get all branches currently on github repository.1.1.3 - ADD COLLABORATORS
Add your team to the GitHub repository
Now that we have the code pushed to GitHub, we need to invite the rest of our team
members as collaborators.
To do this, navigate to the 'Settings' tab in the repository toolbar (very far right).
Once in the settings tab, select 'Manage Access' from the left menu panel.
Click the green 'Invite a collaborator' button at the bottom of the screen, and proceed
to invite your group members by either GitHub username or the email address
attached to their GitHub account.1.1.4 - CREATE A DEVELOP BRANCH
What are branches?
When we create a new repository, our code is attached to a branch named master by default. The
master branch is considered the 'main' branch, and generally reflects a 'production ready' state. The
master branch is also the branch of code that is most largely looked at when deploying an
application. So if our master branch is working with finished "production" code, and that code is
what's being looked at when deployed - we probably don't want multiple members of a team all
pushing code to a singular master branch that contains deployed, working code.
That's where branches come in
Branches
Branches give you the ability to 'branch off' from the default master branch, and create new
branches that generally represent the different stages of our code during development.
Here's an image to help explain.Each circle in the above picture represents a commit and push of our code to GitHub, that lives on
it's own branch until merged with another branch.
Your 'tree' currently looks like this:
Create
Off of our master branch (which we get by default from GitHub), we want to create a new branch
called 'develop'. The develop branch serves as a integration branch for features (which also have
their own branches), or in our case, multiple developers each working on their own piece of the
application.First, lets check what branch we're currently on (make sure you're still in the teamGit directory in
your command prompt/terminal).
git branch
We should see that we're currently on master branch, so if we want to create a new branch run the
following command:
git checkout -b develop
This will not only create a new branch, but automatically switch us to that branch as well. If you run a
'git branch' command again, you should see that you're now on the develop branch.
Switching branches
To switch between branches, run:
git checkout <branch name>
Deleting a branch
To delete a branch, run:
git branch -d <branch name>1.1.5 - UPDATE CODE/PUSH DEVELOP BRANCH
Add code to develop branch
Now that we have a develop branch, we want to add some code to it!
Go ahead and switch back over to VSCode (and make sure you're on branch develop!)
VSCode
Once you're in VSCode and on your develop branch, lets add the following line of code under our
<h1> tag:
<h2>Develop Branch</h2>
You should now have the following:
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Document</title>
</head>
<body>
<h1>Master Branch</h1>
<h2>Develop Branch</h2></body>
</html>
Command prompt/terminal
Now that we've added some new code on the develop branch, lets push that new branch and new
code to GitHub.
Switch back to your terminal window and run a 'git status'. You should see the following after running
a 'git status' command:
On branch develop
Changes not staged for commit:
(use "git add <file>..." to update what will be committed)
(use "git restore <file>..." to discard changes in working directory)
Since we have changes not staged for commit, we need to add, commit, and push those changes to
GitHub:
git add .
git commit -m "pushing deployment branch"
git push
Since we don't want to push code that's on our develop branch to the master branch, we just want to
run the 'git push' command instead of 'git push origin master'.
Running just 'git push' should give you an error saying:
fatal: The current branch develop has no upstream branch.
To push the current branch and set the remote as upstream, usegit push --set-upstream origin develop
Running the above command will set the upstream for our develop branch so it only pushes to the
develop branch.
Testing
With our new code that we wrote in the develop branch now pushed to GitHub, we should be able to
switch back to our master branch ('git checkout master') and see that it does NOT contain the new
<h2> tag we wrote - it only contains
<h1>Master Branch</h1>
Why is that? Our development branch is now 1 commit ahead of our master branch. It contains code
that has not yet been merged into the master branch.
Our tree currently looks like this:1.2 - CLONE REPO
Clone Repository
With the Git Master doing all of the heavy lifting so far, it's now time for the rest of the team to clone
what the Git Master has been working on!
Have the Git Master send out a link to the teamGit GitHub repository, and then click the green 'clone
or download' button, and copy the supplied link.
Command prompt/terminal
Open a new command prompt/terminal window, and navigate to your desktop (or wherever you
want to store the project).
After navigating to the directory you want to store the project in, run:
git clone <paste in linked copied from github>
Running the above command should start the cloning process. After it completes, you can navigate
(cd, ls) into the new project folder.
After opening the folder in VSCode, in your command prompt/terminal, you should be able to switch
to the develop branch ('git checkout <branch name>') that the Git Master created, and see the
additional line of code containing the <h2> tag.*** You can also switch branches within VSCode by clicking the text 'master' in the bottom left hand
corner of the VSCode window, as pictured below. Clicking 'master' at the bottom of the screen will
populate the dropdown menu that's circled in the image. From this dropdown menu, you can select
which branch you want to switch to.1.3 - CREATE NEW BRANCHES
Each team member should now create their own branch that is their name
For example:
master
develop
zach
eric
ing
Your individual branches are where you will do a majority of your coding during your project. Each
team member should be working exclusively off of their own branch, and not writing code on the
develop or master branches. The develop branch is meant for testing code that's still in development
or hasn't been deployed before, and making sure it works locally before merging all of the code with
master branch.
Since we want our individual branches to be branching off of the develop branch and not the master
branch, make sure you have switched to the develop branch before creating your own branch.
The command to switch to the develop branch is:
git checkout develop
Once you get switched to the develop branch, you can run the following command to create and
switch to a new branch:git checkout -b <your name>
Make a change in your code (on your own branch)
Now that we have created our own branch, we want to add to our code, and then push our new
branch and the changes in our code up to GitHub.
Each team member should add an <h3> tag under the <h1> and <h2> tags, with their own name.
You should have something similar to the following afterwards:
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Document</title>
</head>
<body>
<h1>Master Branch</h1>
<h2>Develop Branch</h2>
<h3>Zach's Branch</h3>
</body>
</html>
After you've added the <h3> tag to your code, run the following commands to add, commit, and
push to GitHub:
git add .
git commit -m "zachs branch"git push
Like before, when we push our code, we want to push specifically to the branch that we've been
writing code on. Since the change we made to our code was in a newly created branch, you should
get an error in your command prompt/terminal when running 'git push', telling you that you need to
set the upstream for your current branch. The command it gives you to run should look similar to
below, but will obviously have your own branch name.
git push --set-upstream origin <your branch name>
At this point, we're almost done! Each member of your group should have their own branch, their
own <h3> tag with their branch name, and should have pushed their branch/code to GitHub.
All that's left is having each member of your team merge their code up from their own branch to the
develop branch. Once each member of your team has merged to the develop branch and everything
is working, your Git Master can then merge the develop branch with the master branch - which will
simulate our "production ready" code.
Our tree should now look like this:1.4 - MERGE PERSONAL BRANCH TO DEVELOP
BRANCH
Merging your personal branch with the develop branch
*** each group member should merge individually from their team members (do not all merge your
branches at once). If everyone tries to merge their code all at once, it's more than likely that you'll
run into merge conflicts. After one student has successfully merged their code to the develop
branch, the next student can then merge their code with the develop branch, until everyone on your
team has merged their own code into develop.
Merging branches within GitHub
Navigate back to the teamGit repository in GitHub. You should now be able to see everyone's
individual branches in GitHub by clicking on the 'Branch:' button, or by clicking the 'branches' tab in
the toolbar (pictured below)Click the 'New pull request' button directly to the right of the branches button.Under the 'Open a pull request' heading, you should see two buttons with a leftward facing arrow in
between them. This denotes what branches we want to merge together. In the left box, you should
select the develop branch, and in the right box, you should select your own branch (pictured below).
This denotes that we are merging the zach branch into the develop branch.After selecting the two appropriate branches, click the green, 'Create pull request' button.Finalizing the merge
After clicking the 'Create a pull request' button, you should be directed to a new page where we can
finalize the merge, and see if there are any conflicts with the merge we're trying to submit. The first
team member of your group that merges their own branch to develop should not run into any merge
conflicts, but the remaining two team members most likely will - and that's okay! We'll walk through
that in a bit.
You should be seeing something like the picture below at this pointAs long as there are no merge conflicts (again, whoever is merging first should not run into any), go
ahead and click the green 'Merge pull request' button.
After clicking the 'Merge pull request' button, a new button should pop up asking you to confirm the
merge. Click that button as well to confirm your merge.
You should now see a purple dialogue box that states that the 'Pull request has been successfully
merged and closed'. It also gives you an option to delete the branch we merged from, but since we
don't want to have to set up a new branch every time we merge our code, we do not want to delete
our branch.
Rinse and repeat
The remaining team members who have not yet merged their personal branches with the develop
branch should now do so (remember to go one at a time - be sure to communicate who is merging
and when you're done).
Since one of your team members has already merged their code with the develop branch, you will
more than likely run into a merge error while trying to merge your personal branch with the develop
branch. We'll walk through those steps together below
Merge conflicts
If you have a merge conflict after selecting which branches you want to merge, GitHub will give you
an error message like so (pictured below)Go ahead and click the green 'Create pull request' button. We can still merge even if there's a merge
conflict - we just have to make sure what we're trying to merge isn't overwriting someone elses code
that they merged to the develop branch!After you click the green 'Create pull request' button, you should be directed to a new page that
looks as follows:You will get a prompt telling you that there are conflicts that must be resolved before merging. Go
ahead and click the 'Resolve conflicts' button.
After click the 'Resolve conflicts' button, you will be directed to a page that actually shows you were
the conflict is. You should be seeing something similar to the image below, but with your own branch
names.
Here, our merge conflict is coming from line 12 of the code. Let's breakdown what's happening
above.
1. The red arrow is looking at the current branch that I'm trying to merge with the develop branch.
2. The purple arrow is showing us what's currently on line 12.
Both of lines of code are preceded or succeeded with the branch that they are tied to.Fixing the merge conflict
To fix the merge conflict, simply remove the branch names preceding or succeeding the lines of
code, and structure the code how you would like it to be structured. You should have something the
closely resembles the image below:
With the conflicts now resolved, we can now click the 'Mark as resolved' button in the upper right
hand corner of the screen. Clicking this button should populate a new, green button that we can click
to confirm the changes. Go ahead and click that button as well.
You should now be redirected back to the screen you were previously on, and you should now be
able to click the green 'Merge pull request' button, followed by clicking the green 'Confirm merge'
button.
You have now successfully solved a conflict and merged your branch with the develop branch!1.5 - FINAL MERGE
Merging Develop to Master
Once all of the team members have merged their personal branches with the develop branch, its
time for the Git Master to merge the develop branch with the master branch (follow the steps in the
previous module).
Once the merge from develop -> master is complete, go back to the teamGit repository in GitHub
and click the 'Insights' tab in the toolbar. In the left menu panel, select the 'Network' option. You
should be able to see a graph showing you the timeline of each commit/merge, etc (pictured below).Please take a sceenshot of the graph and send it via your team channel in Slack!1.5.1 - PULLING CODE TO LOCAL MACHINE COPY
Pulling all changes down from GitHub
Once the Git Master has merged the develop branch into the master branch, you can now pull those
changes into your personal branch. The merges we've completed so far have all been within GitHub,
so we need to pull those changes down to our local machines
Command Prompt/Terminal
In the command prompt/terminal, run the 'git branch' command to see which branch you're currently
on. If you're not on your personal branch, navigate to it using the following command:
git checkout <branch name>
Now that you're on your personal branch, you can pull all of the code that was just merged with
develop/master down to your branch - so you have everyones changes!
To pull down everyone's changes to your codebase, run the following command:
git pull origin <branch name>
The branch name you insert above should be either develop or master - they should both have the
same code at this point in time. It's generally a better idea to pull from the develop branch instead ofmaster, just in case you have code in the master branch that is specific to your deployed
application.
Just like we needed to pull the changes into our personal branch locally, we also need to do the
same with the master, and develop branches. First, switch to the master branch ('git checkout
master') and then run 'git pull origin master' - that will pull all of the changes that have been merged
into the master branch via GitHub onto your local machine. You can then do the same for the
develop branch.
Merge conflicts within VSCode
If you happen to have a merge conflict locally within VSCode when pulling down changes, you
should see something similar to what the merge conflict within GitHub itself showed you - it will show
you both your current code, and the incoming changes. Since we know that the develop/master
branches are up-to-date and correct, we can just 'Accept incoming changes'.
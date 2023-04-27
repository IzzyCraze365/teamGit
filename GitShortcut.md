# GIT MASTER (Quick Guide)

Terminal Window

    git init
    git add .
    git commit -m "message"
    git status


Console should read, `nothing to commit, working tree clean`

## CREATE GITHUB REPOSITORY

Navigate to https://github.com/ (https://github.com/) and sign in if necessary.

    git remote add origin https://github.com/<your user name>/teamGit.git
    git push -u origin master


# Branches
Check what branch we're currently on
    
    git branch


Create a new branch run the following command:

    git checkout -b develop


To switch between branches, run:
    
    git checkout <branch name>


To delete a branch, run:

    git branch -d <branch name>

## Terminal Window
Running a 'git status' command:

    On branch develop
    Changes not staged for commit:
    (use "git add <file>..." to update what will be committed)
    (use "git restore <file>..." to discard changes in working directory)


Changes not staged for commit, do following:

    git add .
    git commit -m "pushing deployment branch"
    git push


`NOTE` Running just 'git push' should give you an error saying:

    fatal: The current branch develop has no upstream branch.
    To push the current branch and set the remote as upstream, use
    git push --set-upstream origin develop



## Clone Repository

Terminal Window

After navigating to the directory run:

    git clone <paste in linked copied from github>


## Creating New Branches

The command to switch to the develop branch is:

    git checkout develop


Create new branches in `develop`:

    git checkout -b <your name>



Run the following commands to add, commit, and push the branch to GitHub:

    git add .
    git commit -m "johns branch"
    git push



### ERROR MESSAGE

You will recieve and error and a prompt in the terminal

    git push --set-upstream origin <your branch name>
    git push --set-upstream origin John



## Merging Branches

This is done exclusivly on GitHub

`ONLY ONE PERSON SHOULD PULL REQUEST AT A TIME!!!`

1. Click `Branches` Tab
2. Click `New Pull Request`
3. Make the the drop down menu is correct `base` <= `compare`
    you should see `Able to merge` with a green checkmark
4. Click `Create Pull Request`

As long as there are no merge conflicts (again, whoever is merging first should not run into any), go ahead and click the green 'Merge pull request' button.

### Merge Conflicts

1. Click `Branches` Tab
2. Click `New Pull Request`
3. Make the the drop down menu is correct `base` <= `compare`
    you should see `Can't automatically merge` with a red X
4. Click `Create Pull Request`
5. You will see a popup that says `This branch has conflicts that must be resolved`
6. Click the `Resolve conflicts` button
7. You will see a code view of the conflicted lines.

    To fix the merge conflict, simply remove the branch names preceding or succeeding the lines of code, and structure the code how you would like it to be structured.
8. With the conflicts now resolved, click the `Mark as resolved`

### Final Merge

This is the same process as above but you are merging the `develop` branch and the `main` branch.

## Keeping Locat Code Up-To-Date

### Inside the Command Terminal
Go into your personal branch

    git checkout <branch name>


To pull down everyone's changes to your codebase, run the following command:

    git pull origin <branch name>

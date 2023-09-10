# Basic Git Tutorial

## Introduction
### What is Git and GitHub

Git is a local version control system.
* The folders you are version controlling are called a git repository. 
* Allows the users to see the edit history of the files
* Allows multiple users to edit files at the same time without affecting the others(branching)

GitHub is a web service that hosts git repositories on the web.
* Allows easy sharing of files between users and devices
* The repository on GitHub is referred to as a remote repository
* Similar to cloud-based file storage apps such as Google Drive and Dropbox
* Must have Git on the local computer to use GitHub


### Document usage
For the following tutorial, the dollar sign `($)` represents commands in the terminal, and `<>` represents the part that you need to change based on your use case. Don’t include `<>` and `$` in the final command. **To make your life easier, DO NOT include spaces in any files and folder names!** [Git cheat sheet](chrome-extension://efaidnbmnnnibpcajpcglclefindmkaj/https://education.github.com/git-cheat-sheet-education.pdf)

## Basic Commands
To make a copy of the remote repository on your local machine(initial setup only)
```
$ git clone <url>
```

Update your local git repository with the remote repository (somewhat dangerous)
```
$ git pull
```

A safer way to get updates from a remote repository. But this won't change your local repository code. Usually use this to see a newly created branch on the remote repo.
```
$ git fetch
```

To see what files you modified in your local repository compared to the remote repository
```
$ git status
```

Add the modified documents to the staging area. The first line adds ALL modified documents. Alternatively, you can type the filenames individually, separated by a space.
```
$ git add .
$ git add <file name1> <file name2>
```

Commit changes(files in the staging area)
```
$ git commit -m “description of the commit”
```

Push the files in the staging area to the remote repository
```
$ git push
```

GitHub new branch. This is usually easier to do on the web browser on GitHub.com
```
$ git branch <branch name>
```

Switch to branch
```
$ git checkout <branch name>
```

Merge branches (merge branch A into branch B). Doing this on the web browser is usually easier.
```
$ git checkout <branch B name>
$ git merge <branch A name>
$ git push
```

## Typical initial setup
Navigate to your desired folder and open Git Bash(Windows) or Terminal(MacOS or Linux)
```
$ git clone <repo url>
```

## Typical workflow after cloning
Scenario: you want to push files to the remote repository
1. Make sure you are on the correct branch: 
```
$ git branch
$ git checkout <branch name>
```

2. Routine. When doing `git status` check if there are any files you did not change but it changed since the last commit. If it is not a desired change, DO NOT add it! 
```
$ git status
$ git add . OR $ git add <file name>
$ git commit -m “description of the commit”
```

If you are certain that you are the only one working on this branch you can skip `git pull`. `git pull` make sure your code is up to date with the branch on the remote repository, this step might break your code so make a local backup somewhere else just to be safe. After the pull, one of your code/text editors (typically VSCode) will open up a file asking you to type a commit message and/or resolve merge conflicts. If it’s the latter, manually choose which code to keep and which code to delete. In either case, there will be a MERGE file open. This is because an automatic OR manual merge requires to be saved in a commit. Type your message, save the file, and close it. Return to your terminal and you should be able to push. 

```
$ git pull
$ git push
```

## Pull Request
To make managing your contribution easier, you will need to submit a pull request when you are ready done with the feature you are working on.

When you are ready, go to github.com and switch to your feature branch. On the top, click on the contribute button

![Pull Request](media\PR1.png)

Make sure the merge status is able to merge. Resolve any conflict if there are. Write a description for the pull request then click create pull request.

![Pull Request](media\PR2.png)

## Try for Yourself
1. Clone this repository
2. Make a branch with the source as the `git_test` branch
	Make the branch name = your uniqname and then switch to that branch
3. Make some edits in the `edit_me.txt`, make sure you edit the line number you are assigned to
4. Make a pull request

## Common Errors
### Username and Password Incorrect:
You entered your username and password, it says your password is incorrect and need a personal access token

1. Go to github.com click your pfp on the top right > settings

![settings](media\settings.png)

2. Scroll down a lot to developer settings (left menu bar)

![dev settings](media\developer_settings.png)

3. Personal access tokens > Tokens (classics) > Generate new token > Generate new token (classic) 
4. Set the expiration date to be as long as possible, if you are using your personal machine.
5. Click the repo check box
6. Generate token
7. Copy the token and STORE IT SOMEWHERE SAFE. A text file on your local machine(not in any git repo) is recommended. You will never see this token again.
8. Use this token as your password

### Divergent Branch
When you try to pull from a branch, you might have this divergent branch warning.

![settings](media\divergent_branch.png)

There are several ways to resolve this issue depending on your situation:

1. Update your entire local repository to the remote one. Good for situations where you don’t have any important code on your local machine.

```
$ git fetch origin	
$ git reset --hard origin/<branch name>
```

2. Use merge. This is good when you are working on a branch and just want to pull the most recent changes from a remote repository to your local machine before you make a push. You have to resolve the merge conflict after pulling.
```
	$ git config pull.rebase false
	$ git pull
```

### Merge Conflict
When you and others work on the same file, and you both change the same line of code, git is confused on which one to keep and which one to discard.

If you are scared just do `$ git merge --abort` and it will restore your old files.

When you have a merge conflict, open your code in VScode. It will show green and blue boxes where conflicts arrive. 

![settings](media\merge_conflict.png)

The green box is the current change(your code) and the blue box is what is on the remote repository. Depending on the situation, you can choose the different options on the top.

After all the conflicts have been resolved
```
$ git status
$ git add <the files you just changed>
$ git commit -m “merge commit”
```

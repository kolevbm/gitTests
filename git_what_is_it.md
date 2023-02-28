What does Git do?
	Manage projects with Repositories
	Clone a project to work on a local copy
	Control and track changes with Staging and Committing
	Branch and Merge to allow for work on different parts and versions of a project
	Pull the latest version of the project to a local copy
	Push local updates to the main project

Working with Git:
	Initialize Git on a folder, making it a Repository
	Git now creates a hidden folder to keep track of changes in that folder
	When a file is changed, added or deleted, it is considered modified
	You select the modified files you want to Stage
	The Staged files are Committed, which prompts Git to store a permanent snapshot of the files
	Git allows you to see the full history of every commit.
	You can revert back to any previous commit.
	Git does not store a separate copy of every file in every commit, but keeps track of changes made in each commit!
	
```
git --version
git version 2.30.2.windows.1
```

## Configure Git

Now let Git know who you are. This is important for version control systems, as each Git commit uses this information:

Example:
```
>git config --global user.name "w3schools-test"
>git config --global user.email "test@w3schools.com"
```
>Note: Use global to set the username and e-mail for every repository on your computer.
>If you want to set the username/e-mail for just the current repo, you can remove global

## Git Staging Environment
One of the core functions of Git is the concepts of the Staging Environment, and the Commit.

As you are working, you may be adding, editing and removing files. But whenever you hit a milestone or finish a part of the work, you should add the files to a Staging Environment.

Staged files are files that are ready to be committed to the repository you are working on.

``` 
git add file.file
git add -all	# add / stage all files and ??directories??
```
## Git Commit
Since we have finished our work, we are ready move from stage to commit for our repo.

Adding commits keep track of our progress and changes as we work. Git considers each commit change point or "save point". It is a point in the project you can go back to if you find a bug, or want to make a change.

When we commit, we should always include a message.

By adding clear messages to each commit, it is easy for yourself (and others) to see what has changed and when.

Example
```
git commit -m "First release of Hello World!"
```
>The commit command performs a commit, and the -m "message" adds a message.
The Staging Environment has been committed to our repo, with the message:
"First release of Hello World!"

## Git Commit without Stage
Sometimes, when you make small changes, using the staging environment seems like a waste of time. It is possible to commit changes directly, skipping the staging environment. The `-a` option will automatically stage every changed, already tracked file.

And check the status of our repository. But this time, we will use the --short option to see the changes in a more compact way:

Example
```
git status --short
 M index.html
```

> __Note__: Short status flags are:
>
> -	?? - Untracked files
> -	A - Files added to stage
> -	M - Modified files
> -	D - Deleted files

## Git Commit Log
To view the history of commits for a repository, you can use the log command:

``` 
commit 33dc46f12c1a507dcc3edeec5e6c9aaf42559ffa (HEAD -> master)
Author: boris <kolev.bm@gmail.com>
Date:   Tue Feb 28 10:49:04 2023 +0200

    initial commit
```
## Git Help
If you are having trouble remembering commands or options for commands, you can use Git help.

There are a couple of different ways you can use the help command in command line:

`git command -help` -  See all the available options for the specific command

`git help --all` -  See all possible commands

## Working with Git Branches
In Git, a branch is a new/separate version of the main repository.

Let's say you have a large project, and you need to update the design on it.

How would that work without and with Git:

Without Git:

Make copies of all the relevant files to avoid impacting the live version
Start working with the design and find that code depend on code in other files, that also need to be changed!
Make copies of the dependant files as well. Making sure that every file dependency references the correct file name
EMERGENCY! There is an unrelated error somewhere else in the project that needs to be fixed ASAP!
Save all your files, making a note of the names of the copies you were working on
Work on the unrelated error and update the code to fix it
Go back to the design, and finish the work there
Copy the code or rename the files, so the updated design is on the live version
(2 weeks later, you realize that the unrelated error was not fixed in the new design version because you copied the files before the fix)
With Git:

With a new branch called new-design, edit the code directly without impacting the main branch
EMERGENCY! There is an unrelated error somewhere else in the project that needs to be fixed ASAP!
Create a new branch from the main project called small-error-fix
Fix the unrelated error and merge the small-error-fix branch with the main branch
You go back to the new-design branch, and finish the work there
Merge the new-design branch with main (getting alerted to the small error fix that you were missing)
Branches allow you to work on different parts of a project without impacting the main branch.

When the work is complete, a branch can be merged with the main project.

You can even switch between branches and work on different projects without them interfering with each other.

Branching in Git is very lightweight and fast!

## New Git Branch
Let add some new features to our index.html page.

We are working in our local repository, and we do not want to disturb or possibly wreck the main project.

So we create a new branch:

Example

```git branch hello-world-images```

Now we created a new branch called "hello-world-images"

Let's confirm that we have created a new branch:
Example
```
git branch
  hello-world-images
* master
```

We can see the new `branch` with the name "hello-world-images", but the `*` beside `master` specifies that we are currently on that branch.

`checkout` is the command used to check out a `branch`. Moving us from the current branch, to the one specified at the end of the command:
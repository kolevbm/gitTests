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
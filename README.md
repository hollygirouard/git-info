### Git Materials 

[![General Assembly Logo](https://camo.githubusercontent.com/1a91b05b8f4d44b5bbfb83abac2b0996d8e26c92/687474703a2f2f692e696d6775722e636f6d2f6b6538555354712e706e67)](https://generalassemb.ly/education/web-development-immersive)

# Intro to Git

Git is an essential tool that you will likely use every day as a developer.

## Prerequisites

- Familiarity with the command line and terminal

## Lesson Objectives

Knowledge:

1. Describe what Git is and what it does
1. Explain the difference between Git and GitHub

Skills:

1. Create a repository (repo) in GitHub
1. Clone that repo
1. Stage Files
1. Commit Files
1. Push files
1. Fork a repo
1. Create a branch
1. Push a branch to the repo
1. Create a pull request to original repo

## Version Control

Git is a version control system (VCS). Version control is a way of tracking _changes_ made to a file or group of files over time. If you've worked with track changes in Microsoft Word or Google Docs, or if you've ever saved multiple copies of a file while editing it, then you've used a form of version control.  

![Versioning illustrated by showing several files in the Finder window with slightly different file names](https://media.git.generalassemb.ly/user/17300/files/87b3d000-5fc0-11eb-8f14-36d557ad2fd3)

As a developer, tracking code changes provides us with the ability to examine the revision history for our code and revert to previous versions of a project when needed.  Mainly, these features give us the freedom and confidence to experiment!  With Git, we can easily try out ideas in a sandboxed version of our project, which can be merged into the base code when we get it working, or abandonned entirely if it doesn't work.  It also allows us to restore an older version of our code even after merging changes into our base project!

## Source Code Management

More broadly, there are ***source code management*** (SCM) systems. SCM systems are vital tools for collaborating with others by centralizing where we store our source code. It also allows us to isolate our work until it is ready to be integrated, and quickly troubleshoot issues by identifying who contributed specific changes to the source code. Git fits into this broader category of SCM by providing us with the tools and commands to manage our portion of a larger project, while GitHub is used as the service that centralizes where team members collaborate and store the project's source code.

>  ![Diagram depicting a local repository on a computer and a remote repository on GitHub](https://media.git.generalassemb.ly/user/17300/files/b8930580-5fbe-11eb-824c-d203ca513629)
>
> Git allows you to share a directory of files on your computer, known as the _local repository_, with another Internet-connected computer which is acting as a central location for your code (such as on a Github.com server), known as the _remote repository_. Storing your files in a remote repository has two major advantages, namely it acts as a back up, and enables collaboration with others.

Both version control and SCM systems are sometimes referred to simply as ***source control***.  Source control encompasses any system that gives us the ability to track and manage our most valuable asset as a developer: the code we write.  


### Summary

- **Git** refers to the version control system.
- **GitHub** refers to [github.com](https://www.github.com), the cloud service that hosts code repositories. It's the largest software development platform on the Internet and was acquired by Microsoft in 2018. Public repositories are viewable by all users.
- **GitHub Enterprise** is a version of GitHub for privately-held code repositories by enterprise organizations. General Assembly has its own GHE platform at [git.generalassemb.ly](https://git.generalassemb.ly).

In this course, we will use Git as our version control tool. Most coursework including lessons and homework will take place on GHE, but you will host your project repos on your personal GitHub account. In the second half of the course, we will move more assignments to GitHub so that you can start building out your GitHub presence.

## Create a repository in github

1. Go to https://git.generalassemb.ly
1. On the right click the green button that says "New Repository"
1. Give the repo a name and click Create

## Clone that repository

1. Once you've created the repo, you'll be taken to repo page
1. In the "Quick setup" section, copy and paste **the SSH** url
1. Go to a suitable location in the terminal (let's do `~/sei/unit1/`) and type `git clone ` and paste the ssh url (e.g.`git clone git@git.generalassemb.ly:yourusername/asdfasdf.git`)

> Note: If you start a repository locally (on your machine) instead of on GitHub, you can use `git init` too initialize a new repository that is being tracked by Git.

## Stage Files

`cd` into the repo and use `ls -a` to check for a `.git` repo

Now create `specific_file.txt` and make some changes to it.

Once you've finished making changes for the moment, it's time to tell git which files need to have their changes logged

- `git add specific_file.txt` will log all changes to the file specific_file.text
- `git add .` will log the changes to all files in the current working directory
- `git add some_dir/` will log the changes to all files in the some_dir directory
- `git add -A` will add all files in the local repo that have been modified

To see the status of which files are in the process of being committed use `git status`.

## Commit Files

Log the files, and give the log a description (or "message") so you can easily remember what was done

- `git commit -m "Change the database structure to allow for an email address for each user"`
- if you leave out the `-m` option, your default code editor will open with a file into which you can write a more detailed commit message
- check your commits with `git log`

## Push files

Push your changes to the remote repository

- `git push origin main` (Github)
- `git push origin master` (Github Enterprise)
- origin is the nickname of the remote repo. Main is the name of the branch (covered later) -- this is usually main when you start out.

## Review: What did we just do

Saving our work in Git requires two steps: Adding changes to the **staging area** (`git add .`) and then **committing** (`git commit -m "Describe what you did in the commit"`) those changes.

The **staging area** is one of Git's more unique features, and it can take some time to wrap your head around it. It helps to think of the **staging area** as a buffer between the working directory and the project history.

> [Why stage files?](http://gitolite.com/uses-of-index.html)

Instead of automatically committing all of the changes you've made since the last commit, the **staging area** lets you group _related changes_ into highly focused snapshots before actually committing to the project history. This means you can make all sorts of edits to unrelated files, then go back and split them up into logical commits by adding related changes to the stage and commit them piece-by-piece.

## Pull changes from remote repo

Pull any changes others made to the repo into your local version of the repo

- `git pull origin main`

> We won't need this command

## Fork a repository

Open source software is popular because the source code for an open source application is available for viewing on the internet. If you want to play around with the code of an open source app on github, you can simply fork the repo and make changes to it there.

1. Find the repo for this lesson.
1. In the upper right, click the `fork` button.
1. Choose which user (or organization if you belong to any) should create the duplicated repo.
1. Clone, make changes, add, commit, and push as normal.

## Create a branch

- When working on a specific feature, it's generally a good idea to create a "branch"
- Branches give us the freedom to experiment safely!  When you create a new branch all of the code that is in the current branch becomes the basis of the new branch.  
  - In general, the `main` branch is for finished features
  - If you are working on a feature, it's not complete, but you want to save those changes to the repo (perhaps it's the end of the day), you can use branches to keep your changes off the `main` branch
- To list all branches run `git branch`
- To checkout a new branch run `git checkout -b newbranch`
From now on, until you change branches again, all commits will be created on that branch

## Push a branch to the repo

- `git push origin newbranch` will push the currently active branch to the remote on a branch called "newbranch"
- In general, you should push a local branch to a branch on the remote repo with the same name

## Create a pull request to original repository

If you have made a change to your fork that you want to be integrated into the original repo, you'll have to ask the original repo owner to review and merge your changes into theirs.

1. Go to the original repo
1. Click the tab marked `Pull requests`
1. Click "New pull request"
1. Underneath "Compare changes" click "compare across forks"
1. For the "head fork" choose your fork. Leave "base fork" as the original repo
1. Next to the "base fork" and "head fork" buttons are drop downs for which branch of your fork (compare) should be merged into which original repo branch (base).
1. Click "Create pull request"
---

# Github Collaboration Workflow

The goal for this activity is to practice Github collaboration with branching using the [Shared repository model](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/getting-started/about-collaborative-development-models#shared-repository-model). We'll be creating separate branches to do our work and then merging out work back in to the `main` branch. 

Within groups, choose one team member to be the git owner, or "Team Member A", and the others will be "Team Members B".

## Set Up
1. Have Team Member A share their screen and create a brand new repo in Github.
    - Make it public
    - Do not add a readme or any files on initialization

1. Team Member A can then add **Collaborators** to the repo.
    - Settings tab > Collaborators > Manage access > Add people
    - Search for your partner by their Github username
    - Add your partners as "Collaborators"
    - Team Members B can then check their email and accept the invitation

1. Have Team Member A create the project boilerplate.
    - Team Member A clones down the empty repo to their local machine.
    - Team Member A creates an HTML file and adds some basic code.
    - Team Member A adds and commits their work.
    - `git push origin main`

1. Have Team Members B clone down the project.

## Workflow for Adding a Feature

Pick one team member to share their screen while going through the following steps to add a feature.

- Verify you are on the main branch
    - `git branch`

- If you are not on the main branch
    - `git checkout main`

- Pull down any changes from github to the main branch
    - `git pull origin main`  

- Create a new working branch of off the main branch
    - `git checkout -b <branch name>` (replace `<branch name>` with what you'd like to name your branch)

- Make edits.

- Git add, Commit.

- checkout **main** and verify the **main** branch is up to date.
    - `git checkout main`
    - `git pull origin main`

- **IF THERE ARE UPDATES** to **main** merge updates to your working branch.
    - `git checkout <branch name>` (i.e. your working branch)
    - `git merge main`
    - `git push origin <branch name>`

- **IF THERE ARE NO UPDATES** to **main**, checkout your working branch and push to origin.
    - `git checkout <branch name>`
    - `git push origin <branch name>`

- Go to public repo on github and create a new pull request from **Your Branch** to **main**.

- Ask a team member to verify the work in your pull request looks good.

- **If all team mates agree** and **there are no conflicts**, Team Member B merge the pull request.

- Make sure everyone knows there are new changes available to be pulled down.

- **EVERYONE** (including team member making the changes) save edits to their working branch and and update all local branches.

    - `git add -A && git commit -m "message"` in working branch.

    - `git checkout main`

    - `git pull origin main` (resolve conflicts if any)

    - `git checkout <branch name>` (your working branch)

    - `git merge main`

Repeat [Workflow for Adding a Feature](#workflow-for-adding-a-feature) now with the other team member adding a feature. Continue alternating [Workflow for Adding a Feature](#workflow-for-adding-a-feature) with one team member adding a feature and then the other team member adding a feature.

--- 

### Github 101 

# Github 101

Congrats on completing your first day of SEI! Let's do a little review quiz and while we're at it, get a little practice using Github!

> **Reminder**: Github is your friend, not your enemy!

## Relevant XKCD

![](http://res.cloudinary.com/briezh/image/upload/v1531164700/git_XKCD_y1vvzk.png)

## Review: Git and Github

Remember, *git* and *github* are two different things! Git is a version control system for managing your source code. Github is a platform to host your code online so others can access it and collaborate with you on it. You can think of Github as social media for Git! For a more detailed explanation, [watch this video](https://www.youtube.com/watch?v=uUuTYDg9XoI)!

### Tracking files: What is a .gitignore file?

You may or may not have encountered a file called `.gitignore`. If you haven't, that's fine - you will soon enough! This file tells git *not* to track certain files. Here are a few reasons we might want to do this:

1. Sometimes we have private data (e.g., API keys) in `.env` files that doesn't belong on the internet
1. Sometimes we have files / folders that are huge and it can save us a lot of time to just not include them
  * Once we get to unit 2, we'll always want to exclude the gigantic `node_modules` folder! 
1. Including these files and folders may complicate or mess up your deployments
  * Don't complicate your life 🙂

We won't need to create or use these files ourselves until unit 2, so don't sweat it if you're not yet a git master! For now, we just wanted to let you know what that file was that you may have stumbled across.

> Note: If you're already familiar with Git, you can dig further into [how and why we use gitignore files in Git's docs](https://git-scm.com/docs/gitignore) or you can generate an exhastive list of files and folders you may want to ignore at [http://gitignore.io/](http://gitignore.io/).

### Commit Messages: Best Practices

You can find a [complete list of best practices here](https://gist.github.com/robertpainsi/b632364184e70900af4ab688decf6f53), but in general, your commit message should clearly state what content/features/changes are being added to the code base and be in a complete sentence. Another best practice is to make many commits! Everytime you add something meaningful, even something really small, is a good time for a commit! This way if your code gets all messed up, you can pinpoint the exact change that caused the issue, and you won't lose much working code. Otherwise, if your commits are few and far between and you have to go back to an earlier version, you might end up losing more than you need to!

![](http://res.cloudinary.com/briezh/image/upload/v1531165696/git_commitMessages_rsqm3r.png)

## Directions

#### 1. Fork it!

On the upper righthand corner of this page, you will see a button that says `Fork`. Press that button!!! This will fork it to your personal Github account. This means that a complete copy of all the code and all the commits will be added to your Github account. Remember - a fork is a *copy* which now exists separately than the original repository that you forked from!

> **Note**: If you have access to multiple accounts or organizations on Github, you may get a pop-up asking you which one you want to use. 

#### 2. Clone it!

Once you have a "fork" of the repository on your own account, you want to clone the code onto your local machine. This means that all of the code in your Github repository (and all of the commits) will be copied onto your computer. Do this by copying the clone link. This is a green button to the right of the page. Clicking the copy icon will automatically copy it to your clipboard, or you can highlight the text and press `Cmd + C`.

![](http://res.cloudinary.com/briezh/image/upload/v1531169741/Screen_Shot_2018-07-09_at_1.55.16_PM_kb0fuq.png)

> **Protip**: If you made SSH keys in class, you should use the SSH link. Otherwise, you can use the HTTPS link. 

Once you have this link copied, go to your terminal and run the command 

```bash
git clone THE_LINK_YOU_COPIED
``` 

You may or may not be prompted for a password before the clone can take place.

> **Warning**: Make sure the location you clone at is not inside of another git repository!

In general, when coding, we don't repeat ourselves, but let's say it again. A git repository should NOT live inside another git repository!

Did you read the sentence previous to this one? Read it again! Say it out loud! Tell the person next to you! 😊

> **Note**: In future assignments, steps 1 and 2 will be referred to as a single unit. You might see a direction like "fork and clone this repository".

#### 3. Navigate to the directory

Wherever you cloned this repository should have made a new folder with the name of the folder being the same as the repository. So, in this case you should have a folder called "github_101". Navigate to this directory.

```bash
cd github_101
```

#### 4. Open it in your text editor of choice

Usually this is Sublime Text, Atom, or VS Code, but feel free to get wild and go with whatever you're most productive with. In class, you most likely set up shortcuts to these text editors. Select the one that's appropriate for what you'll be using throughout the course.

```bash
code .
``` 

#### 5. Answer the [Quiz Questions](#quiz-questions) Below

Test your Googling skills and learn something new about Git! Put your answers into the file called `answers.txt`. The file is already provided for you, just fill in your own answers. Please number them!

#### 6. Save and close

Save the answers.txt file when you're done. Close the text editor.

#### 7. Check yourself

Run the following command. 

```bash
git status
```

If you followed the directions up till now, this should tell you that there are "untracked" changes to `answers.txt`.

#### 8. Stage the changes

You can add files to be staged for (ready to go into) the next commit. The following command on your terminal will stage "all" changes in your current folder. The reason we stage files for commits is that we don't necessarily have to check in the changes to all the files, we could potentially just want to check in some of them. Hence what seems to be an extra step. In this case however, there's only one file anyway!

```bash
git add .
```

> **Protip**: The `git init` command is only necessary when you're starting a repository from scratch! Since we used the `git clone` command, we already have an initialized repository. 

#### 9. Commit to it!

The following command will add all staged changes (additions, deletions, or modifications) from the last command and put it into a commit. In our case, `answers.txt` should be modified.

```bash
git commit -m "Add my answers to answers.txt"
```

> **Note**: The `-m` in the command stands for "message". Remember our discussion of best practices for commit messages!

#### 10. Push it!

What this step does is take our commits and send them to wherever we specify. In this case, we'll push our changes on our local computer back up to your fork of this repository on your Github Enterprise account.

```bash
git push origin master
```

In this case, `origin` refers to Github — where the code originated! We can use the push command to push to Github or any another place that might host our repository. We'll also use it to deploy our sites to `Heroku` later in the course. For now, it's important to realize that the code on your Github account and the code on your machine don't match until you send your changes to Github via this push command! 

The `master` at the end of the command refers to the *branch*. Master is always the default branch, and for now, it's the only one we'll use. Later in the course we'll get into branches. 

#### 11. One Last Step!!!

Go into your internet browser and refresh the page with your forked repository. Do you see your changes on Github now?

If so, your one last step is to make a `pull request`. The term is a little bit confusing, but it means to essentially show the original repository the changes you made on your own version. It alerts the owner of the original repository and opens up the code for comments and review. 

> **Protip**: You can double check whether your pull request went through by clicking on the pull requests tab and looking for your username! See the example below (on a different repository).

![](http://res.cloudinary.com/briezh/image/upload/v1531164603/Screen_Shot_2018-07-09_at_12.28.31_PM_fzw4d6.png)

### Deliverables

By the end of this you should have:

* A separate fork of this repository (meaning, a copy on your *own* Github Enterprise account!)
* A file called `answers.txt` that has numbered answers to each of the questions listed below.
* A pull request against this repository (on SEIR-1213)

## Quiz Questions

#### 1. Who invented Git?

#### 2. What else is the person who invented Git famous for?

#### 3. What year was Git invented?

#### 4. What is the git command to initialize a new repository?

#### 5. In your own words, describe what the command `git push` is doing.

#### 6. What is the purpose of a `.gitignore` file?

#### 7. What is a fork? Why would you want to have a fork?

#### 8. What is a clone? How many clones can you have?

#### 9. Should you put a Github repository inside of another Github repository?

#### 10. You can type `git status` at any time while in a git repository - true or false?


## Additional Resources

* [Git Online Mini-Quiz](https://learn.co/lessons/git-basics-quiz)
* [Git vs Github](https://www.youtube.com/watch?v=uUuTYDg9XoI) (Explains the differences)
* [First Github Commit](https://www.youtube.com/watch?v=QqP7YZlZEOo) (This should be a review of our in-class lesson if you feel you need it!)
* [Git and Github for Poets](https://www.youtube.com/watch?v=BCQHnlnPusY) (This is a non-coder intro to using Git/Github)
* [Commit Messages Best Practices](https://gist.github.com/robertpainsi/b632364184e70900af4ab688decf6f53)



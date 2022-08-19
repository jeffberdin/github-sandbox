# git & GitHub Sandbox
** A mock website to explore version management and collaborative work*

## git

### What is git?
Git is a "snapshot manager." Git is a tool you use on your local device, and whenever you tell it to, it will save everything about your project at its current state. It keeps a record of these snapshots, and you can always go back and look at these or restore the code from that point in time. It's amazing -- if you tell git to look at a different commit (point in history), it will change all your files to look like they did at that time!
Additionally, you can create **branches**, which allow you to keep track of multiple different alternative histories things at once. More on this in the collaboration section below.

### How do I use git?
First of all, you'll need to make sure you have git installed on your computer. Run `sudo apt install git-all` from your terminal (open a terminal by pressing `CTRL` + `ALT` + `T` on Ubuntu). You also need to be set up with a GitHub account and SSH, which I believe we've all already configured (ask me if command #1 below doesn't work).
After that, it's just a bunch of commands -- but it's important to conceptually understand the goals of git and what the commands actually do, or else it's easy to get lost. You can also learn a ton about git by reading the outputs in your terminal as you run these commands, or by searching online or looking in the help manual (which you can also look up how to do online). All of these commands have ways to tweak what they do; feel free to ask for more information or if you're trying to do something beyond the simplest approach.
Before you do anything else, open a terminal and run the command `cd code/hacking`. If this fails, run `mkdir -p code/hacking` and then re-run the prior command. This moves you into a folder where you'll put this project (and creates it if it doesn't already exist).

### Base commands
1. `git clone git@github.com ...` is the first command you'll run. On any GitHub respoitory (I know this is a bit out of order, but everything is intertwined) there is a green button that says "Code." Open that, click the "SSH" option, and then copy that into the command. This will make a copy of the existing repository on your computer in the location you're currently located in, `~/code/hacking`.
**Note:** You must be in a git repository for the following commands to work. That means run `cd github-sandbox` after you've cloned the repository into `code/hacking`
2. `git status` just gives current information about your project. This can be super helpful if you're just feeling lost.
3. `git add .` followed by `git commit -m "Add information about what you changed here"` is how you add a snapshot of what you've changed.
4. `git log` or `git log --oneline` give you the a history of git commits (snapshots).
5. `git branch` shows a list of existing branches (alternative histories) and indicates the one you're currently working on. `git branch new_branch_name` creates a new branch, and `git switch new_branch_name` allows you to switch to that branch.
6. `git merge branch_name` takes the history of your current branch up to the history of `branch_name`. If there are conflicts in the files, it will try to walk you through making the changes necessary in order to complete the merge -- read the output carefully!
7. `git push origin branch_name` sends the files and commit history of `branch_name` and sends it to GitHub (more on this below!)

## GitHub

### What is GitHub?
GitHub is an online cloud-based tool that just keeps track of git projects, plus adds some shiny features on top.

### Any unique tools that are super common?
The most important aspect of GitHub for the sake of this project is a feature called **pull requests**. Pull requests are just a fancy version of a `git merge` (see above). Once you push a branch, create a pull request using the GitHub interface and add Grant as the reviewer. We'll work through the merge process together.
This description you're reading is created with the file named README.md -- GitHub knows to display this particular file on this particular screen (note: it has to be in the main folder, known as the "top-level directory"). It uses a lightweight formatting system called markdown, which you can see if you open this file. There are loads of cheatsheets online to help you take advantage of the features of markdown.

## Workflow

### What is a workflow?
There are a handful of different approaches, but a workflow is just a way of staying organized as multiple people collaborate on building a project.

### What workflow approach are we using?
We are using what's called the feature branch approach. Simply put, **any time** you make any changes, you make them on a branch other than main. Then you push that branch to GitHub and make a pull request (more info on these above). The most important part of using this approach is that you start your work from a fresh version of the project and keep others up to date on your changes -- so every time you sit down to work, make sure you *start* by running `git clone git@github.com ...` and *end* by running `git push origin branch_name`.

## Sandbox project

### What is the goal of this project?
Mostly, to learn git and GitHub. Of secondary importance, we'll be building a simple website together.

### How will this project be managed?
See info on pull requests (PRs) above, but in sum Grant will manage code merges and project tasks via [this unit in PM5](https://appcove.com/pm5/unit/10029620).

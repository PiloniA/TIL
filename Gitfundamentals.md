# Git Overview

[image1]

(Git staging)
When you change something in working directory, they are still local. When you add those changes (or a subset of it) to git, they are "staged". Then you can commit these chagnes. (still local).
"Push" to save the changes remote.

# Git Commands
## initial commands
|command|description|
|-|-|
git init | Initializes a new Git repo
git clone \<url> | Gets an existing repo from a server
git config \<level> \<value> | Sets the specified value on the chosen level (setup certain things, user, mail addres, so that main info are reflected in git; can be on different levels (repo, global,...))

## Basic commands:
|command|description|
|-|-|
git add \<file> | Add files to index (file or folder)
git commit -m \<message> | Record changes to the repo
get branch | List and manipulate branches
git checkout \<branch> | Switch between branches. You can also us it as reset. If you have changes on working dir. Make checkout and override your changes, so have a clean branch again
git tag \<tagname> | add tags to commits (you can mark a specific point in time in your repo/branch. e.g. at this point in time on this branch is my release. You can automate promotions on pipeline, you can set up a CI/CD pipeline. Git tags are essential for automated deploymets/deliveries)

## Remote commands
|command|description|
|-|-|
git push | write local changes to remote repo
git pull | Write remote changes to local repo
git fetch | Check for remote changes

## Working directory commands
|command|description|
|-|-|
git status | Shows the staging status
git reset | Reset current branch to specific point in history (You can rewrite history). Mixed reset: uncommit and unstage changes, but not resetting the working directory (flag "soft" removes changes but leaves them in staged). Can be very helpful if you did a lot of changes and you dont want those changes (something was wrong, bugfix,...). You can also make a git checkout to clean up working area.
git reflog | Shows the reference log
git diff | Shows the changes made to the working directory
git stash | Cache local changes for later use. It creates local "Mini-branch" with your changes und you can apply these changes again to your local directory. That enables you to  "cache" changes in a private way
git log | Shows the history for the current branch

## Collaboration Commands
|command|description|
|-|-|
git merge | Merges branch from common base into current branch
git rebase | Sets base of current branch to new base. "This commmit is your new base". Tree strucutre is very clean, but Problem: history gets rewritten
git cherry-pcik | Applying individual commits from another branch
git xxx \<squash> | Combines multiple commits into a single commit

# Tips & Tricks

(you should never squash on main branch)

## .gitignore
allows you to hide files, directories from version controll
"!" = "do not ignore"
eg. !results/* does not ignore the results folder, but everything in it
[image 2]

## Semantic commit messages & conventional commits
[image 3]
commit mesages are human and machine readable and allow for superior automated processing
top left code block:
\<subject> = short message
source: https://www.conventionalcommits.org/en/v1.0.0/

## configuration
git config --global user.name "Alexander Piloni"
git config -- global user.email "piloni@live.at" 

## git lfs
Enhances the possibility to store lage files
git lfs track "*.pdf"
git add .gitattributes
git add file.pdf
git lfs migrate (to also track older files)
git changes how large files are handled. It changes what is written in files


# Tools & Resources
images 4-6
Links:
Official Documentary: https//git-scm.com/docs
Git Explorer: https://gitexplorer.com/
Cheatsheet: https://about.gitlab.com/images/press/git-cheat-sheet.pdf (Gitlab)
Ohmygit: https://ohmygit.org/
Tips and tricks:
    https://ohshitgit.com/


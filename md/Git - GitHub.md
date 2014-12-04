# Git / GitHub

nice git client for Mac OS (free)

[](http://www.sourcetreeapp.com/)http://www.sourcetreeapp.com/

Optionally show hidden files, to make editing the .gitignore file:

/*

$ defaults write com.apple.finder AppleShowAllFiles -boolean true

$ killall Finder

*/

source tree:

1.  (edit some files)
2.  [add]
3.  [commit]
4.  [push]

commands

[](http://git-scm.com/docs)http://git-scm.com/docs

A successful Git branching model:

[](http://nvie.com/posts/a-successful-git-branching-model/)http://nvie.com/posts/a-successful-git-branching-model/

.gitignore example

*   [](https://gist.github.com/motoishmz/5236307/raw/be863c52bc5c3ad8c88d94952118c3578919ead9/.gitignore)https://gist.github.com/motoishmz/5236307/raw/be863c52bc5c3ad8c88d94952118c3578919ead9/.gitignore
*   [](https://gist.github.com/ofZach/3707086)https://gist.github.com/ofZach/3707086   (this is useful for OF developement)

**Process for making a change to a file in SourceTree:**

*   Make a change to a file
*   "Add" the file to the queue
*   "Commit" all of the files you added, and write some comments
*   "Push" all of the commits to Github

**useful resources**

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_W9GmyQIqTZo_p.77282_1380754442277_git.png)

*   [](http://golancourses.net/2013/resources/tools/git-and-github/)http://golancourses.net/2013/resources/tools/git-and-github/
*   my cheat sheet for command line: [](http://piratepad.net/gitCheatSheet))http://piratepad.net/gitCheatSheet)

**Git terminal commands (common workflow)**

Cloning a repository from github:

*   git clone _url_from_github_

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_W9GmyQIqTZo_p.77434_1380758257986_undefined)

_(take care about always cloning from the https url, I have found things can get funky if you don't use https as the source URL w/ github repos, especially if you go to push changes back.  luckily it's the default now... they used ssh before.  Mini and I fixed a problem she had where she had not used the https url so authentication to push changes back was hard.  After switching the source to https it was fine.)_

Get some useful info about what you've changed.

*   git status

Add files you've changed to staging

*   git add _files_

Commit files in staging (add a useful message!)

*   git commit -m '_commit message_'

Alternatively, "git add" all modified files and commit them in one go

*   git commit -am '_commit message_'

See history of commits to this repository, with time, author, commit messages

*   git log

See uncommitted file changes 

*   git diff

Send your changes to Github

*   git push

Download changes from Github (and merge them)

*   git pull

Create a new branch

*   git checkout -b _YourNewBranchName_

Pushing git to the new branch

*   git push origin _YourNewBranchName_

Switching back to master

*   git checkout master
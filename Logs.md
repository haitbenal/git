# Setting Up Git
### setup the username and email
`git config --global user.name "<your_name>"`

`git config --global user.email "<your_email>"`

# Git commits to commit
### Initialize the git repository
`git init`
### change the branch name from default Master to main
`git branch -m master main`
### Displays the files that have differences between index and file
`git status`
### Stage the changed file and commit the changes
`git add <filename> or .`

`git commit -m "<Message>"`

# History
### Show the history of the working directory
`git log`
### Show One-Line History for a condensed view showing only commit hashes and messages
`git log --oneline`
###  customize the log output by specifying the number of entries
`git log -n <Number>`
###  customize the log output by specifying the time range
`git log --since="commits made within the last 5 minutes"`
###  Show logs in a personalized format
`git log --pretty=format:"* %h %ad | %s [%an]" --date=short`

# Check it out
### Restore First Snapshot
`git checkout <commit-hash> -- <filename>`

`git checkout <commit-hash> <filename>`
### Restore Second Recent Snapshot
`git log --all`

`git checkout <commit-hash> <filename>`
### Return to Latest Version
`git checkout HEAD <filename>`

# TAG me
### Referencing Current Version
`git tag v1`
### Tagging Previous Version
`git tag v1-beta HEAD~1`
### Navigating Tagged Versions
`git checkout v1`

`git checkout v1-beta`
### Listing Tags
`git tag`

# Changed your mind?
### Reverting Changes
`git restore <filename>`
### Staging and Cleaning
`git restore --staged <filename>`

`git restore <filename>`
### Committing and Reverting
`git add <filename>`

`git commit -m  <Message>`

`git revert HEAD~1`
### Tagging and Removing Commits
`git tag oops`

`git checkout v1`
### Displaying Logs with Deleted Commits
`git log --all`
### Cleaning Unreferenced Commits
`git tag -d <any tag exist>`

`git gc --prune=now --aggressive`
### Author Information
`git add .`

`git commit -m "add author data"`
### Oops the author email was forgotten
`git add .`

`git commit -amend --no-edit or --edit `

# Move it
### Moving hello.sh
`git mv ./lib`

`git add .`

`git commit -m "moving heelo to /lib"`

`git mv ./lib`

`touch Makefile`

# blobs, trees and commits
### Exploring .git/ Directory
`cd ./git`
### Latest Object Hash
`git rev-parse HEAD && git cat-file -t HEAD && git cat-file -p HEAD`
### Dumping Directory Tree
`git ls-tree <hash> or HEAD`
`git ls-tree <hash> or <HAED>:<folderName>/`

# Branching
### Create and Switch to New Branch
`git checkout -b <Branch_name>`
### Switch && Difference
`git switch main`

`git diff main greet > README.md`
### commit tree diagram 
`git log --graph --decorate`

# Conflicts, merging and rebasing
### Merge Main into Greet Branch
`git switch greet`
`git merge main`
### Merging Main into Greet Branch (Conflict)
`git switch greet`
`git merge main`
"we will fix using graphical merge tools"
### Rebasing Greet Branch
`git reset --hard <hash>`
`git rebase main`
### Merging Greet into Main
`git switch main`
`git merge greet`

# Local and remote repositories
###  make a clone of the repository
`git clone ./hello cloned_hello`
### Show the logs for the cloned repository
`git log --all`
### Display the name of the remote repository
`git remote -v`
`git remote show origin`
### fetch the changes from the remote repository 
`git pull`
### Merge the changes from the remote main 
`git merge origin/main`
### local branch named greet track greet branch
`git checkout --track origin/greet`
### Add a remote to your Git repository
`git remote add <name_of_remote> <url_or_path>`

# Bare repositories
### Create a bare repository named hello.git
`git clone --bare hello hello.git`
### Add the bare hello.git repository as a remote
`git remote add bare ../hello.git`

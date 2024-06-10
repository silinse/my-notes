# git stuff

## links to read
https://cli.github.com/ GitHub CLI  
https://docs.github.com/en/repositories/creating-and-managing-repositories/creating-a-new-repository Creating a new repository on GitHub  
https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/about-pull-requests pull requests

## install GitHub CLI
https://github.com/cli/cli#installation  
`curl -sS https://webi.sh/gh | sh` with Webi https://webinstall.dev/gh/


## random commands

### git config
`git config --get user.name` set user name  
`git config --get user.email` set user email  
`git config --global init.defaultBranch main` init main branch  

#### git clone

`git init` create new repo in current directory

`git branch` check current branch  
`git branch -m oldname newname` rename branch

`git status` get change status

`git log` commit history  
`git log --decorate=full` full ref names  
`git log --oneline` log in one line  
`git log --decorate=full --oneline`  
`git log --oneline -n 1` -n 1: how many commits to display  
`git log --oneline --decorate --graph --parents` display commit history

`git add file_name` stage file to current branch  
`git commit -m "commit message"` commit changes to branch  
`git commit --amend -m "F: Merge branch 'add_classics'"` update merge message

### merge
`git merge my_branch` should be on main branch, to merge changes from my_branch to main

### pull
`git pull origin main` to pull in the most recent changes from remote (origin) branch   
(If you get a "divergent branches" error, run git config pull.rebase false to make sure git will merge on a pull, then try again.)


### git push
`git push origin main` push our local main branch's commits to the remote origin's main branch
`git push origin <localbranch>:<remotebranch>` push a local branch to a remote with a different name
`git push origin :<remotebranch>` delete a remote branch by pushing an empty branch to it

### create new branch
`git branch my_new_branch` create new branch  
`git switch -c my_new_branch` create new branch and switch to it  
`switch` switch to branch  
`-c` create branch if it does not exist  
`git switch -c new_branch_name COMMITHASH` create new branch from COMMITHASH commit 


### delete branch
`git branch -d branch_name` delete branch

### rebase
`git rebase main` rebase current branch on main  
no merge commit with rebase  
don't rebase main branch, rebase your own branch
`git config --global pull.rebase true` configure Git to rebase by default on pull, rather than merge so history is linear

`git reset --hard` reset all changes and go back to last commit  
`git reset --hard a1b2c3d` this will reset your working directory and index to the state of that commit, and all the changes made after that commit are lost forever

`git remote add <name> <uri>` for example: `git remote add origin https://github.com/silinse/webflyx.git`

Create a new repjository on the comand line:
```
echo "# webflyx" >> README.md
git init
git add README.md
git commit -m "first commit"
git branch -M main
git remote add origin https://github.com/silinse/webflyx.git
git push -u origin main
```

Push an existing repository from the command line
```
git remote add origin https://github.com/silinse/webflyx.git
git branch -M main
git push -u origin main
```

`git log remote/branch` see log from other branchy



## solo workflow
1. Make changes to files
2. `git add .` (or `git add <files>` if I only want to add specific files)
3. `git commit -m "a message describing the changes"`
4. `git push origin main`

## team workflow
* Update my local main branch with `git pull origin main`
* Checkout a new branch for the changes I want to make with `git switch -c <branchname>`
* Make changes to files
* `git add .`
`git commit -m "a message describing the changes"`
* `git push origin <branchname>` (I push to the new branch name, not main)
* Open a pull request on GitHub to merge my changes into main
* Ask a team member to review my pull request
* Once approved, click the "Merge" button on GitHub to merge my changes into `main`
* Delete my feature branch, and repeat with a new branch for the next set of changes




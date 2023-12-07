# Git Branching Cheat Sheet

## git commands: 

Summary of common git commands, practice with branching and getting to know git

### basic 

* git init _________________________creates a default branch, establishing a new git repository

* git status_________________________displays/examines all files and compare to the files tracked by the repository

* git add ._________________________adds and updates files to the repository

* git commit________________________records a snapshot of tracked files
			--amend_________________copies and slightly changes commit
			-m " "__________________commits and allows a message to be paired with the commit	

* find .git_________________________shows files in .git (showing what files are tracked) 
	
* git log___________________________shows the log of commits, data of commit, message, user, etc.
		--oneline___________________shows commits on one line (each) shows first 7 digits of commit name

* git config________________________shows git configuration
		-l__________________________list local git configurations

* git help___________________________show synopsis of git commands

### local


* git branch________________________lists local branches
			(new commit)____________creates a new title that moves independently
		  -f (diff commit) HEAD~____moves a different title up a number relative to head 	
		  -u o.main (commit)________changes the reference of main (on remote) to the commit given

* git checkout (diff commit)________moves the head to a new branch (git swithch does the same)
			 HEAD___________________(moves the head off of title, but keeps it on the same branch)
			 (commit)^______________^ moves title to its parent (stackable)
			 (commit)~#	____________specifies the number of parents to move up.
			 -b (commit) o/main_____changes the reference of main (on remote) to the commit given

* git merge (different commit)______combines two branches into one (leaves the the title if not an ancestor)

* git rebase (different commit)_____copy a set of commits and puts them somewhere else
		   -i <com1>~#______________copy a set of commits from head up to given point and rearrange them under highest point

* git reset (same commit)~#_________moves a branch backwards to older commit						
-
* git revert (same commit)__________copies current git, but reverses changes to revert to previous

* git cherry-pick <com1> <com2>...____copies multiple lines underneath current as long as not a part of current branch

* git tag (name) <commit>___________puts a label on a commit for future reference

* git describe <ref>________________shows where you are compared to the nearest tag

### remote

* git remote add origin (URL)_______set 'origin' as alias for remote repo 'URL'

* git push origin (commit) _________push local commits to origin repo on branch

* git clone_________________________clones your repository elsewhere (like the internet)

* git fetch_________________________downloads commits from remote branch to local repository, moves o/main

* git pull__________________________downloads commits from remote branch and merges it with local repository
		--rebase____________________pulls from a remote branch at rebases your branch to it.
		origin branchname___________pull remote branch 'name' into current local branch

* git push__________________________puhes local repository to the remote branch


When in vi editor: (esc) ':wq' escapes the editor


## Summary of branch workflow

1. checkout and pull main
	```bash
	git checkout main
	git pull origin main
	```
1. checkout new branch from up-to-date main
	```bash
	git checkout -b someFeature
	```
1. work, committing each completed task until feature is complete
1. pull remote main into local branch
	```bash
	git add .
	git commit -m "coplete feature"
	git pull origin main
	```

	* if auto merge succeeds, save and quit from vi editor
		```bash
		:wq
		```
	* if 'CONFLICT', fix conflicts in all files, removing merge markers and commit
		```bash
		git add .
		git commit -m "fix merge conflicts"
		```
1. push to remote branch 
	```bash
	git push origin someFeature
	```
1. on github checkout pull request and merge main	
1. checkout and pull merged main 
	```bash
	git checkout main
	git pull origin main
	```



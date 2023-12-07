# Git Branching Cheat Sheet

## git commands: 


### basic 

* git init 							creates a default branch, establishing a new git repository

* git status						displays/examines all files and compare to the files tracked by the repository

* git add .							adds and updates files to the repository

* git commit						records a snapshot of tracked files
			--amend					copies and slightly changes commit
			-m " "					commits and allows a message to be paired with the commit	

* find .git 						shows files in .git (showing what files are tracked) 
	
* git log	 						shows the log of commits, data of commit, message, user, etc.
	
### local


* git branch (new commit) 			creates a new title that moves independently
		  -f (diff commit) HEAD~ 	moves a different title up a number relative to head 	
		  -u o.main (commit)		changes the reference of main (on remote) to the commit given

* git checkout (diff commit)  		moves the head to a new branch (git swithch does the same)
			 HEAD 					(moves the head off of title, but keeps it on the same branch)
			 (commit)^  			^ moves title to its parent (stackable)
			 (commit)~#				specifies the number of parents to move up.
			 -b (commit) o/main 	changes the reference of main (on remote) to the commit given

* git merge (different commit)		combines two branches into one (leaves the the title if not an ancestor)

* git rebase (different commit)		copy a set of commits and puts them somewhere else
		   -i <com1>~#				copy a set of commits from head up to given point and rearrange them under highest point

* git reset (same commit)~#			moves a branch backwards to older commit						

* git revert (same commit)			copies current git, but reverses changes to revert to previous

* git cherry-pick <com1> <com2> ... copies multiple lines underneath current as long as not a part of current branch

* git tag (name) <commit>			puts a label on a commit for future reference

* git describe <ref>				shows where you are compared to the nearest tag

### remote

* git clone 						clones your repository elsewhere (like the internet)

* git fetch							downloads commits from remote branch to local repository, moves o/main

* git pull 							downloads commits from remote branch and merges it with local repository
		--rebase					pulls from a remote branch at rebases your branch to it.

* git push 							puhes local repository to the remote branch





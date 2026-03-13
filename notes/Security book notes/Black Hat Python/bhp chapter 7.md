[[2026-02-11]]

## setup
the git_trojan.py is running but i was having issues with the pull origin master because my remotes are wrong

The error is happening because of how you’re using `git pull`. The syntax is:
	
	git pull <remote> <branch>
	
	- `<remote>` is usually `origin` (the name of your remote repo).
	    
	- `<branch>` is usually `master` or `main`.
    

You **don’t** put the full URL in the pull command if you already added the remote.

### Steps to fix:

1. Make sure your remote is set correctly:
    

git remote -v

You should see something like:

origin  https://github.com/ArcenHallel/bhptrojan.git (fetch)
	what actually there: [https://github.com/ArcenHallel/github.io.git]

origin  https://github.com/ArcenHallel/bhptrojan.git (push)
	 what actually there: [https://github.com/ArcenHallel/github.io.git]

If it doesn’t exist, add it: (it didnt exist)

git remote add origin https://github.com/ArcenHallel/bhptrojan.git


## fixed

you need to follow the steps when working with git

make sure you have the right repo your pushing / pulling 

always
	git add .
	git commit -m " "
	git push origin master
from here you might have to set name and password if working on another machine 

but i got it working and i was able to pull the data from the repo on git !!
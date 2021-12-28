# SE-GI

===============
GIT COMMANDS
===============

GIT BASICS:
------------

1. git init <directory>: Create empty Git repo in specified directory.
	Run with no arguments to initialize the current directory as a git repository
2. git clone <repo> :lone repo located at <repo> onto local machine. Original repo can be 
	located on the local filesystem or on a remote machine via HTTP or SSH.
3. git config user.name <name> :efine author name to be used for all commits in current repo. Devs 
	commonly use --global flag to set config options for current user.
4. git add <directory>: Stage all changes in <directory> for the next commit. 
	Replace <directory> with a <file> to change a specific file.
5. git commit -m "<message>" : Commit the staged snapshot, but instead of launching 
	a text editor, use <message> as the commit message.
6. git status: List which files are staged, unstaged, and untracked.
7. git log: Display the entire commit history using the default format. 
	For customization see additional options.
8. git diff: Show unstaged changes between your index and 
	working directory.

UNDOING CHANGES:
---------------

9. git revert <commit>: Create new commit that undoes all of the changes made in 
	<commit>, then apply it to the current branch.
10. git reset <file> : Remove <file> from the staging area, but leave the working directory 
	unchanged. This unstages a file without overwriting any changes.
11. git clean -n : Shows which files would be removed from working directory.
	Use the -f flag in place of the -n flag to execute the clean

REWRITING GIT HISTORY:
------------------------

12. git commit --amend: Replace the last commit with the staged changes and last commit 
	combined. Use with nothing staged to edit the last commit’s message.
13. git rebase <base> : Rebase the current branch onto <base>. <base> can be a commit ID, 
	branch name, a tag, or a relative reference to HEAD.
14. git reflog:Show a log of changes to the local repository’s HEAD.
	Add --relative-date flag to show date info or --all to show all refs.
	
GIT CONFIG:
-------------
    
15. git config --global user.name <name> : Define the author name to be used for all commits by the current user
16. git config --global user.email <email>: Define the author email to be used for all commits by the current user.
17. git config --global alias. <alias-name> <git-command> : Create shortcut for a Git command. E.g. alias.glog “log --graph
	--oneline” will set ”git glog” equivalent to ”git log --graph --oneline.
18. git config --system core.editor <editor>: Set text editor used by commands for all users on the machine. <editor>
	arg should be the command that launches the desired editor (e.g., vi).
19. git config --global --edit : Open the global configuration file in a text editor for manual editing

GIT LOG:
----------
    
20. git log -<limit> : Limit number of commits by <limit>. E.g. ”git log -5” will limit to 5 commits.
21. git log --oneline : Condense each commit to a single line
22. git log -p: Display the full diff of each commit.
23. git log --stat : include which files were altered and the relative number of 
	lines that were added or deleted from each of them.
	Search for commits by a particular author.

24. git log --author = ”<pattern>” : Search for commits by a particular author.
25. git log <since>..<until> : Show commits that occur between <since> and <until>. Args can be a 
	commit ID, branch name, HEAD, or any other kind of revision reference.
26. git log --grep=”<pattern>”: Search for commits with a commit message that matches <pattern>

27. git log -- <file> : Only display commits that have the specified file.
28. git log --graph --decorate: --graph flag draws a text based graph of commits on left side of commit 
	msgs. --decorate adds names of branches or tags of commits shown

REWRITING GIT HISTORY:
-----------------------
    
29. git commit --amend: Replace the last commit with the staged changes and last commit 
	combined. Use with nothing staged to edit the last commit’s message
30. git rebase <base> : Rebase the current branch onto <base>. <base> can be a commit ID, 
	branch name, a tag, or a relative reference to HEAD.
31. git reflog :Show a log of changes to the local repository’s HEAD.
	Add --relative-date flag to show date info or --all to show all refs
	
GIT BRANCHES:
--------------
    
32. git branch: List all of the branches in your repo. Add a <branch> argument to 
	create a new branch with the name <branch>.
33. git checkout -b <branch> : Create and check out a new branch named <branch>.
	Drop the -b flag to checkout an existing branch.
34. git merge <branch> : Merge <branch> into the current branch

REMOTE REPOSITORIES: 
-------------------
    
35. git remote add <name> <url>: Create a new connection to a remote repo. After adding a remote, 
	you can use <name> as a shortcut for <url> in other commands.
36. git fetch <remote> <branch> : Fetches a specific <branch>, from the repo. Leave off <branch> to fetch all remote refs

37. git pull <remote> : Fetch the specified remote’s copy of current branch and 
	immediately merge it into the local copy.
38. git push <remote> <branch> : Push the branch to <remote>, along with necessary commits and 
	objects. Creates named branch in the remote repo if it doesn’t exist

GIT DIFF: 
----------
39. git diff HEAD: Show difference between working directory and last commit.
40. git diff --cached: Show difference between staged changes and last commit

GIT RESET:
-----------
41. git reset : Reset staging area to match most recent commit, but leave the working directory unchanged.
42. git reset --hard : Reset staging area and working directory to match most recent commit and 
	overwrites all changes in the working directory.
43. git reset <commit> : Move the current branch tip backward to <commit>, 
	reset the staging area to match, but leave the working directory alone.
44. git reset --hard <commit> : Same as previous, but resets both the staging area & working directory to 
	match. Deletes uncommitted changes, and all commits after <commit>.


GIT REBASE:
-----------

45. git rebase -i <base> : Interactively rebase current branch onto <base>. Launches editor to enter 
	commands for how each commit will be transferred to the new base.


GIT PULL:
----------

46. git pull --rebase <remote> : Fetch the remote’s copy of current branch and rebases it into the local copy.
	Uses git rebase instead of merge to integrate the branches.


GIT PUSH:
-----------

47. git push <remote> --force : Forces the git push even if it results in a non-fast-forward merge. Do not use 
	the --force flag unless you’re absolutely sure you know what you’re doing.
48. git push <remote> --all : Push all of your local branches to the specified remote.
49.git push <remote> --tags : Tags aren’t automatically pushed when you push a branch or use the
	--all flag. The --tags flag sends all of your local tags to the remote repo

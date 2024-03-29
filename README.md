# GIT LEARNING MODULE:

## Repository:
	__In Git, Collections and version controll files are kept in a repository.
	__The Repository also contains history of changes and any special configration.
	__In general, A repository will contain all the files and folder of specific type application or Project
 
# Three Local States related to file managed by Git:
	__Working Directory
		--> Working directory is the directory on the computer which holds all the projects and the application file
		--> File in working directory may or may not be managed by Git, However Git is aware of them.
		NOTE: In Working directory there is a hidden folder called '.git' that contains the actual Repository
		
	__Staging Area: pre-commit holding area
		--> It also known as 'Git Index'
		--> It is a holding area for queuing out the changes for next commit
		--> Since Files in Staging Area haven't been commited yet, we can move the file in and out from the Staging Area without effecting the Git Repository
			and its history of changes 
		
	__Commit: Git repository(or the commit history)
		--> It records the Git Commit history, i.e. All the changes that are finalised and are parmanentaly of Git repository. 
		
********************************************************************************

# Installation of Git:

	1. In Search Engine Type: "git-for-windows.github.io"
	2. Download the latest version of installer
	3. Open installer-->Next-->Next
	4. Provide location for storage, then Next-->Next--> Next
	5. Provide the default Editor to attach the git(if any)-->Next
	6. select 'Use Git from the Windows Command Prompt', then Next-->Next
	7. Select 'Checkout as-is, commit Unix-style line endings'(This will convert the windows line ending style to unix style, line ending: Its way how a text file in ending in different operating system)// It can be changed later-->Next-->Next
	8. Uncheck all and Next
	9. After installation, to check:
			A. Open Git Bash or cmd and Type 'git version'
			B. For exiting bash type: "exit"
********************************************************************************
# Git HUB
	__It is the popular git hosting site
	
# Create a repository and give small name this will help to delete the repository whenever we wnat from the repository settings

# after creating we have to prepare our local computer for that particular repository
	1. So open command prompt and navigate to the folder where we want to store the projects
	2. Git requires two information before starting i.e. name and Email address
	3. type : 
		->	git config --global user.name "Rohan Kumar"
		->	git config --global user.email "maxphinix@gmail.com"
		NKow to confirm we can type:
		->	git config --global --list

# Now we can copy the repository in the system, This process is known as 'Cloning'
	1. So at Git Hub site in the repository page, drop doen the clone or download button.
	2. From dropdown copy the HTTP URL(Make sure we copy HTTP url not SSH) of the repository.
	3. Now in cmd or git bash type:
		git clone <url>
	4. After colning a directory/folder will be added to the current destination with all the files. The directory as same name as the repository. We can confirm using 'dir' in cmd or 'ls' in git bash
# Now if we go inside the repository folder, and type : git status
	Example O/P-->
	On branch master			// Line 1
	Your branch is up to date with 'origin/master'.			//Line 2

	nothing to commit, working tree clean				//Line3
	
	__ Line1 states that we are in master root directory of the repository
	__ Line2 states that master is upto date as 'origin/master' which refers to the master branch of the github version of repository
		NOTE: clone command automatically setup a relationship back to the repository at github.
	__ Line3 states that working directory is clean, The working directory, where we do all the works and git monitors for the changes.
	So we use status command to check for any changes in local repository,working area.

	
# Committing at file
	__ After saving the file in the local repository. We can check content of the file by using 'cat' command in GIT BASH
	__ Now we can add this to staging area using following
		'git add <fileName>'
		Now if we check status, we will observe that there is a change detected.
	__ Now we can commit the file in the local repository. Type:
		git commit -m "A commit message"
	__ Now again on status check we can observe that working directory is clean now.
		O/P-->
		On branch master
		Your branch is ahead of 'origin/master' by 1 commit.
		(use "git push" to publish your local commits)

		nothing to commit, working tree clean
		
# Pushing the commits to the git hub
	Type: git push origin master
					^		^
					|		|__This is the name of the brach we pushed. Here 'master' refer to the default and ONLY branch in the repository.
					|
					|___This version of push command refer to the remote name that was automatically assigned by the repository
							Here 'origin' refers to the github copy of the repository
	provide your Git UserName and password

	
**************************************************************************************
# Adding git to existing project
	1. Go to the project folder to add the '.git' repository folder
		type: "git init"
	2. We can check the addition by typing "ls -al" to print all the file and folder(Even hidden folders too)
	3. Noe to add all the files in the staging area we will type:
		'git add .'				// IMPORTANT
	4.Then Commit : 'git commit -m "My first Commit"'

# Pushing An existing repository
	1. First create an empty repository at gitHub.(It would be better you create with same name as that of project). 
	   Avoid initializing the repository with readme and all, iyt can be added later.
	2. Copy the http url of the repository.
	3. Now after commit in local repository od the system. To push it Type:
		'git remote add origin <http URL>'
		'git push -u origin master'
# Git_Documentation
# Table of Contents
1. Git installation and why git? 
2. Git basic commands
3. Rebasing
4. Merge Conflicts
5. Stashing

# 1.Git installation and why git? 

#### Git is a widely used modern version control system for tracking changes in computer files. The term version control system suggests a system that records all the changes made to a file or set of data, so a specific version can be considered whenever needed. This feature makes the process of collaboration so feasible with all team members, making it considerably more comfortable to work over a big project.

# Git Installation
        There are several ways to install Git on a Mac. In fact, if you've installed XCode (or it's Command Line Tools), Git may already be installed. To find out, open a terminal and enter git --version. 

                1. $ git --version 
                git version 2.32.0 (Apple Git-132)

### Git for Mac Installer 


        The easiest way to install Git on a Mac is via the stand-alone installer: 
        1. Download the latest Git for Mac installer.
        2. Follow the prompts to install Git.
        3. Open a terminal and verify the installation was successful by typing  git --version:
                $ git --version

        4. Configure your Git username and email using the following commands.These details will be associated with any commits that you create:
                $ git config --global user.name "UserName"
                $ git config --global user.email "UserEmail"


### Install Git with Homebrew

        If you have installed Homebrew to manage packages on OS X, you can follow these instructions to install Git: 
        1.Open your terminal and install Git using Homebrew:
                $ brew install git
        2.Verify the installation was successful by typing which git --version:
                $ git --version
        3.Configure your Git username and email using the following commands. These details will be associated with any commits that you create:
                $ git config --global user.name "UserName"
                $ git config --global user.email "UserEmail"

### Install Git with MacPorts

        If you have installed MacPorts to manage packages on OS X, you can follow these instructions to install Git:

        1.Open your terminal and update MacPorts:
                $ sudo port selfupdate
        2.Search for the latest available Git ports and variants:
                $ port search git 
                $ port variants git
        3.Install Git with bash completion, the OS X keychain helper, and the docs:

                $ sudo port install git +bash_completion+credential_osxkeychain+doc

        4.Configure your Git username and email using the following commands. These details will be associated with any commits that you create:
                $ git config --global user.name "UserName"
                $ git config --global user.email "UserEmail"


# 2.Git basic commands

        1. $ git init
                The command git init is used to create an empty Git repository.
                
                After the git init command is used, a .git folder is created in the directory with some subdirectories.


        2. $ git add <filename> or git add .
                Add command is used after checking the status of the files, to add those files to the staging area.

        3. $ git commit
                The commit command makes sure that the changes are saved to the local repository.
                
                The command ( git commit -m “commit message” ) allows you to describe everyone and help them understand what has happened.

        4. $ git status
                The git status command tells the current state of the repository.

        5. $ git log
                The git log command shows the order of the commit history for a repository.

                The command helps in understanding the state of the current branch by showing the commits that lead to this state.

        6. $ git config
                The git config command is used initially to configure the user.name and user.email. This specifies what email id and username will be used from a local repository.
                
                When git config is used with --global flag, it writes the settings to all repositories on the computer.
                                git config --global user.name “any user name”
                                git config --global user.email "email id"        

        7. $ git branch
                The git branch command is used to determine what branch the local repository is on.
                The command enables adding and deleting a branch.

                # Create a new branch
                        git branch <branch_name>

                # List all remote or local branches
                        git branch -a

                # Delete a branch
                        git branch -d <branch_name>

        8. $ git checkout
                The git checkout command is used to switch branches, whenever the work is to be started on a different branch.
                The command works on three separate entities: files, commits, and branches.

                # Checkout an existing branch
                        git checkout <branch_name>                

                # Checkout and create a new branch with that name
                        git checkout -b <new_branch>


# Git Commands: Working With Remote Repositories

        9. $ git remote
                The git remote command is used to create, view, and delete connections to other repositories

                git remote add origin <address>

        10. $ git clone
                The git clone command is used to create a local working copy of an existing remote repository.

                git clone <remote_URL>

        11. $ git pull 
                The "git pull "command is used to fetch and merge changes from the remote repository to the local repository.

                The command "git pull origin master" copies all the files from the master branch of the remote repository to the local repository.

                        git pull <branch_name> <remote URL>

        12. git push
                The command git push is used to transfer the commits or pushing the content from the local repository to the remote repository.
                
                The command is used after a local repository has been modified, and the modifications are to be shared with the remote team members.

                        git push -u origin master


# 3. Rebasing
    
#### rebasing is changing the base of your branch from one commit to another making it appear as if you'd created your branch from a different commit
     $ git rebase < base branch name>            :
               This command is used to rebase your feature-branch with base-branch
     $ git rebase --onto main featureA featureB   :
               featureA is the < oldbase >. main becomes the < newbase > and featureB is reference for what HEAD of the < newbase > will point to. 
### resolving rebase conflicts :
      1. $ git diff :  
              use git diff to locate the markers (<<<<<<) and make edits to resolve the conflict.
      2. $ git add <filename>   :
              To tell Git that the conflict has been resolved

      3. $ git rebase --continue :
               After resolving the conflict manually and updating the index with the desired resolution, you can continue the rebasing process by using this command
      4. $ git rebase --skip

               Restart the rebasing process by skipping the current patch.

      5. $ git rebase --abort   :
                Abort the rebase operation and reset HEAD to the original branch. If <branch> was provided when the rebase operation was started, then HEAD will be reset to <branch>. Otherwise HEAD will be reset to where it was when the rebase operation was started.

      6. $ git rebase --quit
               Abort the rebase operation but HEAD is not reset back to the original branch. The index and working tree are also left unchanged as a result. If a temporary stash entry was created using --autostash, it will be saved to the stash list.
               

# 4. Merge Conflicts

#### a merge conflict is an event that takes place when Git is unable to automatically resolve differences in code between two commits. Git can merge the changes automatically only if the commits are on different lines or branches.

![Merge Conflict](https://www.simplilearn.com/ice9/free_resources_article_thumb/pull-push.JPG)

### git commands to resolve conflicts

       1. $ git log --merge :
                the git log --merge command helps to produce the list of commits that are causing the conflict
       
       2. $ git diff :
                the git diff command helps to identify the differences between the states repositories or files
        
       3. $ git checkout :
                the git checkout command is used to undo the changes made to the file, or for changing branches
                
       4. $ git reset --mixed :
                the git reset --mixed command is used to undo changes to the working directory and staging area
       
       5. $ git merge --abort :
                the git merge --abort command helps in exiting the merge process and returning back to the state before the merging began
        
       6. $ git reset :
                the git reset command is used at the time of merge conflict to reset the conflicted files to their original state
                
Refrence : [resolving merge conflicts](https://www.simplilearn.com/tutorials/git-tutorial/merge-conflicts-in-git#what_is_a_git_merge_conflict)                


# 5. Stashing
#### Git Stashing is When you stash changes, the changes are temporarily removed from the files and you can choose to restore or discard the changes later

        1. $ git stash :
                you want to switch branches, but you don’t want to commit what you’ve been working on yet, so you’ll stash the changes. To push a new stash onto your stack we can use git stash push 



        2. $ git stash list :
                you can switch branches and do work elsewhere; your changes are stored on your stack. To see which stashes you’ve stored




        3. $ git stash apply :
                In this case, two stashes were saved previously, so you have access to three different stashed works. You can reapply the one you just stashed by using the command shown in the help output of the original stash command: git stash apply. If you want to apply one of the older stashes, you can specify it by naming it, like this:**git stash apply stash@{index}**. If you don’t specify a stash,  Git assumes the most recent stash and tries to apply it:
        

        4.git stash drop stash@{0} :
                The apply option only tries to apply the stashed work — you continue to have it on your stack. To remove it, you can run git stash drop with the name of the stash to remove:


        5.$ git stash apply --index :
                The changes to your files were reapplied, but the file you staged before wasn’t restaged. To do that, you must run the git stash apply command with a --index option to tell the command to try to reapply the staged changes. If you had run that instead, you’d have gotten back to your original position:
        

        6.$ git stash branch testchanges :
                If you stash some work, leave it there for a while, and continue on the branch from which you stashed the work, you may have a problem reapplying the work. If the apply tries to modify a file that you’ve since modified, you’ll get a merge conflict and will have to try to resolve it. If you want an easier way to test the stashed changes again, you can run git stash branch <new branchname>, which creates a new branch for you with your selected branch name, checks out the commit you were on when you stashed your work, reapplies your work there, and then drops the stash if it applies successfully:
        


        7.git stash --all :
                You’ll want to be pretty careful with this command, since it’s designed to remove files from your working directory that are not tracked. If you change your mind, there is often no retrieving the content of those files. A safer option is to run git stash --all to remove everything but save it in a stash.







        

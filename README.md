# Git_Documentation
# Table of Contents
1. Git basic commands
2. Rebasing
3. Merge Conflicts


# 1.Git basic commands

#### Git is a widely used modern version control system for tracking changes in computer files. The term version control system suggests a system that records all the changes made to a file or set of data, so a specific version can be considered whenever needed. This feature makes the process of collaboration so feasible with all team members, making it considerably more comfortable to work over a big project.

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


# 2. Rebasing
    
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
               

# 3. Merge Conflicts

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

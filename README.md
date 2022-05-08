# Git_Documentation
# Table of Contents
1.Rebasing
2.Merge Conflicts


# 1. Rebasing
    
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
               

# 2. Merge Conflicts

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

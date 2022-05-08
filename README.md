# Git_Documentation
# Table of Contents
1.Rebasing


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


                        

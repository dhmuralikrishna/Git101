# Git101


git branch
git add *
git commit -m "comment.."
git checkout <branchname>
git status
git log -p -1
git log --pretty=oneline
Change 4 server
Change 5 server
  
  
  
  ## REDO Commits
  
  Redo multiple commits as one commit.
  
  git reset [commit] 
  Undo all commits and have the commited changes in pending changes.
  
  git reset --hard [commit]
 Undo all commits. Non recoverable
 
 
 ## MERGE
 
 Merge hot fix back to master.
 
 git checkout master
 git merge hotfix
 
 Merge commit.Threeway merge(Has more than one parent)
 
 ### Rebase

There is no difference with merge and rebase. Rebase will make cleaner history looks like a linear history.
While merging it will be fast forward.

git checkout experiment
git rebase master
 
 

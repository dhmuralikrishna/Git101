# Git101

 <ul>
<li>git init</li>
<li>git branch</li>
<li>git add \*</li>
<li>git commit -m "comment.."</li>
<li>git checkout <branchname></li>
<li>git status</li>
<li>git log -p -1</li>
<li>git log --pretty=oneline</li>
 </ul>

## Branch

git checkout <FromBranchName-That you want to create>
git branch <newbranchname>

## REDO Commits

Redo multiple commits as one commit.

git reset [commit]
Undo all commits and have the committed changes in pending changes.

git reset --hard [commit]
Undo all commits. Non recoverable

## MERGE

Merge hot fix back to master.

 <ul>
<li>git checkout master</li>
<li>git merge hotfix</li>
 </ul>

Merge commit. Three way merge(Has more than one parent)

## Rebase

There is no difference with merge and rebase. Rebase will make cleaner history looks like a linear history.
While merging it will be fast forward.

<ul>
    <li>git checkout experiment</li>
    <li>git rebase master</li>
    <li>git rebase --continue</li>
    <li>git rebase --abort</li>
</ul>

 

 All changes made by commits in the current branch but that are not in <upstream> are saved to a temporary area

 git log <upstream>..HEAD


## Compare changes

It will give the common ancestor between two branches
 git merge-base  branchA  branchB

change 1 on master

change 2 on master
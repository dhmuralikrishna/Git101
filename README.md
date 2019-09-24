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

Merging all that changes that are done after cutting workingbranch

<ul>
    <li>git checkout workingbranch</li>
    <li>git merge master</li>
</ul>

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

## Sync with master

See where is this current branch compared with master.
git log --graph --oneline --all

It will give the common ancestor between two branches
 git merge-base  branchA  branchB

## REDO COMMITS

All the commits after this commit id are rolled back and put it in pending changes.
git reset [commit] 

Discard all commits after this commit.
git reset --hard [commit]

## Save Fragments

git stash list
git stash
git stash pop
git stash drop
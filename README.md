# Git101

 <ul>
<li>git init</li>
<li>git clone [url]</li>
<li>git branch</li>
<li>git add \*</li>
<li>git commit -m "comment.."</li>
<li>git checkout <branchname></li>
<li>git status</li>
<li>git log -p -1</li>
<li>git log --pretty=oneline</li>
<li>git log --graph --oneline --all</li>
<li>git diff branch1..branch2</li>
<li>git reset [file]</li>
<li>git pull origin [branch name]</li>
<li>git show [commitid]</li>
<li>git rev-parse master -- Last commitid</li>
 </ul>
 
## Branch

|Command                   |Description   |
|--------------------------|---|
|```git branch``` | Lists all the branches in current repository|
|```git checkout [branch-name]```|Checkout the provided branch| 
|```git checkout [from-branch-name]``` <br/> ```git branch [new-branch-name]```|Create a new branch from the current checkout branch|
|```git branch [new-branch-name] [sha1-of-commit]```|Create a new branch from the commit-id| 
|```git branch -d [deleting-branch-name]```|Delete branch </br> Make sure you are NOT checked out the branch you are deleting|
|```git checkout [from-branch-name]``` <br/> ```git branch -m [to-branch-name]``` |Rename a branch|
|||
|```git branch -r --list *search*```|Search remote branches|
|```git fetch```<br/>```git checkout -b [branch name] origin/[branch name]```|Clone a remote branch and switch to it|
|```git push origin --delete [branch name]```|Delete a remote branch|
|```git checkout -b [new branch name]```|Create a new branch and checkout <br/> By mistake you started changing in master and want to create a new branch and have to changes there |

## MERGE

Merge hot fix back to master.

Merge commit. Three way merge(Has more than one parent)

<ul>
    <li>git checkout master</li>
    <li>git merge hotfix</li>
</ul>

Merging all that changes that are done after cutting working-branch

<ul>
    <li>git checkout [working-branch]</li>
    <li>git merge master</li>
</ul>

Merge all the changes in a branch to another branch as single commit.

<ul>
    <li>git checkout [new-working-branch]</li>
    <li>git merge --squash [worked-branch that has your commits c1, c2, m1, m2, c3...]</li>
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

Lets say next is cut from master and topic is cut from next. 
And next changes are merged to master. Now we want the topic is rebase master.
git rebase --onto master next topic

 All changes made by commits in the current branch but that are not in <upstream> are saved to a temporary area

 git log <upstream>..HEAD


## REDO Commits

Redo all changes. Dont provide the commiitid 
```git reset --hard```

Redo changes on a file. Go to a directory cd directory-path
```git checkout f08a63ff4 -- filename```

git reset [commit]
Undo all commits and have the committed changes in pending changes.

git reset --hard [commit]
Undo all commits after the provided commits. Non recoverable

## Sync with master

It will give the common ancestor between two branches
 git merge-base  branchA  branchB

## REDO COMMITS

All the commits after this commit id are rolled back and put it in pending changes.
git reset [commit]

Discard all commits after this commit.
git reset --hard [commit]

## Squash commits

Merging multiple commits as one. N is the number of latest commits that needs to be merged.
git rebase -interactive  HEAD~[N]

Sqash all the commits after this commit.
git rebase --interactive [commit-hash]

## CherryPick

Checkout the branch that you want to cheery pick into. <br/>
git cherry-pick a7c3dab

## Save Fragments

git stash list<br/>
git stash<br/>
git stash pop<br/>
git stash drop

## VisualStudio  

Lets say when we stash the changes there are stage(Good code ready to make commit) and changed sections(Draft version).<br/>
We can stash and restore the changes as-is.<br/>

Apply vs Pop. <br/>
Apply will keep the stash where as pop will delete the stash after popping the changes. <br/>

[Apply and restore staged]. It Will un-shelve the same way state when it's stashed. <br/>
[Apply all and unstage]. It will un-shelve all the(stated and changed) files to changed section.

* Git has five stages, initially we will be focusing on three areas.
    1. Working Tree
    2. Staging Area
    3. Local Repository
    4. Remote Repository
    5. Stash


* Git Basic Configuration
    * This configuration is to set username and email id of the author.
    * git config --global user.name "venkannababukotha"
    * git config --global user.email "vasukotha.aws2@gmail.com"

* Some git commands and their uses.
* git add fileName -- to add the file to staging area
* git remote set-url origin https://venkannababukotha@https://github.com/venkannababukotha/Git.git -- to set the remote repository URL 
* git restore --staged <fileName> -- to bring changes from staging area to working directory

# Excercie-1
============
* Create a folder git_merge_scenario (`mkdir git_merge_scenario`)
* Go into the folder and initialize git repository (`cd git_merge_scenario`, `git init`)
* create src and tests folders. Also create main.py in src folder and test_main.py in tests folder (`mkdir src`, `mkdir tests`, `touch src/main.py`, `touch tests/test_main.py`)
* check the git status (`git status`)
* Rename the branch to main from master (`git branch -M main`)
* create a branch rel_v1.0 from main branch (`git branch rel_v1.0`)
* create a file version.txt and add to staging area(`touch license.txt`, `git add .`, `git commit -m "added license"`)
* merge the main branch with rel_v1.0 branch (`git checkout main`, `git merge rel_v1.0`)



Differences between git merge, git rebase, git merge --fastforward

References:
* https://www.atlassian.com/git/tutorials/using-branches/git-merge
* https://www.atlassian.com/git/tutorials/rewriting-history/git-rebase
* https://www.atlassian.com/git/tutorials/merging-vs-rebasing


* Merge conficts:A merge conflict occurs when Git cannot automatically combine changes from different branches. This happens when:
    * Two branches modify the same part of a file.
    * A file is deleted in one branch but modified in another.
    * There are conflicting changes in multiple commits.
* We have to manually resolve the conflicts. If you want to abort the merge use `git merge --abort`
* If you want to change the message of previous commit use `git commit --amend` command. This is only used to change the latest commit message.
* If we want to change the commit message of even before commit then we have to traverse to the commit before of that. (suppose we have to change 5th commit we have to go one step back to 5th commit i.e. 6th commit) `git cat-file -p HEAD~2` `git rebase -i HEAD~2`
* interactive rebase is used to change the commit history `git rebase -i `
we have some commands here to change the history 
* p, pick <commit> = use commit
* r, reword <commit> = use commit, but edit the commit message
* e, edit <commit> = use commit, but stop for amending
* s, squash <commit> = use commit, but meld into previous commit
* f, fixup [-C | -c] <commit> = like "squash" but keep only the previous
*                    commit's log message, unless -C is used, in which case
*                    keep only this commit's message; -c is same as -C but
*                    opens the editor
* x, exec <command> = run command (the rest of the line) using shell
* b, break = stop here (continue rebase later with 'git rebase --continue')
* d, drop <commit> = remove commit
* l, label <label> = label current HEAD with a name
* t, reset <label> = reset HEAD to a label
* m, merge [-C <commit> | -c <commit>] <label> [# <oneline>]
*         create a merge commit using the original merge commit's
*         message (or the oneline, if no original merge commit was
*         specified); use -c <commit> to reword the commit message
* u, update-ref <ref> = track a placeholder for the <ref> to be updated
*                       to this position in the new commits. The <ref> is
*                       updated at the end of the rebase

* These lines can be re-ordered; they are executed from top to bottom.
* If you remove a line here THAT COMMIT WILL BE LOST.
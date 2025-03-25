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

# Excercie-1
============
* Create a folder git_merge_scenario (mkdir git_merge_scenario)
* Go into the folder and initialize git repository (cd git_merge_scenario, git init)
* create src and tests folders. Also create main.py in src folder and test_main.py in tests folder (mkdir src, mkdir tests, touch src/main.py, touch tests/test_main.py)
* check the git status (git status)
* Rename the branch to main from master (git branch -M main)
* create a branch rel_v1.0 from main branch (git branch rel_v1.0)
* create a file version.txt and add to staging area(touch license.txt, git add ., git commit -m "added license")
* merge the main branch with rel_v1.0 branch (git checkout main, git merge rel_v1.0)



Differences between git merge, git rebase, git merge --fastforward

References:
* https://www.atlassian.com/git/tutorials/using-branches/git-merge
* https://www.atlassian.com/git/tutorials/rewriting-history/git-rebase
* https://www.atlassian.com/git/tutorials/merging-vs-rebasing
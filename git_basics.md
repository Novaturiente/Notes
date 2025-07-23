---
id: git_basics
aliases:
  - Git_basics
tags: []
---

# Git_basics


## 3 stages in git flow
  ___Working diectory___ ->  where the changes are made and work is done
  ___Staging area___ ->  Where the files that are going to be commited
  ___Git repo___ ->  After submitting the commit


## Commands

-  init
    Initialize git repo

-  status
    View status of git repo

-  add [files]
    Add files to the staging area

-  reset [files]
    Remove files from staging area
    Run without file names to remove everying added

-  commit
    Commit changes added to staging area
    git commit -m "Message"

-  log
    View the commits

-  diff
    Show changes after last commit


### Branch management
-  branch -a
    Show all branches of git repo

-  branch [name_for_brach]
    Create a brach with given name

-  chckout [name_of_branch]
    Start working on the branch with given name (move to the brach)

-  branch --merge
    Show all the branches that are already merged

-  branch merge [branch_to_merge]
    Merge the given branch to the branch from which the command is ran (move to main branch and run to merge the given branch to main)

-  brach -d [branch_to_delete]
    Delete given branch

-  push [github_repo] [branch]
    Push the updates to remote repository like github
    git push origin main
    git push -u origin [branch]  -> connect the local [branch] with remote master [branch] (only have to be ran once)


### Remote repo management
-  push [repo] --delete [branch]
    Delete the [branch] from remote repo

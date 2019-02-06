# Git

  - Git basics: `https://docs.gitlab.com/ee/gitlab-basics/README.html`
  - Readme file markdown `https://dillinger.io`


### Start using git
  - Check if Git has already been installed(it is usually preinstalled on Mac and Linux) `git --version`
  - Add Git username and set email
  ```sh
  git config --global user.name "YOUR_USERNAME"
  git config --global user.name
  git config --global user.email "your_email_address@example.com"
  git config --global user.email
  git config --global --list
  ```
  
  - Download the latest changes from github `git pull REMOTE NAME-OF-BRANCH`, usually use as `git pull origin NAME-OF-BRANCH`
  - View remote repositories: `git remote -v`
  
  - Clone repository: `git clone "REPO-URL"`



### Branch
  - Create a new branch: `git checkout -b "BRANCH-NAME"`
  - Switch to another branch: `git checkout "BRANCH-NAME"`
  - Check which branch: `git branch`
  - Push branch: `git push origin [name_of_your_new_branch]`
  - Add a new remote for your branch: `git remote add [name_of_your_remote] [name_of_your_new_branch]`
  - Push changes from your commit into your branch: `git push [name_of_your_new_remote] [url]`
  - Update your branch when the original branch from official repo has been updated: `git fetch [name_of_your_remote]`
  - Delete a branch on your local filesystem: `git branch -d [name_of_your_new_branch]`
  - Force the deletion of local branch on your filesystem: `git branch -D [name_of_your_new_branch]`
  - Delete the branch on github: `git push origin :[name_of_your_new_branch]`



### Make changes and push
  - View the changes you've made `git status`
  - View differences between local, unstaged changes and the repository versions:`git diff`
  
  - Add (to the staging area to wait to be commited) and commit local changes:
  ```sh
  git add FILE OR FOLDER
  git commit -m "COMMENT TO DESCRIBE THE INTENTION OF THE COMMIT"
  ```
  - Add and commit all changes:
  ```sh
  git add .
  git commit -m "COMMENT TO DESCRIBE THE INTENTION OF THE COMMIT"
  ```
  
  - Send changes: `git push REMOTE NAME-OF-BRANCH`
  


### Delete
  - Delete all local changes that have not been added to the staging area `git checkout .`
  - Delete all untracked changes `git clean -f`
  - Unstage all changes that have been added to the staging area (undo the most recent add, but not commited) `git reset .`
  - Undo most recent commit (but leaves the files and folders unstaged in the local) `git reset HEAD~1`
  


### Abandon
  - Abandon changes in a file to the previously-committed version:`git checkout <file>`
  

  

### Merge
  - Merge created branch with master branch:
  ```sh
  git checkout NAME-OF-BRANCH
  git merge master
  ```
  - Merge master branch with created branch:
  ```sh
  git checkout master
  git merge NAME-OF-BRANCH
  ```






## Examples:
### Copy a folder from one branch to another
```sh
$ git checkout work
Switched to branch 'work'
$ git checkout master -- utils
$ git add utils
$ git commit -m "Adding 'utils' directory from 'master' branch."
[work 9fcd968] Adding 'utils' directory from 'master' branch.
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 utils/file
 ```
 ### Delete it on master branch after that
 ```sh
 $ git checkout master
 Switched to branch 'master'
 $ git rm -r utils
 rm 'utils/file'
 $ git commit -m "Removing 'utils' directory."
 [master c786f95] Removing 'utils' directory.
 1 file changed, 0 insertions(+), 0 deletions(-)
 delete mode 100644 utils/file
 $ git push
```
### Revert to previous commit
 ```sh
 $ git reset --hard [previous Commit SHA id here]
 $ git push origin [branch Name] -f
```


References:
  ```sh
  https://docs.gitlab.com/ee/gitlab-basics/start-using-git.html
  https://dont-be-afraid-to-commit.readthedocs.io/en/latest/git/commandlinegit.html
  https://github.com/Kunena/Kunena-Forum/wiki/Create-a-new-branch-with-git-and-manage-branches
  https://avilpage.com/2014/11/git-updating-clonedforked-repository-on.html
  https://stackoverflow.com/questions/17999851/git-copy-a-folder-from-master-branch-to-another-branch
  ```

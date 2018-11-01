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



### Make changes and push
  - View the changes you've made `git status`
  - View differences between local, unstaged changes and the repository versions:`git diff`
  
  - Add and commit local changes:
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




References:
  - Git lab docs:
  ```sh
  https://docs.gitlab.com/ee/gitlab-basics/start-using-git.html
  ```

# git-cheatsheet-commands
Git commands to make you more productive

First, install git for windows or mac 
https://git-scm.com/downloads


# Setting up

Setting up username and email
```
git config --global user.name "heychessy"
git config --global user.email "email@gmail.com"
git config --global --list
```

Initialize git, in your project directory run: 

```
git init 
or 
git init <project-name>
```

To check status and untracted files 
```
git status
```

To commit changes
```
git commit -m "<some message>"
```

To add file to stating stage 
``` 
git add <filename>
or
git add .
```

To discard changes in working directory
```
git checkout -- <filename>
```

To unstage a file 
```
git reset HEAD <filename>
```

To remove a file 
```
git rm <filename>
or
rm <filename>
git add -u
git commit -m "<filename> removed"
```

To ingore some files from bieng included in git create .gitignore file and put the file/folder names and save

Creating SSH 
create folder .ssh 
inside that folder run the following command
```
ssh-keygen -t rsa -C "<youremail@id.com> 
```
enter a  passphrase, once done. copy the content of .pub file to SSH settings on github. 
Run the following to check the connection
```
ssh -T git@github.com
```


# To work on global/remote directory.

1. Create a repo on github
2. Copy the ssh or normal url from the repo 
3. Make sure there is nothing left to commit on local repo
4. Run the following command 
```
git remote add origin <paste the url here>
```

Now, check the origin 
```
git remote -v
```

To push the repo first time use the following command
```
git push -u origin master
```

Next time, just use 
```
git push origin master
```

Note: The leading practice is always to pull the remote repo first, this will merge the changes done by anyone else. Then push the repo.
So, run 
```
git pull origin master
```

Now, push to the repo
```
git push origin master
```

# Creating a new branch
Create the branch on your local machine and switch in this branch
```
 git checkout -b [name_of_your_new_branch]
 ```
 
 Change working branch 
 ```
 git checkout [name_of_your_new_branch]
 ```
 
 Push the branch on github
 
 ```
 git push origin [name_of_your_new_branch]
 ```

You can see all branches created by using 
```
git branch
```

# Merging to a local branch
Merging localbranchB on to localbranchA

```
git checkout <localbranchA>

git merge <localbranchB>
```

Merging only file changes without commit history
```
git merge --squash <localBranchB>
```


# Stashing
saving changes in stash 
```
git stash list
git stash 
```
applying changes from stash
```
git stash apply stash@{0}
```
or
```
git stash pop
```
dropping stash
```
git stash drop
```
clearing the stash
```
git stash clear
```

# Rebase vs Merge 
https://www.youtube.com/watch?v=CRlGDDprdOQ

# Cherry pick 
allows to pick a particular commit using the hash, switch to the brach in which you want to apply the commit and then 
```
git cherry-pick <hash>
```

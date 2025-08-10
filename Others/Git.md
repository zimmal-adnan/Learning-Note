# LEARNING NOTES
## Backing Up Code
- You can easily backup code online either using Google Drive or GitHub
    - To backup code on Google Drive, simply drop your folder. Google Drive will provide a 2-way sync.

## The Basic Git Commands

- You initialize an empty git with ```git init```

- Save all files with ```git add .``` (can be risky if you want some files ignored) or specific files with ```git add [filename]```
    - Here, the files are in the Staging Area to review our changes.

- If everything is good, you commit with ```git commit -m "message"``` to commit with a one-line message or ```git commit``` for longer lines.
    - For longer lines, you write a short description at the top, then a longer description below it.

> A risk move! If you want to skip the Staging Area entirely, do ```git commit -am "Message"```

- To view the status of your files (whether they are unstaged, staged or committed), write ```git status```

>Check all the files in the Staging Area with ```git ls-files```

- Remove files from both the working directory and staging area with ```git rm [filename]```
    - If you want to remove the file from the Staging Area only then use ```git rm --cached [filename]```

- To rename or move files, use ```git mv [original filename] [new filename]```

---

## Ignoring Files to Commit
- Create a special file using ```.gitignore```
- You can add all the files and folders that you don't want to be committed by using ```code .gitignore``` and placing the files [filename.js] and folders [foldername/]in there.
- Add the ```.gitignore``` to the Staging Area and commit it.

>### Accidentally Committing Unwanted Files
>- Add the file to the ```.gitignore```
>- Stage and Commit.
>- Remove the unwanted file with ```git rm --cached -r [filename]```
>- Commit the change.

## Using Visual Diff Tools to Check Staged/Unstaged Changes
- ```git difftool``` will compare what we have in the Staging Area to what we have in the working directory.
- ```git difftool --staged``` will compare the file from the last commit to the file in the Staging Area.

## Viewing Git History
- Use ```git log``` to check commit history.
    - You can use ```git log --oneline``` for a summary.
    - You can also use ```git log --oneline --reverse``` so you get the first commit at the top.
    - To check the graphical flow of the commits, use ```git log --all --graph```

## Changing the Commit Message of a Previous Commit
- Use ```git commit --amend -m [message]```

## Viewing the Contents of a Commit
- Use ```git show [unique ID of the commit]``` or ```git show HEAD``` to view the last commit or ```git show HEAD~[number of steps you want to go back]```

- To not see the differences, and just the final version, use ```git show [CommitNumber]:.[filename] or [directory]/[filename]```

- To see all the files in a commit, use ```git ls-tree [CommitNumber]```
 
## Unstaging Files from the Staging Area
- Use ```git restore --staged [filename]```
- This copies the contents of the file from the next staging environment (in this case, the commit) while keeping the changes in your working directory unchanged.

## Discarding Local Changes
- To discard any code that you don't want in your working directory, do ```git restore [filename]```
- To remove any untracked files, write ```git clean -fd```

## Restoring a File from the Previous Version 
- If you want to undo the previous commit, simply do ```git restore --source=[HEAD~1] [filename]```

## Deleting Commits from GitHub
- Use ```git reset --hard [CommitHash]```
- Then ```git push origin [branchname] --force```
 
## Branches
- To create a new branch in git, use ```git branch [branchname]```
- To switch branches, use either ```git checkout [branchname]``` or ```git switch [branchname]```
- To delete a branch use ```git branch -d [branchname]```

## Merging Branches
- Usually, the 'main' or 'master' branch hold the real application/website code.
    - The branches are used to work on new features that will be implemented into the main branch when completed.
- To merge 2 branches, switch to the 'main' branch, then use ```git merge [branchname]``` 

## Feature Branches
- A feature workflow involves:
    - Creating feature branches
    - Uploading it to GitHub
    - Creating a 'Pull Request' (code reviews) 
    - M erging the feature branch into the main branch
- In our local repository, we have to add a link to the remote repository (in this case GitHub)
- Use ```git remote add [name, usually origin] [link]```
- Push it to GitHub with ```git push origin [branchname]```
- Compare and create a 'Pull Request'
- After all code reviews are done, you can merge.
>If you want to unlink your local repository with the remote one, use ```git remote remove origin```

## Updating Local Repository After Merge on GitHub
- To keep your local repository upto date with the repository on GitHub (if you are merging on GitHub), use ```git fetch```
- Then, pull the 'master' branch with ```git pull [RepoName] master```

## Cloning a Repository from GitHub
- ```cd``` to the directory where you want to keep the folder
- Use ```git clone [GitHublink]```

## Solving Merge Conflicts
- On GitHub, you can either solve merge conflicts using the web editor
- Or to edit the code on your local system, use ```git checkout master``` then ```git pull origin master```
- Use ```git checkout [branchname that is causing conflict]``` 
- Merge 'master' into [branchname]
- Fix the conflicts
- Add and commit
- Push the results to GitHub

## Protocols
- ### SSH (Secure Shell)
    - SSH includes a key pair - a private and a public key.
    - The public key can be shared anywhere - it encrypts data.
    - The private key is kept hidden for the local client - it decrypts the data.
    - It uses the TCP/IP Protocol.

## For a Summary
[GitHub Commands](https://supersimpledev.github.io/references/git-github-reference.pdf)
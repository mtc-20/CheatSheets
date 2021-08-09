# Git CheatSheet

## Contents
1. [Clone branch](#clone-branch)
2. [Remove from remote](#remove-from-remote)
3. [Change remote](#change-remote)


### Clone Branch
To clone only a single branch from a repo
```
git clone --single-branch --branch <branch_name> <repo_link>
```

### Remove from Remote
Often enough, it happens that I upload my `.vscode` settings folder to a new repo, because I forgot to create a `.gitignore` file beforehand. No more worries, I found an elegant solution [here][1]! (I am surprised that wasn't selected as the answer!)


To remove that file/folder(s) from the remote repo while still maintaining the files/folder(s), do the following:
- create or add the files to `.gitgnore` file
- and from the local repo folder, run the following command
  ```
  git rm --cached `git ls-files -i -X .gitgnore`
  ```
  
  
  [1]: https://stackoverflow.com/a/21477287

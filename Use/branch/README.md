# Git : Branch

the pointer '**HEAD**' is point to current branch.

### checkout

#### params
**-b**:create new branch and change to it.
followed the new branch name.
```
PS C:\ProjectSpace\Git> git checkout -b dev
M       README.md
M       Use/local/README.md
A       Use/remote/README.md
Switched to a new branch 'dev'
```
### branch
use this command to check current branch.
the branch which has a '**\***' in the front is the current.
```
PS C:\ProjectSpace\Git> git branch
* dev
  master
```

### merge
use this to combine the branch you choose to current branch.

*****
there may have some conflict happened in different branch, then when they are merging, something happened.

master & test1 add!

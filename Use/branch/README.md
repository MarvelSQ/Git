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
## Conflict
there may have some conflict happened in different branch, then when they are merging, something happened.

**create a new branch 'test1'**
```
PS C:\ProjectSpace\Git> git checkout -b test1
Switched to a new branch 'test1'
```

**change this file**
```
#33 test1 add!
```

**add & commit**
```
PS C:\ProjectSpace\Git> git add .\Use\branch\README.md
PS C:\ProjectSpace\Git> git commit -m 'test1 add'
[test1 966e2c1] test1 add
 1 file changed, 2 insertions(+)
```

**switch to master & change this file again**

```
#33 master add!
```
**add & commit**
```
PS C:\ProjectSpace\Git> git add .\Use\branch\README.md
PS C:\ProjectSpace\Git> git commit -m 'master add'[master 1cd2d10] master add
 1 file changed, 2 insertions(+)
```

**then merge with branch test1**
```
PS C:\ProjectSpace\Git> git merge test1
Auto-merging Use/branch/README.md
CONFLICT (content): Merge conflict in Use/branch/README.md
Automatic merge failed; fix conflicts and then commit the result.
```

**there is the conflicts, & you can see it use 'git status'**

```
PS C:\ProjectSpace\Git> git status
On branch master
Your branch is ahead of 'origin/master' by 1 commit.
  (use "git push" to publish your local commits)
You have unmerged paths.
  (fix conflicts and run "git commit")
  (use "git merge --abort" to abort the merge)
 
Unmerged paths:
  (use "git add <file>..." to mark resolution)
 
        both modified:   Use/branch/README.md
 
no changes added to commit (use "git add" and/or "git commit -a")
```

also you can see the conflict in the file, use **cat &lt;file&gt;**

```
cat .\Use\branch\README.md
# Git : Branch
 
the pointer '**HEAD**' is point to current branch.
.
.
.
<<<<<<< HEAD
master add!
=======
test1 add!
>>>>>>> test1
.
```

**you can change it, add & commit again**

```
PS C:\ProjectSpace\Git> git add .\Use\branch\README.md
PS C:\ProjectSpace\Git> git commit -m 'conflict fixed'
[master ab2c0db] conflict fixed
```

**git log --graph**

```
PS C:\ProjectSpace\Git> git log --graph
*   commit ab2c0db2983214220951301652fff435bbe836b3
|\  Merge: 1cd2d10 966e2c1
| | Author: MarvelSQ <sunqiang1993hlj@hotmail.com>
| | Date:   Thu Jul 20 23:40:25 2017 +0800
| |
| |     conflict fixed
| |
| * commit 966e2c18939d8104089b88585714445ea38261c8
| | Author: MarvelSQ <sunqiang1993hlj@hotmail.com>
| | Date:   Thu Jul 20 23:33:30 2017 +0800
| |
| |     test1 add
| |

* | commit 1cd2d10f978d649be857b2980b7aeb0be2ea0561
```

**this is a conflict**

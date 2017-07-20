# Git : Command

### init

Initialized empty Git repository

```
PS C:\ProjectSpace\Git> git init
Initialized empty Git repository in C:/ProjectSpace/Git/.git/
```

### add

add file to commit

#### params:
**&lt;file&gt;**:the file you add to commit.
```
PS C:\ProjectSpace\Git> git add README.md
```

### commit

commit the change

#### params:
**-m**:behind this params is description about commit.

```
PS C:\ProjectSpace\Git> git commit -m "first commit"
[master (root-commit) 0f65
8ab] first commit
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 README.md
```

### status

show the file status:
```
PS C:\ProjectSpace\Git> git status
On branch master
 
Initial commit
 
Changes to be committed:
  (use "git rm --cached <file>..." to unstage)
 
        new file:   README.md
 
```

### diff
show the file's difference between last commit.
#### params:
**&lt;file&gt;**:choise the file you want see difference.
```
PS C:\ProjectSpace\Git> git diff README.md
diff --git a/README.md b/README.md
index d3aa693..6b49a50 100644
--- a/README.md
+++ b/README.md
@@ -11,3 +11,4 @@ git commit -m "first commit"
 git remote add origin git@github.com:MarvelSQ/Git.git
 git push -u origin master
`` `
+## Github
```

### log
show the commit log

```
PS C:\ProjectSpace\Git> git log
commit be7f8a2702957a504e366a76b7a8bf55769b14be
Author: MarvelSQ <sunqiang1993hlj@hotmail.com>
Date:   Thu Jul 20 20:56:27 2017 +0800
 
    change Description&Use's name to README
 
commit 9551bfebbd196cfd74dab659ebe0118ec90b838c
Author: MarvelSQ <sunqiang1993hlj@hotmail.com>
Date:   Thu Jul 20 20:53:35 2017 +0800
```
#### params:
**--pretty=oneline**:simplfy the log message
```
PS C:\ProjectSpace\Git> git log --pretty=oneline
be7f8a2702957a504e366a76b7a8bf55769b14be change Description&Use's name to README
9551bfebbd196cfd74dab659ebe0118ec90b838c add Description&Use
ad91329ef51d8619583501d9c3a1c49a2a48b777 add README content
0f658aba4aa6ad22b871779729fdd45cc9f2ba30 first commit
```

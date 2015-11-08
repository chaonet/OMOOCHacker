# Git 教程
## 使用
### 创建仓库
- 从远程仓库clone
进入存放仓库的文件夹
git clone git@github.com:chaonet/OMOOCHacker.git # 创建 OMOOCHacker 文件夹，仓库内容完整 clone 到`OMOOCHacker`文件夹中
cd OMOOCHacker

- 将本地文件夹作为仓库
mkdir dir_name
cd dir_name
git init

- clone 本地仓库

### 添加、提交 已有文件
- 创建文件，查看 git 状态

```
➜  OMOOCHacker git:(master) ✗ git status
On branch master
Your branch is up-to-date with 'origin/master'.
Untracked files:
  (use "git add <file>..." to include in what will be committed)

	1sGit/Version.doc

nothing added to commit but untracked files present (use "git add" to track)
```

- `git add file_name`添加文件

```
➜  OMOOCHacker git:(master) ✗ git status
On branch master
Your branch is up-to-date with 'origin/master'.
Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

	new file:   1sGit/Version.doc

```

- `git reset <file>`撤销对文件的`add`

```
➜  OMOOCHacker git:(master) ✗ git reset 1sGit/Version.doc
➜  OMOOCHacker git:(master) ✗ git status
On branch master
Your branch is up-to-date with 'origin/master'.
Untracked files:
  (use "git add <file>..." to include in what will be committed)

	1sGit/Version.doc

nothing added to commit but untracked files present (use "git add" to track)
```

- `git commit -m 'sss'`提交，用`-m`添加描述

提交者信息`chao xu <chao@chaodeMBP.lan>`
```
➜  OMOOCHacker git:(master) ✗ git commit -m 'new ver'
[master ae8ff1b] new ver
 Committer: chao xu <chao@chaodeMBP.lan>
Your name and email address were configured automatically based
on your username and hostname. Please check that they are accurate.
You can suppress this message by setting them explicitly:

    git config --global user.name "Your Name"
    git config --global user.email you@example.com

After doing this, you may fix the identity used for this commit with:

    git commit --amend --reset-author

 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 1sGit/Version.doc
```

文件提交后被修改`modified `
```
➜  1sGit git:(master) ✗ git status
On branch master
Your branch is ahead of 'origin/master' by 1 commit.
  (use "git push" to publish your local commits)
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

	modified:   Version.doc

no changes added to commit (use "git add" and/or "git commit -a")
```

`deleted `文件被删除
```
➜  OMOOCHacker git:(master) rm 1sGit/Version.doc
➜  OMOOCHacker git:(master) ✗ git status
On branch master
Your branch is ahead of 'origin/master' by 1 commit.
  (use "git push" to publish your local commits)
Changes not staged for commit:
  (use "git add/rm <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

	deleted:    1sGit/Version.doc

no changes added to commit (use "git add" and/or "git commit -a")
```

- `git add .`添加全部更改，包括 对文件的删除

```
➜  1sGit git:(master) ✗ git add .
➜  1sGit git:(master) ✗ git status
On branch master
Your branch is ahead of 'origin/master' by 1 commit.
  (use "git push" to publish your local commits)
Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

	deleted:    Version.doc
	new file:   Version5.0.doc

```

提交
```
➜  1sGit git:(master) ✗ git commit -m 'new'
[master 7dddaa6] new
 Committer: chao xu <chao@chaodeMBP.lan>
Your name and email address were configured automatically based
on your username and hostname. Please check that they are accurate.
You can suppress this message by setting them explicitly:

    git config --global user.name "Your Name"
    git config --global user.email you@example.com

After doing this, you may fix the identity used for this commit with:

    git commit --amend --reset-author

 2 files changed, 0 insertions(+), 0 deletions(-)
 delete mode 100644 1sGit/Version.doc
 create mode 100644 1sGit/Version5.0.doc
```

- `git log`查看提交历史

```
commit 0f8777cad4508900198f94e96a67741012b66219
Author: chao xu <chao@chaodeMBP.lan>
Date:   Sat Nov 7 16:50:30 2015 +0800

    back

commit 7dddaa64d446c02f370472a61f95fcc1e81f199f
Author: chao xu <chao@chaodeMBP.lan>
Date:   Sat Nov 7 16:38:13 2015 +0800

    new

commit ae8ff1b99c764bfab1cd9b45234d894493c1a6b9
Author: chao xu <chao@chaodeMBP.lan>
Date:   Sat Nov 7 16:22:59 2015 +0800

    new ver

commit b9408e19ce08da0494481c790cc1ae03ddb2a96b
Author: Azeril <azeril@live.cn>
Date:   Sat Oct 31 08:02:53 2015 +0800

    Add some new files

commit d7964a17689a69cefd5e1f0db88be579996e923f
Author: Azeril <azeril@live.cn>
Date:   Thu Oct 29 15:31:56 2015 +0800

    Create a new repo
```

- git reset –hard：彻底回退到某个版本。重置文件版本、之后的所有add、commit。
>并不是真正退回，只是后面的版本看不到。可以通过这个方法自由在版本间切换。
`--hard                reset HEAD, index and working tree`
```
➜  1sGit git:(master) git reset --hard 7dddaa
HEAD is now at 7dddaa6 new
```

- git reset --soft：回退到某个版本add后的状态，只重置commit的操作。可以通过commit提交新版本。

`--soft                reset only HEAD`
```
➜  1sGit git:(master) git reset --soft ae8ff1
➜  1sGit git:(master) ✗ git status
On branch master
Your branch is ahead of 'origin/master' by 1 commit.
  (use "git push" to publish your local commits)
Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

	deleted:    Version.doc
	new file:   Version5.0.doc

```

提交新版本

```
➜  1sGit git:(master) ✗ git commit -m 'two files'
[master 9ff1fdb] two files
 Committer: chao xu <chao@chaodeMBP.lan>
Your name and email address were configured automatically based
on your username and hostname. Please check that they are accurate.
You can suppress this message by setting them explicitly:

    git config --global user.name "Your Name"
    git config --global user.email you@example.com

After doing this, you may fix the identity used for this commit with:

    git commit --amend --reset-author

 2 files changed, 0 insertions(+), 0 deletions(-)
 delete mode 100644 1sGit/Version.doc
 create mode 100644 1sGit/Version5.0.doc
```

- git reset：默认`--mixed`，回退到某个版本未add、commit的状态

```
➜  1sGit git:(master) git reset ae8ff1
Unstaged changes after reset:
D	1sGit/Version.doc
➜  1sGit git:(master) ✗ git status
On branch master
Your branch is ahead of 'origin/master' by 1 commit.
  (use "git push" to publish your local commits)
Changes not staged for commit:
  (use "git add/rm <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

	deleted:    Version.doc

Untracked files:
  (use "git add <file>..." to include in what will be committed)

	Version5.0.doc

no changes added to commit (use "git add" and/or "git commit -a")
```

- `git log`查看提交历史

```
commit 0f8777cad4508900198f94e96a67741012b66219
Author: chao xu <chao@chaodeMBP.lan>
Date:   Sat Nov 7 16:50:30 2015 +0800

    back

commit 7dddaa64d446c02f370472a61f95fcc1e81f199f
Author: chao xu <chao@chaodeMBP.lan>
Date:   Sat Nov 7 16:38:13 2015 +0800

    new

commit ae8ff1b99c764bfab1cd9b45234d894493c1a6b9
Author: chao xu <chao@chaodeMBP.lan>
Date:   Sat Nov 7 16:22:59 2015 +0800

    new ver

commit b9408e19ce08da0494481c790cc1ae03ddb2a96b
Author: Azeril <azeril@live.cn>
Date:   Sat Oct 31 08:02:53 2015 +0800

    Add some new files

commit d7964a17689a69cefd5e1f0db88be579996e923f
Author: Azeril <azeril@live.cn>
Date:   Thu Oct 29 15:31:56 2015 +0800

    Create a new repo
```

- `git reflog`查看命令历史

```
0f8777c HEAD@{0}: reset: moving to 0f8777
2d02586 HEAD@{1}: commit: test2 history
ae8ff1b HEAD@{2}: reset: moving to ae8ff1
9ff1fdb HEAD@{3}: commit: two files
ae8ff1b HEAD@{4}: reset: moving to ae8ff1
7dddaa6 HEAD@{5}: reset: moving to 7dddaa
0f8777c HEAD@{6}: reset: moving to 0f8777cad4508900198f94e96a67741012b66219
d5d87ad HEAD@{7}: commit: test1
0f8777c HEAD@{8}: commit: back
7dddaa6 HEAD@{9}: commit: new
ae8ff1b HEAD@{10}: commit: new ver
b9408e1 HEAD@{11}: clone: from git@github.com:chaonet/OMOOCHacker.git
```

### 获取帮助
git -h
git <command> -h

### 查看git信息、进行配置
git —-version
```
➜  OMOOCHacker git:(master) ✗ git --version
git version 2.4.9 (Apple Git-60)
```
git config —global user.name ‘chant'   # 修改提交时的用户名
git config —global user.email ’name@mail.com’   # 修改提交时的邮件地址

### 推送到远程仓库
从远端仓库clone创建的，不需要这步：
git remote add origin git@url   # 向git 的配置文件中添加 远程仓库名称'origin'、地址'git@url'

git push -u origin master  # 初次推送时，使用`-u`参数，让git记住 push 的远程仓库、分支，后续可以直接`git push`
```
➜  OMOOCHacker git:(master) git push -u origin master
Counting objects: 4, done.
Delta compression using up to 4 threads.
Compressing objects: 100% (4/4), done.
Writing objects: 100% (4/4), 9.68 KiB | 0 bytes/s, done.
Total 4 (delta 2), reused 0 (delta 0)
To git@github.com:chaonet/OMOOCHacker.git
   b9408e1..ae8ff1b  master -> master
Branch master set up to track remote branch master from origin.
```
git push   # 使用过`-u`参数后，可以简单使用这条命令进行推送


### git 的配置内容
git 的配置在仓库根目录下的隐藏文件夹`.git`中

使用`ls -a`查看所有文件和文件夹，包括隐藏文件夹
```
➜  OMOOCHacker git:(master) ✗ ls -a
.            .git         2nMarkdown   4tMac        6tGitbook    README.md    _book        node_modules
..           1sGit        3rJekyll     5tCLI        About.md     SUMMARY.md   book.json
```

进入存放配置的隐藏文件夹`.git`
```
➜  OMOOCHacker git:(master) ✗ cd ./.git
➜  .git git:(master) ls
HEAD        branches    config      description hooks       index       info        logs        objects     packed-refs refs
```

查看配置内容
```
➜  OMOOCHacker git:(master) ✗ cat ./.git/config
[core]
	repositoryformatversion = 0
	filemode = true
	bare = false
	logallrefupdates = true
	ignorecase = true
	precomposeunicode = true
[remote "origin"]
	url = git@github.com:chaonet/OMOOCHacker.git
	fetch = +refs/heads/*:refs/remotes/origin/*
[branch "master"]
	remote = origin
	merge = refs/heads/master
```

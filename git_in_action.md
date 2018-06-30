

# Hello World (2^n)

## git 初始配置


设置默认提交的用户和邮箱

```bash
$ git config --global user.name "your name"
$ git config --global user.email your_email@example.com
```

设置默认编辑器（可选）

` $ git config --global core.editor vim`

查看设置

` $ git config --list `

## 最基本的文件本地操作

` git init` 新建一个git仓库

` git add` 添加文件到当前项目管理，一般直接使用`git add .`添加所有文件（git能够自动识别文件是否被修改过，未修改但已经被git管理的文件不会被添加）。

` git commit` 提交`git add`添加的文件到本地代码仓库。会出现文本编辑器要求提交相关的代码说明，也可以直接用`-m "your comment" `提交说明。

` git commit -a` 相当于` git add .` 后执行` git commit`，但注意，**此命令不会提交新的文件，只会提交仓库中已有的和已经add的文件**

` git rm `和` git mv` 删除/移动指定文件，感觉没太大用，可以直接删除/移动后用` git add .`

## 查看状态

` git status` 查看文件的修改和添加状态。`-s` 参数得到简单的状态。

` git diff ` 显示没有被add的文件做出的修改。可以添加`--staged`参数，显示被add但没有commit的文件的的修改。

` git log` 查看提交日志，`-p`得到具体的修改，`--stat`显示修改的文件，`-2`显示最近的两次修改。

## .gitignore文件

` git add .`会添加所有的文件，可以在.gitignore文件中的添加不希望加入到仓库的文件。

```bash
# ignore .o .a 
*.[oa]

# ignore files begin with "~"
~*

# do track by "!"
!aa.txt

# ignore all files in the build/ directory
build/

# ignore doc/notes.txt, but not doc/server/arch.txt
doc/*.txt

# ignore all .txt files in the doc/ directory
doc/**/*.txt

```

## Hello World End

使用上述命令能够向本地仓库提交文件并查看基本的提交状态。

# Hello World (n^2)

## git 代码管理形式

典型的分布式管理方式，分为本地仓库和远程仓库。典型的流程为：每个人将远程仓库clone到本地；在本地修改代码或者添加新代码，然后commit到本地仓库；将本地的提交push到远程仓库。

TODO 加图

github可以直接作为远程仓库使用，可以多个人同时使用一个github仓库，但是更建议使用github的pull request操作：fork想要提交修改的远程仓库到自己的github仓库；从自己的github仓库clone修改后push推送（同上）；从自己github仓库发送pull request到之前fork的仓库。


## 撤销操作

注意某些操作针对未提交前的处理，可能导致对文件修改的丢失。git对已提交的文件几乎总是可以恢复的，因此建议尽量在提交后处理。

` git commit --amend` 重新提交，提交后删除上一次提交。 



# 远程仓库

` git remote -v` 显示远程仓库名和对应的URL。

` git remote show <remote-name>` 显示远程仓库信息

` git fetch <remote-name>` 获取远程仓库的数据。

` git push <remote-name> <branch-name>` 推送相应的分支到远程仓库。默认为master分支。



# TODO

- push和pull是所有代码还是只有对应的分支
- 冲突处理方式
- 本地提交之后推送了所有提交还是一两次提交


------

# 撤销操作2

以下命令存在危险性不建议使用。


` git checkout <file>` 撤销文件修改（到上一次提交）。


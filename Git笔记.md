# Git笔记

[Git教程 ](https://www.liaoxuefeng.com/wiki/0013739516305929606dd18361248578c67b8067c8c017b000)

###1 前言

主要内容来源于廖雪峰网站，内容通俗易懂，有些地方用了Gif来演示，实用性超强。至于git的强大，就不强调很多了，觉得不错，就自己整理了一下。

### 2 git简介

Git是目前世界上最先进的分布式版本控制系统（没有之一）。首先，分布式版本控制系统根本没有“中央服务器”，每个人的电脑上都是一个完整的版本库，这样，你工作的时候，就不需要联网了，因为版本库就在你自己的电脑上。既然每个人电脑上都有一个完整的版本库，那多个人如何协作呢？比方说你在自己电脑上改了文件A，你的同事也在他的电脑上改了文件A，这时，你们俩之间只需把各自的修改推送给对方，就可以互相看到对方的修改了。和集中式版本控制系统相比，分布式版本控制系统的安全性要高很多，因为每个人电脑里都有完整的版本库，某一个人的电脑坏掉了不要紧，随便从其他人那里复制一个就可以了。而集中式版本控制系统的中央服务器要是出了问题，所有人都没法干活了。

#### 2.1 [git安装](http://github.liaoxuefeng.com/sinaweibopy/video/git-apt-install.mp4)

linux上的命令

```
sudo apt-get install git
```

windows上

从官网[下载安装程序](https://git-scm.com/downloads) ，或者[国内镜像](https://pan.baidu.com/s/1kU5OCOB#list/path=%2Fpub%2Fgit) ，正常安装完在桌面右键会有git相关显示。安装完成后需要设置
$$

$$

```
$ git config --global user.name "Your Name"
$ git config --global user.email "email@example.com"
# 注意git config命令的--global参数，用了这个参数，表示你这台机器上所有的Git仓库都会使用这个配置，当然也可以对某个仓库指定不同的用户名和Email地址
```

#### 2.2 版本库建立

用命令行建立一个文件夹，或者在已有文件夹下面右键进入git命令窗口，然后执行命令

```
git init
```

具体可以看[建立版本库](http://github.liaoxuefeng.com/sinaweibopy/video/git-init.mp4)。

#### 2.3 添加文件到版本库

```
# 第一步
$ git add readme.txt
# 第二步
$ git commit -m "wrote a readme file"
[master (root-commit) cb926e7] wrote a readme file
 1 file changed, 2 insertions(+)
 create mode 100644 readme.txt
```

具体可看[添加文件到版本库](http://github.liaoxuefeng.com/sinaweibopy/video/add-and-commit.mp4).

#### 2.4 总结

初始化一个Git仓库，使用`git init`命令。

添加文件到Git仓库，分两步：

- 第一步，使用命令`git add <file>`，注意，可反复多次使用，添加多个文件；
- 第二步，使用命令`git commit`，完成。

###3 本地版本控制

使用 git status 命令，查看当前工作区与版本库状态

```
git status
# On branch master
# Changes not staged for commit:
#   (use "git add <file>..." to update what will be committed)
#   (use "git checkout -- <file>..." to discard changes in working directory)
#
#    modified:   readme.txt
#
no changes added to commit (use "git add" and/or "git commit -a")
```

git diff 查看修改变化具体使用：

```
$ git diff readme.txt 
diff --git a/readme.txt b/readme.txt
index 46d49bf..9247db6 100644
--- a/readme.txt
+++ b/readme.txt
@@ -1,2 +1,2 @@
-Git is a version control system.
+Git is a distributed version control system.
 Git is free software.
```

[演示](http://github.liaoxuefeng.com/sinaweibopy/video/git-diff-status.mp4)


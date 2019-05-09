# 背景介绍

代码版本管理大致分为三个阶段：本地式，客户端-服务器式，分布式；我们常用的git属于分布式，而Subversion则属于客户端-服务器式,其典型的产品如tortoiseSVN。

本文主要围绕tortoiseSVN其对应命令行式客户端The Subversion Command Line Client：svn描述简单的本地代码版本管理基础知识。

# The Subversion Command Line Client：svn简单介绍

可以理解为运行在windows系统下的tortoiseSVN命令行版本；其svn.exe程序提供了add,status,checkout,diff,commit等常见命令。完整参考

[官方文档](http://svnbook.red-bean.com/en/1.4/index.html)

svn开始流程大致为：
- 1. 新建服务器（repo)
- 2. 导入一个或多个项目；
- 3. checkout项目到工作区(Working copy)文件夹。

> 之后就是在工作区的日常操作。如新增(svn add),状态查看(svn status), 对比修改文件(svn diff),提交修改文件(svn commit)等。


# 实践一： svn + network share + git 本地局域网的远程仓库的搭建

> 这里讨论的特殊场景是：后端开发人员具备代码库所有git权限，而前端开发人员不具备这个权限。因此我们基于给定的远程文件夹，利用svn实现一个本地代码版本管理功能。

**步骤**

- 1. 按照svn官方指导新建repo库，导入代码文件夹，创建工作区文件夹。
- 2. 如何同步repo库代码到远程文件夹
- 2.1 如何解决同步过程中，远程文件夹有更新的场景
- 2.2 如何显示本地库与远程文件夹冲突，并显示diff详细信息
- 2.3 如何快速解决本地库与远程文件夹的冲突，并安全合并
- 3.代码同步到工作区文件夹


# 实践二： git  本地局域网的远程仓库的搭建

参考 [这里](https://blog.csdn.net/github_36878269/article/details/80967388)

>适合局域网所有人都具备访问全部代码库权限的场景。

---
title: Git 学习总结
published: 2022-10-17
description: Git 版本控制系统的基本理论与常用命令行操作总结
tags: [Git, 版本控制, 工具]
category: 技术工具
draft: false
---

## Git 的学习

### 版本控制

- 集中式版本控制 SVN

  将所有的版本数据都保存在中央服务器上，开发者同步更新或上传自己的修改

- 分布式版本控制 git

  所有的版本信息仓库都同步到每个用户

  <u>本次学习重点</u>
  
  <!--more-->

### 常用命令行

1. cd：改变目录
2. cd..：退回上一个目录
3. pwd：显示当前所在的目录路径
4. clear：清屏
5. ls（ll）：列出当前目录的所有文件
6. rm：删除文件
7. mkdir：创建目录
8. rm -r：删除当前文件夹
9. rm -r src：删除 src 目录
10. mv srcA srcB：把 srcA 移动到 srcB
11. reset：重新初始化终端
12. history：查看历史
13. help：帮助
14. exit：退出

### git 基本理论

![git 基本理论](https://img-blog.csdn.net/20140417104150109)

![git 工作流程](https://img-blog.csdn.net/20140417113336421)

### git 项目搭建

基本操作

```bash
# 查看指定文件状态
git status [filename]

# 查看所有文件状态
git status

# 将工作目录中所有的文件提交至暂存区
git add .
    
# 将暂存区的内容提交至本地仓库 -m 是 message 后面跟的是提交信息
git commit -m "消息内容"
   
# 将本地仓库的内容提交至远端
git push
```

忽略文件

```gitignore
一些例子

*.txt # 忽略所有以.txt
!lib.txt # 不忽略 lib.txt
/tmep # 向上忽略
bulid/ # 向下忽略    
```

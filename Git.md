###  Git

1.下载git进入dash操作界面

```
需要以下配置
1.配置用户名(提交时会引用)
git config --global user.name "用户名"
2.配置邮箱(提交时会引用)
config --global User.email"邮箱地址"
3.其他配置
git config --global merge.tool "kdiff3"(根据是否安装,安装就配置)
git config --global core.autocrlf false
#让Git不要管Windows/Unix换行符转换的事
4.配置编码
git config --global gui.encoding utf-8
#避免git gui中的中文乱码
git config --global core.quotepath off
#避免gitstatus显示的中文文件乱码
Windows上还需要配置
git config --global core.ignorecase false
5.生成ssh公钥
ssh -Keygen -t rsa -C"邮箱地址"
一路回车
6.ssh-add ~/.ssh/id_rsa
7.cat ~/.ssh/id_rsa.pub
得到秘钥
```

2.如何在idea工具中关联git

```
1.file/setting/version controller/git
在右侧的Path to Git executable :路径是你的git.exe
2.file/setting/teminal
的右侧Shell path =\Git\bin\bash.exe
```

3.提交工程(terminal中操作)

```
1.touch README.md(写入你要写的关键信息)
2.touch .gitignore
模板:
*class
#package file
*.war
*.ear
*ds
#kdiff3 ignore
*.orig

#maven ignore
target/

#idea
.idea/
/ideal/
*.ipr
*.iml
*.iws

#temp file
*.log
*.cache
*.patch
*.tmp

#system ignore
.DS_Strore
Thumbs.db

3.git init
4.git status
5.git add .
6.git status
7.git commit -am '注释内容'
8.git remote add origin git地址
9.git branch
10.git push -u origin master
11.git pull
12.git push -u -f origin master
13.git branch
14.git branch -r
15.git checkout -b v1.0 origin/master
16.git branch
17.git push origin HEAD -u
```

创建分支并提交到分支

````
一:第一创建本地库,并且向远程第一次提交代码建立项目
    1.建立一个空的文件夹作为本地仓库
    2.进入该文件夹 cd /Users/zhanglizhi/Desktop/test本地库
  3.git init   //作为git项目
    4.关联本地与远程仓库 git remote add origin https://github.com/zhanglizhi123/IvarTezt.git
  5.第一次提交代码建立文件 touch REARD.md
  6.git add REARD.md  //跟新
  7.git commit -m "第一次提交” //提交本地库
  8.第一次提交远程库生成master $git push -u origin master 
  9.查看git log

  10.第一次将项目文件脱入本地库
  11.git add .  //跟新变动
  12.git commit -m "提交代码scrollview”  //提交代码
  13.建立分支new_分支 git checkout -b new_分支
  14.查看分支  git branch
  15.git push origin new_分支 将代码提交到改分支


二:从远程拉取已经有的代码到本地并且建立新的本地库
  1.进入想要建立本地库的目录下 cd /Users/zhanglizhi/Desktop/
  2.从远程获取代码到本地库相应文件下(没有就自动建立文件名是 test2_本地库)  git clone https://github.com/zhanglizhi123/IvarTezt.git test2_本地库
  3.进入该关联的本地库   cd /Users/zhanglizhi/Desktop/test2_本地库 
  4.获取远程分支  git branch -a
  5.拉取合并远程相应分支代码到本地  git pull origin new_分支
````

修改用户和邮箱

```
git 修改提交邮箱以及用户名
原创 2016年11月23日 10:37:56 标签：git 2387
    一.查看git配置

          $ git config --list     此命令会列出所有GIT当时能找到的配置
           ...

          查看 列表项

          user.email=123@qq.com        邮箱
          user.name=123                         用户名

    二.修改邮箱和用户名

         1.重新设置邮箱和用户名

          $ git config --global user.email"123456@qq.com"   

          $ git config --global user.name"123456"  

          2.在原有的基础上，修改邮箱和用户名

          $ git config --global  -e              显示当前邮箱和用户名

          i                                                     字母i 编写状态（在git命令行左下角显示 - -插入- -）   

          ......                                                修改邮箱和用户名

          Esc                                                电脑左上角Esc键（退出编辑）

          Shift+;                                             Shift键和分号键 同时点击（git命令行左下角显示 ：）
          wq                                                   输入此命令后回车
```

```
git add 1.java
git add 2.java
git status 查看放入缓存中问价1.java 2.java
如果要删除缓存中的文件可通过
git rm --cached 1.java
```


### git如何把远程分支更新到本地分支

参考地址:http://blog.csdn.net/tterminator/article/details/78108550

1.查看本地分支与远程分支的映射关系

````
git branch -vv
````

2.建立本地分支与远程分支的映射关系(当前分支)

````
git branch -u origin/远程分支名

或者使用命令：

git branch --set-upstream-to origin/addFile
````

3.撤销本地分支与远程分支的映射关系

```
git branch --unset-upstream
```

4.拉去

```
git pull

```

上传(同名)

```
git push
```

上传(不同命)

```
git push 
```


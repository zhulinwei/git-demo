# git demo
git 存在工作区、暂存区、版本库三个概念

## 初始化
```git
git init
```

## 添加文件
将工作区文件提交到暂存区

### 添加指定文件
```git
git add file.txt
或
git add *.js
或
git add dir/*
```

### 添加全部文件
```git
git add .
或
git add -A
```

## 提交文件
将暂存区文件提交到版本库
```git
git commit -m 'some describe'
```

## 查看日志
```git
git log --pretty=oneline
或
git reflog
```

## 版本回退
### 回退上一个版本
```git
git reset --hard HEAD^
```
### 回退指定版本A
```git
git reset --hard commit_id_of_A
```

## 状态查询
```git
git status
```

## 比较不同
```git 
git diff master
或
git diff master -- file.txt
```

### 撤销修改

### 撤销工作区中的文件修改
注意双横杠，如果没有双横杠的话git checkout就变成了切换分支了
```git
git checkout -- file
```

### 撤销暂存区中的文件修改
```git
git reset HEAD file
```

### 撤销版本库中的文件修改
```git
git reset --hard commit_id_of_A
```

### 撤销远程版本库中的文件修改
撤不了，没救了，考虑覆盖吧

### 删除文件与恢复
+ 1.如果你用rm删除文件，那就相当于只删除了工作区的文件，如果想要恢复，可直接用git checkout -- file就可以
+ 2.如果你用的是git rm删除文件，那就相当于不仅删除了文件，而且还添加到了暂存区，需要先git reset HEAD file，然后再git checkout -- file
+ 3.如果你想彻底把版本库的删除掉，先git rm，再git commit，以后要是想恢复，怕是有点困难，除非该文件在上一个版本中出现过，你可以考虑回退版本，但不建议这样做

## 添加远程库
在Github上创建完仓库并拿到地址后，执行
```git
git remote add origin url_of_repository
```

## 推送远程库
```git
git push origin master
```
如果是初次推送文件到远程仓库的话，需要
```git
git push -u origin master
```

## 克隆远程库
```git
git clone url_of_repository
或
git clone -b branch_name url_of_repository
```

## 拉取远程库
```git
git pull
```
如果不希望拉取的过程中有合并操作，我们可以：
```git
git pull --rebase
```

## 创建分支
```git
git checkout -b dev
或
git branch dev
git checkout dev
```

## 查看分支
```git
git branch
或
git branch -a
```

## 删除本地分支
``` git
git branch -d dev
或
git branch -D dev
```

## 删除远程分支
``` git
git push origin :branch_name
```

## 合并分支
合并某分支到当前分支（如果是想要将dev合并到master时，注意先切换回master）
``` git
git merge branch_name
```

## 存档分支
如果分支在工作的途中需要暂停并且执行突发任务，我们可以考虑将当前分支存档，让其恢复到初始状态
```git
git stash
```
我们在分支上处理完突发情况并在主分支完成合并后，可以读档继续开始分支在之前的工作
```git
git stash pop
```

## 创建标签
```git
git tag tag_id
或
git tag tag_id commit_id
```

## 查看标签
```git
git tag
```

## 标签详情
```git
git show tag_id
```

## 推送标签
```git
git push origin tag_id
或
git push origin --tags
```

## 删除标签
+ 1.删除本地标签：git tag -d tag_id
+ 2.删除远程标签：先删除本地，然后git push origin :refs/tags/tag_id

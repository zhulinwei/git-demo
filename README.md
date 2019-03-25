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
或
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
撤不了，没救了


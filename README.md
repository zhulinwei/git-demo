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

# git demo

## 初始化
```git
git init
```

## 添加文件
```git
git add file.txt
```

## 提交文件
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
git reset --hard id_of_A
```




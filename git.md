## 配置
- 的git邮箱和账号
```
git config --global user.name '用户名'
git config --global user.email '邮箱'
```
- 查看配置
git config --list
##  创建目录
```
mkdir 目录的名字
```
## 改变目录
```
cd ..
```
# locals
##  git init 
初始化本地仓库，表示当前文件夹归git所管理

## echo可以输入内容并且创建文件 
```
echo hello > index.txt
```

## 查看文件的内容
```
cat 文件名
```
## 编辑
```
vi index.txt
```

> 先按i键 进入insert模式 更改后按esc， :wq退出

## 追加内容
```
echo world >> index.txt
```
> 一个大于号表示清空并写入，两个大于号表示追加内容

## 将内容追加到暂存区中
```
git add .   /git add -A / git add 文件名
```

## 提交到历史区中
```
git commit 
```

## 查看版本库日志
```
git log --oneline
```
## 比较不同
- 默认比较的是工作区和暂存区的不同
```
git diff 
```
- 工作区和版本库
```
git diff master
```
- 暂存区和版本库
```
git diff --cached
``` 
## 不能用于某个文件的首次提交
```
git add 
git commit -m
git commit -a -m 'write second'
```

## 拉回本次的add内容
```
git reset HEAD index.txt
```
## 将暂存区的内容覆盖掉工作区
```
git checkout index.txt
```
> 暂存区中没有会从历史区拉回来

## 回滚
- 用历史区覆盖掉工作区
```
git reset --hard 版本号
```
## 查看历史版本
```
git reflog
```

## 回滚指定回滚几个版本
```
git reset --hard HEAD^/HEAD~1
```


## 分支
- 创建分支
```
git branch 分支的名字
```
- 切换分支
```
git checkout dev
```
- 查看所有分支
```
git branch
```
- 删除分支
``` 
git branch -d dev 
```
## 既创建分支还要进入到分支中
```
git branch dev
git checkout dev
git checkout -b dev 
```

> git checkout -b gh-pages 一步到位

## 在分支上进行开发
- 开发后切换到主分支上合并本次的开发
```
git merge dev
```
> 在主干上合并就要切换到主分支上

## 解决冲突
将<<<<<   ====== >>>>> 删除保留想要的再次add commit 生成合并后的版本
## 创建文件
```
touch dev.js
```
- 显示图表并显示分支
```
git log --graph --decorate
```


```
git branch 
git checkout 
git merge 
git branch -d
```


## 如果正在开发时 切换分支 要保证工作区和暂存区都为干净的否则不让切换

## 保存到历史
- 用历史区覆盖暂存区和工作区
```
git stash
```

## 查看保存的内容
```
git stash list
```
## 应用历史并且删除历史
```
git stash apply 
git stash drop
=
git stash pop
```

## rebase 变基 
- rebase和merge的区别 
- 更改了合并的线 
- 不会产生新的提交，在当此提交上演绎分支上的提交，最终合并成了一个提交
```
git rebase dev
```
## cherry-pick 挑选精选
```
git cherry-pick 当前分支的版本号
```

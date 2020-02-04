### 命令行本地仓库：提交流程

将改动文件提交到暂存区（标记文件）

    git add .
  
将缓存区内容添加到本地仓库中（标记的文件提交到本地仓库）

    git commit -m "xxx"
    
### 命令行本地仓库：新建分支

新建dev分支

    git branch dev
    
切换至新建分支

    git checkout dev
    
和远程分支关联（使用git在本地新建一个分支后，需要做远程分支关联，目的是在执行git pull, git push操作时就不需要指定对应的远程分支，你只要没有显示指定，git pull的时候，就会提示你）

    git push --set-upstream origin newBranch
    
  或者
  
    git push origin newBranch  // 远程无newBranch分支
    

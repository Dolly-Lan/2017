### git commit规范

[资料](https://github.com/angular/angular.js/blob/master/DEVELOPERS.md#commits)

  * feat: A new feature
  * fix: A bug fix
  * docs: Documentation only changes
  * style: Changes that do not affect the meaning of the code (white-space, formatting, missing semi-colons, etc)
  * refactor: A code change that neither fixes a bug nor adds a feature
  * perf: A code change that improves performance
  * test: Adding missing or correcting existing tests
  * chore: Changes to the build process or auxiliary tools and libraries such as documentation generation

### 删除本地/远程指定分支

删除本地：

    git branch -d 分支名
    
删除远程分支：

    git push origin –-delete 分支名 

### add

命令会更新package.json和yarn.lock文件

    yarn add package-name  // 会安装 latest 最新版本。
    yarn add package-name@1.2.3   // 会从 registry 里安装这个包的指定版本。
    yarn add package-name --dev/-D   // 用 --dev 或 -D 会在 devDependencies 里安装一个或多个包。

### remove

依赖中移除指定包，在此期间会更新你的 package.json 和 yarn.lock 文件。

    yarn remove package-name
    
    

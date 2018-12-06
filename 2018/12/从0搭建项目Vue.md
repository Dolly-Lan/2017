### package.json

    {
      "name": "xxx",   // 页面title配置项 package.json不能使用中文
      "version": "1.0.0",
      "description": "xx",  // 页面description配置项
      "author": "cjtir",
      "private": true,
      "scripts": {  // * npm 快捷命令配置项
        "dev": "fi-pack dev",
        "build": "fi-pack build",
        "lint": "eslint --ext .js,.vue src"
      },
      "dependencies": {
        "vue": "2.4.2"   // * vue库 同vue-template-compiler版本一致，否则运行vue-template-compiler会报错
      },
      "devDependencies": {
        "@360es/fi": "^10.1.4",  // * fi 库
        "vue-template-compiler": "2.4.2"   // * 编译template模版库
      }
    }
    
### fi.config.js

使用自动化脚手架，类似vue-cli


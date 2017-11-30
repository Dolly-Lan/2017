
### package.json中 dependencies devdependencies的区别

以ngsoc中的package.json为例

    "devDependencies": {
		"autoprefixer": "~6.3.6",
		"babel-core": "6.14.0",
		"babel-eslint": "6.0.4"，
		"express": "4.14.0",
    ｝,
    "dependencies": {
		"@qnpm/FUI": "^1.2.7",
		"@qnpm/httpmw": "^1.0.7",
		"d3": "~3.5.6",
		"easy-mock": "^1.0.0",
		"echarts": "3.7.0",
		"highcharts": "^6.0.3",
		"jquery": "~2.2.4"
    }

可见此处：devDependencies安装的都是用于代码检查编译等等工具型，dependencies是安装一些项目所需的类库、框架
所以总结就是：

1. dependencies是正常运行该包时所需要的依赖项，而devDependencies则是开发的时候需要的依赖项
2. 同时执行npm install命令会安装这2项中所有的依赖，npm install -save安装dependencies，npm install -save-dev安装devDependencies

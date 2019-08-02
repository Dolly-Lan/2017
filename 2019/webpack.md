### require.context(directory, useSubdirectories, regExp )

[参考资料](https://www.jianshu.com/p/c894ea00dfec)

自动化导入模块：在前端工程中,如果遇到从一个文件夹引入很多模块的情况,可以使用这个api,它会遍历文件夹中的指定文件,然后自动导入,使得不需要每次显式的调用import导入模块

#### 参数说明：

directory {String} -读取文件的路径

useSubdirectories {Boolean} -是否遍历文件的子目录

regExp {RegExp} -匹配文件的正则

#### 返回值

为**函数**类型，
参数：匹配的文件名的相对路径
返回值：模块,这个模块才是真正我们需要的

且包含以下重要属性和方法：

.id： 返回了匹配的文件夹的相对于工程的相对路径,是否遍历子目录,匹配正则组成的字符串
.keys()： 返回了一个由匹配文件的文件名组成的数组
.resolve(): 参数即匹配文件名的相对路径，返回值为该文件相对于整个工程的相对路径

    const files = require.context("./modules", false, /\.js$/)  // 遍历modules目录下的所有js文件，假设有目录下有index.js、test.js， 相对与项目根木路为./src/modules
    console.log(files(files.keys()[0])) // 返回index.js这个模块
    console.log(files.id) // "./modules sync \.js$"
    console.log(files.keys()) // ["./index.js", "./test.js"]
    console.log(files.resolve(files.keys()[0])) // "./src/modules/index.js"

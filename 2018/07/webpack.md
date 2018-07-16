 ### resolve (解析) 的 alias（别名）
 
    resolve: {
      alias: {
        'vue': 'vue/dist/vue.common.js'   // 独立构建（包含模版编译器）
      }
    }
    
  vue有两种构建方式，独立构建和运行构建(runtime-only)。它们的区别在于前者包含模板编译器而后者不包含。而默认 NPM 包导出的是 运行时(runtime-only)构建。为了使用独立构建，要在webpack 配置中添加下面的别名：添加alias:{'vue':'vue/dist/vue.common.js'}. 这个别名，同样适用于jquery,zepto这些库。这样在import vue from 'vue' 的时候，如果不配置alias，使用的是NPM导出的独立构建的vue库，如果配置了alias为vue.common.js则使用的是包含模版编译器的运行时构建vue库

对于vue来说，如果不用别名，也可以从node_modules/vue/dist/复制vue.common.js到开发目录下，比如./src/vue下面，然后像普通的js文件一样引用, import vue from './src/js/vue.common.js' 这也是可以的。只是和使用别名相比，显的很lower 

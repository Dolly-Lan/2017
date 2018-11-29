### 介绍

> Handlebars 是 JavaScript 一个语义模板库，通过对view和data的分离来快速构建Web模板。它采用"Logic-less template"（无逻辑模版）的思路，在加载时被预编译，而不是到了客户端执行到代码时再去编译， 这样可以保证模板加载和运行的速度。Handlebars兼容Mustache，你可以在Handlebars中导入Mustache模板。

### 基本语法

#### {{value}}

* 输出变量值
* 调用函数

示例：

    <h1>{{title}}</h1>  {{! 如果没找到匹配项，则没有输出。}}
    <p>{{content.title}}</p>  {{! 支持点操作符}}

#### {{#Array}}{{/Array}}

Block表达式：自动展开数组，并将Blocks的上下文设为数组中的元素

模版代码示例：

    ul>  
    {{#programme}}    {{! {programme: [{language: "JavaScript"}, {language: "HTML"}, {language: "CSS"}]} }}
        <li>{{language}}</li>
    {{/programme}}
    </ul>
   
 编译结果示例：
 
    <ul>  
      <li>JavaScript</li>
      <li>HTML</li>
      <li>CSS</li>
    </ul>
    


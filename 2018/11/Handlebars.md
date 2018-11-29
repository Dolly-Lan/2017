### 介绍

> Handlebars 是 JavaScript 一个语义模板库，通过对view和data的分离来快速构建Web模板。它采用"Logic-less template"（无逻辑模版）的思路，在加载时被预编译，而不是到了客户端执行到代码时再去编译， 这样可以保证模板加载和运行的速度。Handlebars兼容Mustache，你可以在Handlebars中导入Mustache模板。

### 基本语法

#### {{value}}

* 输出变量值
* 调用函数

示例：

    <h1>{{title}}</h1>  {{! 如果没找到匹配项，则没有输出。}}
    <p>{{content.title}}</p>  {{! 支持点操作符 }}
    <p>{{array.length}}</p>  {{! 支持array为数组类型变量的长度语法读取长度值 }}

#### {{#array}}{{/array}}

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
    
#### {{#each array}}{{/each}}

each block helper：遍历列表块内容，this表示当前遍历的对象，同block表达式的用法很像，但是比block表达式多了this对象直接读取

模版代码示例：

    <ul>  
      {{#each name}} {{! {name: ["html","css","javascript"]} }}
        <li>{{this}}</li>
      {{/each}}
    </ul>  
    
编译结果示例：
 
    <ul>  
      <li>html</li>
      <li>css</li>
      <li>javascript</li>
    </ul>
    
#### {{#if value}}{{else}}{{/if}}

if else block helper：value变量的值为true，则编译{{#if value}}后面的模版，如果value变量的值为false，则编译{{else}}后面的模版。
**由于handlebar属于无逻辑模版，所以value只能是变量值，而不能使用运算符（===、<=、>=）比较得出true/false**，如果需要支持逻辑判断，请使用[链接文字][link id]

### registerHelper()


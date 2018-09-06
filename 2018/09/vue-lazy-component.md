### Git 地址

https://github.com/xunleif2e/vue-lazy-component

### Demo 地址

https://xunleif2e.github.io/vue-lazy-component/demo/dist/index.html

### Demo 源码所在git目录

    /demo/views/
  
### 安装

    npm install @xunlei/vue-lazy-component
    
### 注册

https://github.com/xunleif2e/vue-lazy-component#%E4%BD%BF%E7%94%A8

### 使用

    <vue-lazy-component>
      <div>真正模块内容</div>
      <div slot="skeleton">lazy时的占位内容</div>
    </vue-lazy-component>
    
### vue-lazy-component 的Props

  https://github.com/xunleif2e/vue-lazy-component#props
  
 * viewport: 视窗，默认为浏览器窗口，指定时可选定任意视窗，如vue-lazy-component的所在组件的父组件视窗，可通过$el获得上级组件的根部DOM元素


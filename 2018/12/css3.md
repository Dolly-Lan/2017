### :root

选择器，用于匹配文档根元素，在HTML文档中的根元素是html

  :root {
    --theme-color: 'red'
  }
  button {
    background-color: var(--theme-color);
  }

### :nth(a*n + b)

n从0开始计算

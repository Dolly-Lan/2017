### 解构赋值

允许我们将**数组**或**对象**的属性赋予给任何变量，该变量的定义语法与数组字面量或对象字面量很相似。

#### 数组

有序：变量与值一一对应关系

    let [param1, param2, param3] = [1, 2 ,3]
    console.log(param1, param2, param3)  // param1=>1, param2=>2, param3=>3
    
可缺失：缺失处必须使用","分隔

    let [param1, param2, param3, param4] = [1, 2, ,4]
    console.log(param1, param2, param3, param4)  // param1=>1, param2=>2, param3=>undefined, param4=>4
    
或：

    let [param1, param2, , param4] = [1, 2, 3, 4]
    console.log(param1, param2, param3, param4)  // param1=>1, param2=>2, param3=>undefined, param4=>4
    
支持"rest“模式：

    let [head, ...tail] = [1, 2, 3, 4];  
    console.log(tail);  // [2, 3, 4]  
    
#### 对象

和数组的用法相类似，一个主要的不同点是，对象是无次序排列的，所以变量必须和属性名相同。

示例：

    let { username, password } = { username: 'dolly', password: '123456' }
    
函数参数的解构赋值：

    function add({ x, y }) {
      return x + y
    }
    add({ x: 1, y: 2 })  // 相当于let {x, y} = { x: 1, y: 2 }
  

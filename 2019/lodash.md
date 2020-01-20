### _.max()

  _.max(Array)
  
### _.sortBy() 对象数组排列

  var users = [
    { 'user': 'fred',   'age': 48 },
    { 'user': 'barney', 'age': 36 },
    { 'user': 'fred',   'age': 40 },
    { 'user': 'barney', 'age': 34 }
  ];
  _.sortBy(users， ['age'])  // 默认升序
  _.sortBy(users, [function(item){ return -item.count }]) // 降序

### _.difference(array, [values])  提出源数据中的目标数据，且返回新数组

    array (Array): 要检查的数组。
    [values] (...Array): 排除的值。

### _.endsWith(string, [value])  判断字符串是否已某字符串结尾，且返回true/false

    _.endsWith('abc', 'c');

### _.equalWidth(value, other) 判断value和other是否相等

[文档](https://www.lodashjs.com/docs/latest#_isequalvalue-other)


### _.mean(array) 求数组平均值

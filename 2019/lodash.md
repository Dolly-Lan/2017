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

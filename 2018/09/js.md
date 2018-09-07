### typeof 和 instanceof 用法

    typeof + 变量
    变量 + instanceof + Array/Funtion/ObjectString/....


### Array.find(fun) 函数

  找到数组中符合fun条件的第一个元素值
        
      let obj = {}
      let arr = [{
        value: 1,
        label: '猫'
      }, {
        value: 2,
        label: '狗'
      }]
      obj = arr.find(item => {    // obj 为　{value: 1, label: '猫'}
        return item.value === 1
      })
       

### watch

  watch数组类型时也要设定 deep: true
  
### $router.push()传参

    $router.push({
      patch: '',
      query: {
        name1: '',
        name2: ''
      }
    })

### $set(target, key, value)

  更新Array类型的key值时也需要使用此方法，否则无法watch变化

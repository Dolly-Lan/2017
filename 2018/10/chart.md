### format

有可能是多个系列的数组时，需用回调函数来处理

    formatter: (params) => {
      let str = ''
      params.map(item => {
        str += `${item.seriesName}:${item.value}</br>`
      })
      return str
    }

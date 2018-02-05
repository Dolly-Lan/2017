中文字符换行 word-break: break-all 
文字两端对齐 text-align: justfy

关于隐藏滚动条：对overflow-x:hidden/scroll时 也需要对 overflow-y同步设置对应的效果 否则会引起同步修改

table表头固定表体滚动条

  通过在传统的表格的tbody中直接设置max-height是没有效的，需要把“表头”和“表体”拆开独立成2个table，并且通过对每个table的table-layout属性设置为fixed
  然后再通过统一colgroup的宽度来达到表头和表体列对齐
  
  > 关于table-layout作用： 用于设置表格宽度和列宽度的生成方式
    
 * automatic（默认值）： 表格的列的宽会根据单元格中的内容来自动生成，确保能不换行全部展示每个单元格的内容，表格的宽度则会自动生成所有列宽的累加
宽度，即使对列和表格设定固定宽度也不会生效
      
 * fixed ：表格的列宽会优先根据手动配置的列宽来生成，如果没有配置列宽，那么会根据表格宽度来自动分配

    <table style="table-layout:fixed;width:100px">  <!--表头-->
      <!--通过colgroup设置列宽-->
      <colgroup>  
        <col width="20"></col>
        <col width="30"></col>
        <col width="50"></col>
      </colgroup>
      <thead>
        <th>
          <td></td>
          <td></td>
          <td></td>
        </th>
      </thead>
    </table>
    <table style="max-height: 200px; style="table-layout:fixed;width:100px"> <!--表体-->
      <!--通过colgroup设置列宽-->
      <colgroup>
        <col width="20"></col>
        <col width="30"></col>
        <col width="50"></col>
      </colgroup>
      <tbody>
        <tr>
          <td></td>
          <td></td>
          <td></td>
        </tr>
      </tbody>
    </table>

calc()
 
 

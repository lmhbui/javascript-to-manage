#manage后台JS和API交互接口

- [专场相关](#专场)  

#专场

#专场编辑-数据字段
```
专场ID :{{$id}}
专场品牌：{{$partner_brand['title']}}
专场标题：{{$title}}
Pc专场图（322*308）：{{$image_pc_small['image_path']}}
Pc Banner图（1920*250）：{{$image_pc_banner['image_path']}}
app专场图（1080*462）：{{$image_app_big['image_path']}}
app专场图（770*540）:{{$image_app_small['image_path']}}
app专场Banner（720*290）：{{$image_app_banner['image_path']}}
```

#商品设置
```
表格插件 请求地址
url: '/event/item?event_id=' +{{$id}} (专场id)
  param: {
   page_size: 20 //每页显示多少条数据
  }
  
商品设置下的数据字段
商品ID：<%= id %>
商品信息 ：<%= title %>
价格（元）：<%= sales_price %><%= market_price %>
库存：<%= stock %>
佣金：(%)<%= commission %>
开始/结束时间：<%= begin_at %>/<%= end_at %>
状态：<%= status_name %>
操作（查看）：
<td data-name="opration"  width="100" class="tac">
  <a data-id="<%= id %>" data-name="<%= name %>" href="javascript:;" class="edit" title="查看">查看</a>
</td>
```

#专场管理页面
```
专场列表Tab统计数字 请求地址：
'/event/count'

表格插件请求地址：
'/event/list'

审核/排期  请求地址：
'/event/audit'

审核排期/待上线状态：再次审核 请求地址：
'/event/remark?event_id=' + id






  
                    



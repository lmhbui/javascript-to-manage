#manage后台JS和API交互接口

- [专场编辑](#专场编辑)  
- [专场编辑-商品设置](#专场编辑-商品设置) 
- [专场管理页面](#专场管理页面)
- [专场列表Tab数字统计](#专场列表tab统计数字)
- [审核](#审核)

#专场

#专场编辑
1.请求地址

2.请求参数

3.返回结果
```
数据字段
专场ID :{{$id}}
专场品牌：{{$partner_brand['title']}}
专场标题：{{$title}}
Pc专场图（322*308）：{{$image_pc_small['image_path']}}
Pc Banner图（1920*250）：{{$image_pc_banner['image_path']}}
app专场图（1080*462）：{{$image_app_big['image_path']}}
app专场图（770*540）:{{$image_app_small['image_path']}}
app专场Banner（720*290）：{{$image_app_banner['image_path']}}
```

#专场编辑-商品设置
1.请求地址
```
表格插件 
url: '/event/item?event_id=' +{{$id}} (专场id)
```
2.请求参数
```
id//专场id
param: {
  page_size: 20 //每页显示多少条数据
}
```
3.返回结果 
```
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
4.代码示例
```
require([], function () {

    //表格插件
    var table = $('#datatable').dataTable({
        url: '/event/item?event_id=' + $('#event_id').val(),
        param: {
            page_size: 20 //每页显示多少条数据
        }
    });

});
```
#专场管理页面
#专场列表
1.请求地址
```
url: '/event/list'
```
2.请求参数
```
{
}
```
3.返回结果
```
专场ID：<%= id %>
创建时间 <%= create_at %>

专场信息
图片地址：<%= img_url %>
标题：<%= title %> 
预览专场 <a target="_blank" href="/event/edit?event_id=<%= id %>" class="edit ui-btn" title="预览专场"><span>预</span></a>
品牌:<%= brand_title %>

在线商品/总数： <%= total_item_official %>/<%= total_item %>
商家信息： <%= partner_title %>
开始/结束时间: <%= begin_at %><br/><%= end_at %>
备注： <%= remark %>

操作
查看专场： <a target="_blank" href="/event/edit?event_id=<%= id %>" class="edit ui-btn" title="查看专场"><span class="ui-icon ui-icon-zoomin"></span></a> 
审核 ：<a data-id="<%= id %>" href="javascript:;" class="examine ui-btn" title="审核"><span class="ui-icon ui-icon-transferthick-e-w"></span></a>
审核排期：<a data-id="<%= id %>" href="javascript:;" class="examine1 ui-btn" title="审核排期"><span class="ui-icon ui-icon-calendar"></span></a>
修改排期：<a data-id="<%= id %>" data-arr="<%= begin_at %>,<%= end_at %>,three" href="javascript:;" class="schedule ui-btn" title="修改排期"><span class="ui-icon ui-icon-calendar"></span></a>
        
```

#专场列表Tab统计数字 
1.请求地址
```
'/event/count'
```
2.请求参数
```
{
}
```
3.返回结果
```
{
}
```
4.示例
```
Tab统计数字：
define([], function () {
    var i = $('.dc-tab').find('i');

    function refresh() {
        setTimeout(function () {
            $.post('/event/count')
                .done(function (res) {
                    _.each(res, function (val, index) {
                        i.eq(index).text(val);
                    });
                });
        }, 10);
    }

    return {
        refresh: refresh
    };
});
```
#审核
```
审核：请求地址'/event/audit'

示例:
 function examine(html) {
            $.jBox(html, {
                width: 600,
                height: 500,
                title: "商家审核",
                buttons: buttons,
                submit: function (v, h, f) {
                    if (v) {
                        var status = $('input[name=status]:checked').val();
                        if (status == -2) {
                            if (!$('textarea[name=remark]').val()) {
                                alert('不通过时审核备注必填');
                                return false;
                            }
                        }
                        var parms = $('#examine-form').serialize();
                        $.post('/event/audit', parms, function (res) {
                            refresh(res);
                        });
                    }
                }
            });
        }

排期：请求地址'/event/audit'
示例
function schedule(html, width, height, title) {
            $.jBox(html, {
                width: width,
                height: height,
                title: title,
                buttons: buttons,
                submit: function (v, h, f) {
                    if (v) {
                        $.post('/event/audit', $('#examine-form1').serialize(), function (res) {
                            refresh(res);
                        });
                    }
                }
            });
        }
```
#审核排期
1.请求地址
```
'/event/remark?event_id=' + id
```
2.请求参数
```
{
}
```
3.返回结果
```
历史审核备注： <%= listHtml %>
```
4.示例
```
//审核排期
  table.opration('examine1', function (id) {
    $.get('/event/remark?event_id=' + id).done(function (res) {
      var data = {
            examine_id: id,
            listHtml: getMarkList(res)
        },
        tpl = $('#audit_event_status1').text(),
        html = $.template(tpl, data);
    schedule(html, 600, 500, '修改排期');
    });
  });

```
#待上线状态再次审核
1.请求地址
```
'/event/remark?event_id=' + id
```
2.请求参数
```
{
}
```
3.返回结果
```
开始时间：<%= begin_at %>
结束时间：<%= end_at %>
状态：<%= status_kind %>
```
4.示例
```
 //待上线状态:再次审核
  table.opration('schedule', function (id, arr) {
      arr = arr.split(',');
      $.get('/event/remark?event_id=' + id).done(function (res) {
          var data = {
                  examine_id: id,
                  listHtml: getMarkList(res),
                  begin_at: arr[0].replace(/\./g, '-'),
                  end_at: arr[1].replace(/\./g, '-'),
                  status_kind: arr[2]
              },
              tpl = $('#audit_event_status2').text(),
              html = $.template(tpl, data);
          schedule(html, 380, 180, '修改排期');
      });
  });
```




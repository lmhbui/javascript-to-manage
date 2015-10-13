#manage后台专场页面JS和API交互接口

#专场列表页
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
[
    4,
    3,
    2,
    16,
    16,
    32,
    4
]
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
#专场列表页-审核列表

1.请求地址
```
/event/list
```
2.请求参数
```
ajax:1
page:1
page_size:20
id:
title:
brand_title:
partner_title:
event_status:0
begin_time:
end_time:
```

3.返回结果
```
{
    "errorcode": 0,
    "datatable": {
        "list": [
            {
                "id": 119,
                "title": "1111",
                "sales_title": "",
                "url_key": "",
                "discount_word": "",
                "is_recommend": 0,
                "channel_ids": "",
                "seo_title": "",
                "seo_keywords": "",
                "seo_description": "",
                "begin_at": "1970-01-01 08:00",
                "end_at": "1970-01-01 08:00",
                "sort_num": 0,
                "show_goods": 0,
                "update_at": "0",
                "delete_at": 0,
                "is_delay": 1,
                "image_logo_id": 0,
                "image_pc_banner_id": 50,
                "image_pc_small_id": 50,
                "image_app_banner_id": 50,
                "image_app_big_id": 50,
                "image_app_small_id": 50,
                "brand_id": 0,
                "image_banner_id": 0,
                "partner_brand_id": 0,
                "partner_id": 17,
                "platform_id": 0,
                "status": 0,
                "remark": "",
                "create_at": "2015-07-20 19:51:43",
                "event_item": [],
                "partner": {
                    "id": 17,
                    "username": "13544445555",
                    "rank": 1,
                    "contact_name": "31232131",
                    "contact_wang": "",
                    "contact_qq": "111",
                    "contact_qq2": "abcdafa",
                    "contact_mobile": "13514785698",
                    "contact_email": "",
                    "sale_admin_id": 0,
                    "buyer_admin_id": 111,
                    "alipay_account": "111",
                    "alipay_name": "111",
                    "bank_province": "7",
                    "bank_city": "412",
                    "bank_name": "中国建设银行",
                    "bank_sub_name": "111",
                    "bank_user": "111",
                    "bank_no": "111",
                    "delivery_province_id": 2,
                    "delivery_city_id": 8892,
                    "account_type": 1,
                    "exemption": null,
                    "auth_status": 2,
                    "auth_message": "",
                    "auth_admin_id": 1,
                    "auth_at": 1437707966,
                    "is_liquidate": 0,
                    "liquidate_at": 0,
                    "create_at": "1444376947",
                    "update_at": "1444376947",
                    "delete_at": 0,
                    "is_overseas": 0,
                    "title": "布袋测试的商家"
                },
                "partner_brand": null,
                "event_status": [],
                "event_remark": [],
                "preview_url": "http://www.lamahui.loc",
                "partner_title": "布袋测试的商家",
                "brand_title": null,
                "remarks": "",
                "notes": "",
                "img_url": "http://img.test.lamahui.com/static/images/2015/06/24/73bce5a79cbb466c731b37caca31bef42340.gif",
                "total_item_official": 0,
                "total_item": 0
            }
          ],"total_count":1
        }
  }
```
#专场列表页-审核排期列表
1.请求地址
```
/event/list
```
2.请求参数
```
ajax:1
page:1
page_size:20
id:
title:
brand_title:
partner_title:
event_status:1
begin_time:
end_time:
```
3.返回结果
```
{
    "errorcode": 0,
    "datatable": {
        "list": [
            {
                "id": 120,
                "title": "11212312",
                "sales_title": "",
                "url_key": "",
                "discount_word": "",
                "is_recommend": 0,
                "channel_ids": "",
                "seo_title": "",
                "seo_keywords": "",
                "seo_description": "",
                "begin_at": "1970-01-01 08:00",
                "end_at": "1970-01-01 08:00",
                "sort_num": 0,
                "show_goods": 0,
                "update_at": "1444725040",
                "delete_at": 0,
                "is_delay": 1,
                "image_logo_id": 0,
                "image_pc_banner_id": 50,
                "image_pc_small_id": 50,
                "image_app_banner_id": 50,
                "image_app_big_id": 50,
                "image_app_small_id": 50,
                "brand_id": 16,
                "image_banner_id": 0,
                "partner_brand_id": 0,
                "partner_id": 17,
                "platform_id": 0,
                "status": 10,
                "remark": "",
                "create_at": "2015-07-20 19:52:02",
                "event_item": [],
                "partner": {
                    "id": 17,
                    "username": "13544445555",
                    "rank": 1,
                    "contact_name": "31232131",
                    "contact_wang": "",
                    "contact_qq": "111",
                    "contact_qq2": "abcdafa",
                    "contact_mobile": "13514785698",
                    "contact_email": "",
                    "sale_admin_id": 0,
                    "buyer_admin_id": 111,
                    "alipay_account": "111",
                    "alipay_name": "111",
                    "bank_province": "7",
                    "bank_city": "412",
                    "bank_name": "中国建设银行",
                    "bank_sub_name": "111",
                    "bank_user": "111",
                    "bank_no": "111",
                    "delivery_province_id": 2,
                    "delivery_city_id": 8892,
                    "account_type": 1,
                    "exemption": null,
                    "auth_status": 2,
                    "auth_message": "",
                    "auth_admin_id": 1,
                    "auth_at": 1437707966,
                    "is_liquidate": 0,
                    "liquidate_at": 0,
                    "create_at": "1444376947",
                    "update_at": "1444376947",
                    "delete_at": 0,
                    "is_overseas": 0,
                    "title": "布袋测试的商家"
                },
                "partner_brand": {
                    "id": 16,
                    "title": "贝亲",
                    "license_type": "sole",
                    "begin_date": 1435766400,
                    "end_date": 1436371200,
                    "fee_rate": -1,
                    "audit_admin_id": 0,
                    "audit_status": 0,
                    "audit_reson": "",
                    "audit_at": 0,
                    "delete_admin_id": 0,
                    "update_at": null,
                    "delete_at": 0,
                    "age_range": "2",
                    "sex_range": 1,
                    "remark": "",
                    "remark_admin_id": 0,
                    "brand_level": 0,
                    "partner_id": 17,
                    "brand_id": 1,
                    "registr_image": 50,
                    "brand_image": 50,
                    "other_image": 50,
                    "create_at": null
                },
                "event_status": [
                    {
                        "id": 230,
                        "step": "one",
                        "status": 1,
                        "admin_id": 163,
                        "event_id": 120,
                        "remark": "",
                        "create_at": "1444725040"
                    }
                ],
                "event_remark": [
                    {
                        "id": 8,
                        "event_id": 120,
                        "admin_id": 331,
                        "content": "好的",
                        "create_at": "1444708106",
                        "update_at": "0",
                        "delete_at": 0,
                        "admin": {
                            "id": 331,
                            "username": "js_wj",
                            "name": "汪杰",
                            "password": "$2y$10$Vt/pRh7DcRfXlZvxdWcr3uN8y/rcz43TnWO4VgETFdbCUxX66bpJW",
                            "remember_token": "9XuV6U7F8UFkqHxz0p6UL0ztSizvUoG5oqzQ8Prkk2tp2ABChdFrN5T5Cabd",
                            "reg_salt": "",
                            "menu_group_id": 0,
                            "status": 1,
                            "initial": 1,
                            "is_active": 0,
                            "update_at": "1444467799",
                            "delete_at": 0,
                            "group_id": 0,
                            "create_at": "1444284340",
                            "role_id": 0,
                            "email": "wangjie@lamahui.com",
                            "department": 5
                        }
                    }
                ],
                "preview_url": "http://www.lamahui.loc",
                "partner_title": "布袋测试的商家",
                "brand_title": "贝亲",
                "remarks": "",
                "notes": "汪杰: 好的<br />",
                "img_url": "http://img.test.lamahui.com/static/images/2015/06/24/73bce5a79cbb466c731b37caca31bef42340.gif",
                "total_item_official": 0,
                "total_item": 0
            }
        ],
        "total_count": 1
    }
}
```
#专场列表页-待上线列表
1.请求地址
```
/event/list
```
2.请求参数
```
ajax:1
page:1
page_size:20
id:
title:
brand_title:
partner_title:
event_status:2
begin_time:
end_time:
```
3.返回结果
```
{
    "errorcode": 0,
    "datatable": {
        "list": [
            {
                "id": 139,
                "title": "ll测试专场",
                "sales_title": "",
                "url_key": "",
                "discount_word": "",
                "is_recommend": 0,
                "channel_ids": "",
                "seo_title": "",
                "seo_keywords": "",
                "seo_description": "",
                "begin_at": "2015-10-14 00:00",
                "end_at": "2015-10-31 00:00",
                "sort_num": 0,
                "show_goods": 0,
                "update_at": "1444619435",
                "delete_at": 0,
                "is_delay": 1,
                "image_logo_id": 0,
                "image_pc_banner_id": 98,
                "image_pc_small_id": 103,
                "image_app_banner_id": 98,
                "image_app_big_id": 99,
                "image_app_small_id": 106,
                "brand_id": 32,
                "image_banner_id": 0,
                "partner_brand_id": 0,
                "partner_id": 25,
                "platform_id": 0,
                "status": 1,
                "remark": "",
                "create_at": "2015-07-23 14:00:36",
                "event_item": [
                    {
                        "id": 121428,
                        "event_id": 139,
                        "sort_num": 0,
                        "create_at": "0",
                        "update_at": "0",
                        "delete_at": 0,
                        "item_id": 20000246,
                        "item_detail": {
                            "id": 20000246,
                            "title": "测试商品1",
                            "sales_title": "卖点",
                            "market_price": "117.00",
                            "sales_price": "57.00",
                            "supply_price": "54.15",
                            "taobao_seller_id": 0,
                            "is_buy_change": 0,
                            "postage_tpl_id": 0,
                            "source_platform": "",
                            "source_id": "0",
                            "click_url": "",
                            "intended_population": "778",
                            "stock": 15,
                            "status": 1,
                            "is_able_apply": 0,
                            "create_at": "1437469120",
                            "update_at": "1437631380",
                            "delete_at": 0,
                            "brand_id": 32,
                            "cate1_id": 366,
                            "cate2_id": 370,
                            "cate3_id": 0,
                            "partner_id": 25,
                            "item_type_id": 1,
                            "is_overseas": 0,
                            "image_id1": 88,
                            "image_id2": 0,
                            "website": ""
                        }
                    }
                ],
                "partner": {
                    "id": 25,
                    "username": "18868816701",
                    "rank": 1,
                    "contact_name": "luolan",
                    "contact_wang": "",
                    "contact_qq": "461564840",
                    "contact_qq2": "",
                    "contact_mobile": "18868816701",
                    "contact_email": "",
                    "sale_admin_id": 0,
                    "buyer_admin_id": 0,
                    "alipay_account": "",
                    "alipay_name": "",
                    "bank_province": "1",
                    "bank_city": "",
                    "bank_name": "",
                    "bank_sub_name": "",
                    "bank_user": "",
                    "bank_no": "",
                    "delivery_province_id": 0,
                    "delivery_city_id": 0,
                    "account_type": 1,
                    "exemption": null,
                    "auth_status": 2,
                    "auth_message": "",
                    "auth_admin_id": 1,
                    "auth_at": 1437468778,
                    "is_liquidate": 0,
                    "liquidate_at": 0,
                    "create_at": "1437468745",
                    "update_at": "1437468778",
                    "delete_at": 0,
                    "is_overseas": 0,
                    "title": "不二家"
                },
                "partner_brand": {
                    "id": 32,
                    "title": "贝亲",
                    "license_type": "own",
                    "begin_date": 1435680000,
                    "end_date": 1438272000,
                    "fee_rate": -1,
                    "audit_admin_id": 0,
                    "audit_status": 1,
                    "audit_reson": "",
                    "audit_at": 1437449083,
                    "delete_admin_id": 0,
                    "update_at": "1437449083",
                    "delete_at": 0,
                    "age_range": "1,6",
                    "sex_range": 0,
                    "remark": "",
                    "remark_admin_id": 0,
                    "brand_level": 0,
                    "partner_id": 25,
                    "brand_id": 1,
                    "registr_image": 90,
                    "brand_image": 90,
                    "other_image": 90,
                    "create_at": null
                },
                "event_status": [
                    {
                        "id": 63,
                        "step": "one",
                        "status": 1,
                        "admin_id": 1,
                        "event_id": 139,
                        "remark": null,
                        "create_at": "0"
                    },
                    {
                        "id": 193,
                        "step": "one",
                        "status": 1,
                        "admin_id": 331,
                        "event_id": 139,
                        "remark": "测试",
                        "create_at": "1444619411"
                    },
                    {
                        "id": 194,
                        "step": "two",
                        "status": 1,
                        "admin_id": 331,
                        "event_id": 139,
                        "remark": "排期",
                        "create_at": "1444619435"
                    }
                ],
                "event_remark": [],
                "preview_url": "http://www.lamahui.loc",
                "partner_title": "不二家",
                "brand_title": "贝亲",
                "remarks": "排期",
                "notes": "",
                "img_url": "http://img.test.lamahui.com/static/images/2015/07/23/99c5ae4adc815407f9ecf733a3d337849770.png",
                "total_item_official": 1,
                "total_item": 1            
            }
        ],
        "total_count": 1
    }
}
```
#专场列表页-上线中列表
1.请求地址
```
/event/list
```
2.请求参数
```
ajax:1
page:1
page_size:20
id:
title:
brand_title:
partner_title:
event_status:3
begin_time:
end_time:
```

3.返回结果
```
{
    "errorcode": 0,
    "datatable": {
        "list": [
            {
                "id": 150,
                "title": "彩色",
                "sales_title": "",
                "url_key": "",
                "discount_word": "",
                "is_recommend": 0,
                "channel_ids": "",
                "seo_title": "",
                "seo_keywords": "",
                "seo_description": "",
                "begin_at": "2015-10-11 00:00",
                "end_at": "2015-10-16 00:00",
                "sort_num": 0,
                "show_goods": 0,
                "update_at": "1444703831",
                "delete_at": 0,
                "is_delay": 1,
                "image_logo_id": 0,
                "image_pc_banner_id": 5568,
                "image_pc_small_id": 5567,
                "image_app_banner_id": 5571,
                "image_app_big_id": 5569,
                "image_app_small_id": 5570,
                "brand_id": 17,
                "image_banner_id": 0,
                "partner_brand_id": null,
                "partner_id": 17,
                "platform_id": 0,
                "status": 1,
                "remark": "",
                "create_at": "2015-10-13 10:09:51",
                "event_item": [
                    {
                        "id": 121460,
                        "event_id": 150,
                        "sort_num": 6,
                        "create_at": "0",
                        "update_at": "1444702374",
                        "delete_at": 0,
                        "item_id": 20000277,
                        "item_detail": {
                            "id": 20000277,
                            "title": "布袋测试商品",
                            "sales_title": "布袋商品杠杠滴",
                            "market_price": "120.00",
                            "sales_price": "20.00",
                            "supply_price": "18.80",
                            "taobao_seller_id": 0,
                            "is_buy_change": 0,
                            "postage_tpl_id": 0,
                            "source_platform": "",
                            "source_id": "0",
                            "click_url": "",
                            "intended_population": "100",
                            "stock": 100,
                            "status": 1,
                            "is_able_apply": 0,
                            "create_at": "1444299889",
                            "update_at": "1444300003",
                            "delete_at": 0,
                            "brand_id": 17,
                            "cate1_id": 340,
                            "cate2_id": 348,
                            "cate3_id": 390,
                            "partner_id": 17,
                            "item_type_id": 1,
                            "is_overseas": 0,
                            "image_id1": 5523,
                            "image_id2": 0,
                            "website": ""
                        }
                    },
                    {
                        "id": 121461,
                        "event_id": 150,
                        "sort_num": 2,
                        "create_at": "0",
                        "update_at": "1444702374",
                        "delete_at": 0,
                        "item_id": 20000280,
                        "item_detail": {
                            "id": 20000280,
                            "title": "布袋测试专场商品",
                            "sales_title": "布袋测试",
                            "market_price": "100.00",
                            "sales_price": "10.00",
                            "supply_price": "9.70",
                            "taobao_seller_id": 0,
                            "is_buy_change": 0,
                            "postage_tpl_id": 0,
                            "source_platform": "",
                            "source_id": "0",
                            "click_url": "",
                            "intended_population": "1,2",
                            "stock": 100,
                            "status": 1,
                            "is_able_apply": 0,
                            "create_at": "1444359566",
                            "update_at": "1444359667",
                            "delete_at": 0,
                            "brand_id": 17,
                            "cate1_id": 171,
                            "cate2_id": 183,
                            "cate3_id": 0,
                            "partner_id": 17,
                            "item_type_id": 1,
                            "is_overseas": 0,
                            "image_id1": 5523,
                            "image_id2": 0,
                            "website": ""
                        }
                    },
                    {
                        "id": 121462,
                        "event_id": 150,
                        "sort_num": 5,
                        "create_at": "0",
                        "update_at": "1444702374",
                        "delete_at": 0,
                        "item_id": 20000281,
                        "item_detail": {
                            "id": 20000281,
                            "title": "布袋测试专场商品",
                            "sales_title": "布袋测试",
                            "market_price": "100.00",
                            "sales_price": "10.00",
                            "supply_price": "9.70",
                            "taobao_seller_id": 0,
                            "is_buy_change": 0,
                            "postage_tpl_id": 0,
                            "source_platform": "",
                            "source_id": "0",
                            "click_url": "",
                            "intended_population": "775,776",
                            "stock": 100,
                            "status": 1,
                            "is_able_apply": 0,
                            "create_at": "1444359568",
                            "update_at": "1444359653",
                            "delete_at": 0,
                            "brand_id": 17,
                            "cate1_id": 171,
                            "cate2_id": 183,
                            "cate3_id": 0,
                            "partner_id": 17,
                            "item_type_id": 1,
                            "is_overseas": 0,
                            "image_id1": 5523,
                            "image_id2": 0,
                            "website": ""
                        }
                    },
                    {
                        "id": 121463,
                        "event_id": 150,
                        "sort_num": 4,
                        "create_at": "0",
                        "update_at": "1444702374",
                        "delete_at": 0,
                        "item_id": 20000283,
                        "item_detail": {
                            "id": 20000283,
                            "title": "测试产品2",
                            "sales_title": "布袋的商品",
                            "market_price": "120.00",
                            "sales_price": "10.00",
                            "supply_price": "9.70",
                            "taobao_seller_id": 0,
                            "is_buy_change": 0,
                            "postage_tpl_id": 0,
                            "source_platform": "",
                            "source_id": "0",
                            "click_url": "",
                            "intended_population": "774",
                            "stock": 200,
                            "status": 1,
                            "is_able_apply": 0,
                            "create_at": "1444463276",
                            "update_at": "1444463432",
                            "delete_at": 0,
                            "brand_id": 17,
                            "cate1_id": 341,
                            "cate2_id": 344,
                            "cate3_id": 0,
                            "partner_id": 17,
                            "item_type_id": 1,
                            "is_overseas": 0,
                            "image_id1": 5523,
                            "image_id2": 0,
                            "website": ""
                        }
                    },
                    {
                        "id": 121464,
                        "event_id": 150,
                        "sort_num": 3,
                        "create_at": "0",
                        "update_at": "1444702374",
                        "delete_at": 0,
                        "item_id": 20000284,
                        "item_detail": {
                            "id": 20000284,
                            "title": "测试产品3",
                            "sales_title": "布袋的商品",
                            "market_price": "120.00",
                            "sales_price": "10.00",
                            "supply_price": "9.70",
                            "taobao_seller_id": 0,
                            "is_buy_change": 0,
                            "postage_tpl_id": 0,
                            "source_platform": "",
                            "source_id": "0",
                            "click_url": "",
                            "intended_population": "3",
                            "stock": 200,
                            "status": 1,
                            "is_able_apply": 0,
                            "create_at": "1444463290",
                            "update_at": "1444463449",
                            "delete_at": 0,
                            "brand_id": 17,
                            "cate1_id": 341,
                            "cate2_id": 344,
                            "cate3_id": 0,
                            "partner_id": 17,
                            "item_type_id": 1,
                            "is_overseas": 0,
                            "image_id1": 5523,
                            "image_id2": 0,
                            "website": ""
                        }
                    },
                    {
                        "id": 121465,
                        "event_id": 150,
                        "sort_num": 1,
                        "create_at": "0",
                        "update_at": "1444702374",
                        "delete_at": 0,
                        "item_id": 20000285,
                        "item_detail": {
                            "id": 20000285,
                            "title": "测试产品4",
                            "sales_title": "布袋的商品",
                            "market_price": "120.00",
                            "sales_price": "10.00",
                            "supply_price": "9.70",
                            "taobao_seller_id": 0,
                            "is_buy_change": 0,
                            "postage_tpl_id": 0,
                            "source_platform": "",
                            "source_id": "0",
                            "click_url": "",
                            "intended_population": "5",
                            "stock": 200,
                            "status": 1,
                            "is_able_apply": 0,
                            "create_at": "1444463297",
                            "update_at": "1444463496",
                            "delete_at": 0,
                            "brand_id": 17,
                            "cate1_id": 341,
                            "cate2_id": 344,
                            "cate3_id": 0,
                            "partner_id": 17,
                            "item_type_id": 1,
                            "is_overseas": 0,
                            "image_id1": 5523,
                            "image_id2": 0,
                            "website": ""
                        }
                    }
                ],
                "partner": {
                    "id": 17,
                    "username": "13544445555",
                    "rank": 1,
                    "contact_name": "31232131",
                    "contact_wang": "",
                    "contact_qq": "111",
                    "contact_qq2": "abcdafa",
                    "contact_mobile": "13514785698",
                    "contact_email": "",
                    "sale_admin_id": 0,
                    "buyer_admin_id": 111,
                    "alipay_account": "111",
                    "alipay_name": "111",
                    "bank_province": "7",
                    "bank_city": "412",
                    "bank_name": "中国建设银行",
                    "bank_sub_name": "111",
                    "bank_user": "111",
                    "bank_no": "111",
                    "delivery_province_id": 2,
                    "delivery_city_id": 8892,
                    "account_type": 1,
                    "exemption": null,
                    "auth_status": 2,
                    "auth_message": "",
                    "auth_admin_id": 1,
                    "auth_at": 1437707966,
                    "is_liquidate": 0,
                    "liquidate_at": 0,
                    "create_at": "1444376947",
                    "update_at": "1444376947",
                    "delete_at": 0,
                    "is_overseas": 0,
                    "title": "布袋测试的商家"
                },
                "partner_brand": {
                    "id": 17,
                    "title": "伊曼莎",
                    "license_type": "sole",
                    "begin_date": 1435680000,
                    "end_date": 1435680000,
                    "fee_rate": -1,
                    "audit_admin_id": 0,
                    "audit_status": 0,
                    "audit_reson": "",
                    "audit_at": 0,
                    "delete_admin_id": 0,
                    "update_at": null,
                    "delete_at": 0,
                    "age_range": "3",
                    "sex_range": 1,
                    "remark": "",
                    "remark_admin_id": 0,
                    "brand_level": 0,
                    "partner_id": 17,
                    "brand_id": 2,
                    "registr_image": 81,
                    "brand_image": 82,
                    "other_image": 83,
                    "create_at": null
                },
                "event_status": [
                    {
                        "id": 216,
                        "step": "one",
                        "status": 1,
                        "admin_id": 250,
                        "event_id": 150,
                        "remark": "",
                        "create_at": "1444702762"
                    },
                    {
                        "id": 217,
                        "step": "two",
                        "status": 1,
                        "admin_id": 250,
                        "event_id": 150,
                        "remark": "",
                        "create_at": "1444703276"
                    },
                    {
                        "id": 218,
                        "step": "three",
                        "status": 1,
                        "admin_id": 250,
                        "event_id": 150,
                        "remark": "0",
                        "create_at": "1444703318"
                    },
                    {
                        "id": 219,
                        "step": "four",
                        "status": 1,
                        "admin_id": 250,
                        "event_id": 150,
                        "remark": "0",
                        "create_at": "1444703571"
                    },
                    {
                        "id": 221,
                        "step": "five",
                        "status": 1,
                        "admin_id": 250,
                        "event_id": 150,
                        "remark": "0",
                        "create_at": "1444703831"
                    }
                ],
                "event_remark": [],
                "preview_url": "http://www.lamahui.loc",
                "partner_title": "布袋测试的商家",
                "brand_title": "伊曼莎",
                "remarks": "0",
                "notes": "",
                "img_url": "http://img.test.lamahui.com/static/images/2015/10/13/f6cc8a9f5f34ecaea1c18e2d8111be087293.jpg",
                "total_item_official": 6,
                "total_item": 6
            }
        ],
        "total_count": 1
    }
}
```
#专场列表页-已下线列表
1.请求地址
```
/event/list
```
2.请求参数
```
ajax:1
page:1
page_size:20
id:
title:
brand_title:
partner_title:
event_status:4
begin_time:
end_time:
```

3.返回结果
```
{
    "errorcode": 0,
    "datatable": {
        "list": [
            {
                "id": 142,
                "title": "阿萨德",
                "sales_title": "",
                "url_key": "",
                "discount_word": "",
                "is_recommend": 0,
                "channel_ids": "",
                "seo_title": "",
                "seo_keywords": "",
                "seo_description": "",
                "begin_at": "2015-08-04 00:00",
                "end_at": "2015-08-06 00:00",
                "sort_num": 0,
                "show_goods": 0,
                "update_at": "1438671009",
                "delete_at": 0,
                "is_delay": 1,
                "image_logo_id": 0,
                "image_pc_banner_id": 124,
                "image_pc_small_id": 124,
                "image_app_banner_id": 124,
                "image_app_big_id": 128,
                "image_app_small_id": 124,
                "brand_id": 40,
                "image_banner_id": 0,
                "partner_brand_id": null,
                "partner_id": 29,
                "platform_id": 0,
                "status": 1,
                "remark": "",
                "create_at": "2015-08-04 14:13:15",
                "event_item": [
                    {
                        "id": 121435,
                        "event_id": 142,
                        "sort_num": 1,
                        "create_at": "0",
                        "update_at": "1438669230",
                        "delete_at": 0,
                        "item_id": 20000267,
                        "item_detail": {
                            "id": 20000267,
                            "title": "乔丹男鞋运动鞋男跑步鞋男春春正品轻便透气减震休闲鞋XM3320307",
                            "sales_title": "史蒂夫",
                            "market_price": "279.00",
                            "sales_price": "129.00",
                            "supply_price": "101.91",
                            "taobao_seller_id": 0,
                            "is_buy_change": 0,
                            "postage_tpl_id": 0,
                            "source_platform": "",
                            "source_id": "0",
                            "click_url": "",
                            "intended_population": "771,774",
                            "stock": 48,
                            "status": -2,
                            "is_able_apply": 1,
                            "create_at": "1438656472",
                            "update_at": "1439278003",
                            "delete_at": 0,
                            "brand_id": 40,
                            "cate1_id": 341,
                            "cate2_id": 342,
                            "cate3_id": 0,
                            "partner_id": 29,
                            "item_type_id": 1,
                            "is_overseas": 0,
                            "image_id1": 125,
                            "image_id2": 0,
                            "website": ""
                        }
                    }
                ],
                "partner": {
                    "id": 29,
                    "username": "15868164621",
                    "rank": 1,
                    "contact_name": "大撒风",
                    "contact_wang": "",
                    "contact_qq": "34234234",
                    "contact_qq2": "",
                    "contact_mobile": "15868134567",
                    "contact_email": "",
                    "sale_admin_id": 0,
                    "buyer_admin_id": 0,
                    "alipay_account": "",
                    "alipay_name": "",
                    "bank_province": "1",
                    "bank_city": "8893",
                    "bank_name": "中国工商银行",
                    "bank_sub_name": "阿杜舒服",
                    "bank_user": "阿萨德发",
                    "bank_no": "662",
                    "delivery_province_id": 1,
                    "delivery_city_id": 8893,
                    "account_type": 1,
                    "exemption": null,
                    "auth_status": 2,
                    "auth_message": "",
                    "auth_admin_id": 1,
                    "auth_at": 1438653975,
                    "is_liquidate": 0,
                    "liquidate_at": 0,
                    "create_at": "1438653922",
                    "update_at": "1444628995",
                    "delete_at": 0,
                    "is_overseas": 0,
                    "title": "大法师地方"
                },
                "partner_brand": {
                    "id": 40,
                    "title": "多力",
                    "license_type": "sole",
                    "begin_date": 1438531200,
                    "end_date": 1440950400,
                    "fee_rate": -1,
                    "audit_admin_id": 0,
                    "audit_status": 0,
                    "audit_reson": "",
                    "audit_at": 0,
                    "delete_admin_id": 0,
                    "update_at": "0",
                    "delete_at": 0,
                    "age_range": "1",
                    "sex_range": 0,
                    "remark": "",
                    "remark_admin_id": 0,
                    "brand_level": 0,
                    "partner_id": 29,
                    "brand_id": 5,
                    "registr_image": 124,
                    "brand_image": 124,
                    "other_image": 124,
                    "create_at": "1438583345"
                },
                "event_status": [
                    {
                        "id": 142,
                        "step": "one",
                        "status": 1,
                        "admin_id": 1,
                        "event_id": 142,
                        "remark": "",
                        "create_at": "1438670884"
                    },
                    {
                        "id": 143,
                        "step": "two",
                        "status": 1,
                        "admin_id": 1,
                        "event_id": 142,
                        "remark": "",
                        "create_at": "1438670928"
                    },
                    {
                        "id": 144,
                        "step": "three",
                        "status": 1,
                        "admin_id": 1,
                        "event_id": 142,
                        "remark": "0",
                        "create_at": "1438671009"
                    }
                ],
                "event_remark": [
                    {
                        "id": 4,
                        "event_id": 142,
                        "admin_id": 86,
                        "content": "礼拜三",
                        "create_at": "1438703365",
                        "update_at": "0",
                        "delete_at": 0,
                        "admin": null
                    }
                ],
                "preview_url": "http://www.lamahui.loc",
                "partner_title": "大法师地方",
                "brand_title": "多力",
                "remarks": "0",
                "notes": ": 礼拜三<br />",
                "img_url": "http://img.test.lamahui.com/static/images/2015/08/03/93fb45c45a1550d40aade0d304018b068281.png",
                "total_item_official": 1,
                "total_item": 1
                }
        ],
        "total_count": 1
    }
}
```
#专场列表页-未通过列表
1.请求地址
```
/event/list
```
2.请求参数
```
ajax:1
page:1
page_size:20
id:
title:
brand_title:
partner_title:
event_status:5
begin_time:
end_time:
```

3.返回结果
```
{
    "errorcode": 0,
    "datatable": {
        "list": [
            {
                "id": 121,
                "title": "11212312",
                "sales_title": "",
                "url_key": "",
                "discount_word": "",
                "is_recommend": 0,
                "channel_ids": "",
                "seo_title": "",
                "seo_keywords": "",
                "seo_description": "",
                "begin_at": "1970-01-01 08:00",
                "end_at": "1970-01-01 08:00",
                "sort_num": 0,
                "show_goods": 0,
                "update_at": "1444717650",
                "delete_at": 0,
                "is_delay": 1,
                "image_logo_id": 0,
                "image_pc_banner_id": 50,
                "image_pc_small_id": 50,
                "image_app_banner_id": 50,
                "image_app_big_id": 50,
                "image_app_small_id": 50,
                "brand_id": 16,
                "image_banner_id": 0,
                "partner_brand_id": 0,
                "partner_id": 17,
                "platform_id": 0,
                "status": -2,
                "remark": "",
                "create_at": "2015-07-20 19:52:22",
                "event_item": [],
                "partner": {
                    "id": 17,
                    "username": "13544445555",
                    "rank": 1,
                    "contact_name": "31232131",
                    "contact_wang": "",
                    "contact_qq": "111",
                    "contact_qq2": "abcdafa",
                    "contact_mobile": "13514785698",
                    "contact_email": "",
                    "sale_admin_id": 0,
                    "buyer_admin_id": 111,
                    "alipay_account": "111",
                    "alipay_name": "111",
                    "bank_province": "7",
                    "bank_city": "412",
                    "bank_name": "中国建设银行",
                    "bank_sub_name": "111",
                    "bank_user": "111",
                    "bank_no": "111",
                    "delivery_province_id": 2,
                    "delivery_city_id": 8892,
                    "account_type": 1,
                    "exemption": null,
                    "auth_status": 2,
                    "auth_message": "",
                    "auth_admin_id": 1,
                    "auth_at": 1437707966,
                    "is_liquidate": 0,
                    "liquidate_at": 0,
                    "create_at": "1444376947",
                    "update_at": "1444376947",
                    "delete_at": 0,
                    "is_overseas": 0,
                    "title": "布袋测试的商家"
                },
                "partner_brand": {
                    "id": 16,
                    "title": "贝亲",
                    "license_type": "sole",
                    "begin_date": 1435766400,
                    "end_date": 1436371200,
                    "fee_rate": -1,
                    "audit_admin_id": 0,
                    "audit_status": 0,
                    "audit_reson": "",
                    "audit_at": 0,
                    "delete_admin_id": 0,
                    "update_at": null,
                    "delete_at": 0,
                    "age_range": "2",
                    "sex_range": 1,
                    "remark": "",
                    "remark_admin_id": 0,
                    "brand_level": 0,
                    "partner_id": 17,
                    "brand_id": 1,
                    "registr_image": 50,
                    "brand_image": 50,
                    "other_image": 50,
                    "create_at": null
                },
                "event_status": [
                    {
                        "id": 225,
                        "step": "one",
                        "status": -2,
                        "admin_id": 331,
                        "event_id": 121,
                        "remark": "图片不清晰",
                        "create_at": "1444717650"
                    }
                ],
                "event_remark": [],
                "preview_url": "http://www.lamahui.loc",
                "partner_title": "布袋测试的商家",
                "brand_title": "贝亲",
                "remarks": "图片不清晰",
                "notes": "",
                "img_url": "http://img.test.lamahui.com/static/images/2015/06/24/73bce5a79cbb466c731b37caca31bef42340.gif",
                "total_item_official": 0,
                "total_item": 0
          }
        ],
        "total_count": 1
    }
}
```
#专场列表页-未提交列表
1.请求地址
```
/event/list
```
2.请求参数
```
ajax:1
page:1
page_size:20
id:
title:
brand_title:
partner_title:
event_status:6
begin_time:
end_time:
```

3.返回结果
```
{
    "errorcode": 0,
    "datatable": {
        "list": [
            {
                "id": 153,
                "title": "1212",
                "sales_title": "",
                "url_key": "",
                "discount_word": "",
                "is_recommend": 0,
                "channel_ids": "",
                "seo_title": "",
                "seo_keywords": "",
                "seo_description": "",
                "begin_at": "1970-01-01 08:00",
                "end_at": "1970-01-01 08:00",
                "sort_num": 0,
                "show_goods": 0,
                "update_at": "0",
                "delete_at": 0,
                "is_delay": 1,
                "image_logo_id": 0,
                "image_pc_banner_id": 5583,
                "image_pc_small_id": 5580,
                "image_app_banner_id": 5586,
                "image_app_big_id": 5584,
                "image_app_small_id": 5585,
                "brand_id": 17,
                "image_banner_id": 0,
                "partner_brand_id": null,
                "partner_id": 17,
                "platform_id": 0,
                "status": -1,
                "remark": "",
                "create_at": "2015-10-13 16:58:19",
                "event_item": [],
                "partner": {
                    "id": 17,
                    "username": "13544445555",
                    "rank": 1,
                    "contact_name": "31232131",
                    "contact_wang": "",
                    "contact_qq": "111",
                    "contact_qq2": "abcdafa",
                    "contact_mobile": "13514785698",
                    "contact_email": "",
                    "sale_admin_id": 0,
                    "buyer_admin_id": 111,
                    "alipay_account": "111",
                    "alipay_name": "111",
                    "bank_province": "7",
                    "bank_city": "412",
                    "bank_name": "中国建设银行",
                    "bank_sub_name": "111",
                    "bank_user": "111",
                    "bank_no": "111",
                    "delivery_province_id": 2,
                    "delivery_city_id": 8892,
                    "account_type": 1,
                    "exemption": null,
                    "auth_status": 2,
                    "auth_message": "",
                    "auth_admin_id": 1,
                    "auth_at": 1437707966,
                    "is_liquidate": 0,
                    "liquidate_at": 0,
                    "create_at": "1444376947",
                    "update_at": "1444376947",
                    "delete_at": 0,
                    "is_overseas": 0,
                    "title": "布袋测试的商家"
                },
                "partner_brand": {
                    "id": 17,
                    "title": "伊曼莎",
                    "license_type": "sole",
                    "begin_date": 1435680000,
                    "end_date": 1435680000,
                    "fee_rate": -1,
                    "audit_admin_id": 0,
                    "audit_status": 0,
                    "audit_reson": "",
                    "audit_at": 0,
                    "delete_admin_id": 0,
                    "update_at": null,
                    "delete_at": 0,
                    "age_range": "3",
                    "sex_range": 1,
                    "remark": "",
                    "remark_admin_id": 0,
                    "brand_level": 0,
                    "partner_id": 17,
                    "brand_id": 2,
                    "registr_image": 81,
                    "brand_image": 82,
                    "other_image": 83,
                    "create_at": null
                },
                "event_status": [],
                "event_remark": [],
                "preview_url": "http://www.lamahui.loc",
                "partner_title": "布袋测试的商家",
                "brand_title": "伊曼莎",
                "remarks": "",
                "notes": "",
                "img_url": "http://img.test.lamahui.com/static/images/2015/10/13/ee86011dc5b992952cefbcb51686b4a43768.png",
                "total_item_official": 0,
                "total_item": 0
            }
          ],
        "total_count": 1
    }
}
```
#专场搜索
1.请求地址
```
/event/list
```
2.请求参数
```
ajax:1
page:1
page_size:20
id:153
title:
brand_title:
partner_title:
event_status:0(审核列表），1（审核排期），2（待上线），3（上线中），4（已下线），5（未通过），6（未提交）
begin_time:
end_time:
```
3.返回结果 
```
{
    "errorcode": 0,
    "datatable": {
        "list": [
            {
                "id": 153,
                "title": "1212",
                "sales_title": "",
                "url_key": "",
                "discount_word": "",
                "is_recommend": 0,
                "channel_ids": "",
                "seo_title": "",
                "seo_keywords": "",
                "seo_description": "",
                "begin_at": "1970-01-01 08:00",
                "end_at": "1970-01-01 08:00",
                "sort_num": 0,
                "show_goods": 0,
                "update_at": "0",
                "delete_at": 0,
                "is_delay": 1,
                "image_logo_id": 0,
                "image_pc_banner_id": 5583,
                "image_pc_small_id": 5580,
                "image_app_banner_id": 5586,
                "image_app_big_id": 5584,
                "image_app_small_id": 5585,
                "brand_id": 17,
                "image_banner_id": 0,
                "partner_brand_id": null,
                "partner_id": 17,
                "platform_id": 0,
                "status": -1,
                "remark": "",
                "create_at": "2015-10-13 16:58:19",
                "event_item": [],
                "partner": {
                    "id": 17,
                    "username": "13544445555",
                    "rank": 1,
                    "contact_name": "31232131",
                    "contact_wang": "",
                    "contact_qq": "111",
                    "contact_qq2": "abcdafa",
                    "contact_mobile": "13514785698",
                    "contact_email": "",
                    "sale_admin_id": 0,
                    "buyer_admin_id": 111,
                    "alipay_account": "111",
                    "alipay_name": "111",
                    "bank_province": "7",
                    "bank_city": "412",
                    "bank_name": "中国建设银行",
                    "bank_sub_name": "111",
                    "bank_user": "111",
                    "bank_no": "111",
                    "delivery_province_id": 2,
                    "delivery_city_id": 8892,
                    "account_type": 1,
                    "exemption": null,
                    "auth_status": 2,
                    "auth_message": "",
                    "auth_admin_id": 1,
                    "auth_at": 1437707966,
                    "is_liquidate": 0,
                    "liquidate_at": 0,
                    "create_at": "1444376947",
                    "update_at": "1444376947",
                    "delete_at": 0,
                    "is_overseas": 0,
                    "title": "布袋测试的商家"
                },
                "partner_brand": {
                    "id": 17,
                    "title": "伊曼莎",
                    "license_type": "sole",
                    "begin_date": 1435680000,
                    "end_date": 1435680000,
                    "fee_rate": -1,
                    "audit_admin_id": 0,
                    "audit_status": 0,
                    "audit_reson": "",
                    "audit_at": 0,
                    "delete_admin_id": 0,
                    "update_at": null,
                    "delete_at": 0,
                    "age_range": "3",
                    "sex_range": 1,
                    "remark": "",
                    "remark_admin_id": 0,
                    "brand_level": 0,
                    "partner_id": 17,
                    "brand_id": 2,
                    "registr_image": 81,
                    "brand_image": 82,
                    "other_image": 83,
                    "create_at": null
                },
                "event_status": [],
                "event_remark": [],
                "preview_url": "http://www.lamahui.loc",
                "partner_title": "布袋测试的商家",
                "brand_title": "伊曼莎",
                "remarks": "",
                "notes": "",
                "img_url": "http://img.test.lamahui.com/static/images/2015/10/13/ee86011dc5b992952cefbcb51686b4a43768.png",
                "total_item_official": 0,
                "total_item": 0
            }
          ],
        "total_count": 1
    }
}
```
#审核
#商家审核-审核通过
1.请求地址
```
/event/audit'
```

2.请求参数
```
status:1
remark:
event_id:117
status_kind:one
```

3.返回结果
```
{
    "errorcode": 0,
    "message": "操作成功"
}
```
#商家审核-审核不通过
1.请求地址
```
/event/audit'
```

2.请求参数
```
status:-2
remark:的典范
event_id:115
status_kind:one
```

3.返回结果
```
{
    "errorcode": 0,
    "message": "操作成功"
}
```
#审核-添加审核备注
1.请求地址
```
/event/note
```

2.请求参数
```
remark:二二得
event_id:110
```

3.返回结果
```
{
    "errorcode": 0,
    "message": "操作成功"
}
```

#修改排期
1.请求地址
```
event/remark?event_id=121
```
2.请求参数
```
event_id:120
```

3.返回结果
```
{
    "errorcode": 0,
    "datatable": {
        "list": [
            {
                "name": "郭圣",
                "remark": "",
                "create_at": "2015-10-13 16:40:30"
            }
        ],
        "total_count": 1
    }
}
```
#专场编辑页面
1.请求地址
```
/event/item?event_id=114
```
2.请求参数
```
ajax:1
page:1
page_size:20
title:%E5%9C%B0%E6%96%B9%E6%92%92%E6%97%A6
image_id1:%2Fstatic%2Fimages%2F2015%2F07%2F13%2Fc451553cafc1d836c5efbf19774aa2448196.jpg
image_id2:%2Fstatic%2Fimages%2F2015%2F07%2F13%2Fc451553cafc1d836c5efbf19774aa2448196.jpg
image_id3:%2Fstatic%2Fimages%2F2015%2F07%2F13%2Fc451553cafc1d836c5efbf19774aa2448196.jpg
image_id4:%2Fstatic%2Fimages%2F2015%2F07%2F13%2Fc451553cafc1d836c5efbf19774aa2448196.jpg
image_id5:
```
3.返回结果
```
{
    "errorcode": 0,
    "datatable": {
        "list": [],
        "total_count": 0
    }
}
```
#专场编辑页面上传图片
1.请求地址
```
/item/upload
```
2.请求参数
```
{
}
```
3.返回结果
```
{
    "errorcode": 1,
    "message": "图片尺寸不符合要求,请上传(720*290)的图片"

}
```










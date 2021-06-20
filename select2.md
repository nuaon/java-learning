## select2

```javascript
$(".select2").select2({language:"zh-CN"});
```



select2 AJAX获取数据

```javascript
$("#1_search_company_id").select2({
    language:"zh-CN",
    ajax: {
        url: "/company/search",
        dataType: 'json',
        delay: 250,
        data: function (params) {
            return {
                keyword: params.term,
            };
        },
        processResults: function (data) {
            var list = data.data.list;
            var dataList = new Array;
            for(var i = 0; i < list.length; i++) {
                dataList.push({id: list[i].id, text: list[i].name});
            }
            return {
                results: dataList
            };
        },
        cache: true
    },
    escapeMarkup: function (markup) {
        return markup;
    },
    minimumInputLength: 1
});
```


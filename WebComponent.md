[Home](README.md)

網頁 Chart 元件 Web Chart<br>[Htlm Emmet](https://codertw.com/%E8%BB%9F%E9%AB%94%E9%96%8B%E7%99%BC%E5%B7%A5%E5%85%B7/21517/)<br>[bootstrap4 Gride](https://www.quackit.com/bootstrap/bootstrap_4/tutorial/bootstrap_grid_system.cfm)<br>(Ajax VS Fetch)[https://eyesofkids.gitbooks.io/javascript-start-from-es6/content/part4/ajax_fetch.html]<br>[jqueryDataTable](https://datatables.net/)<br>[plotjs](https://plotly.com/graphing-libraries/)<br>[chartjs](https://www.chartjs.org/samples/latest/)<br>

網頁基本架構<br>![架構示意](img/WebStruct.png)




``` javascript
async function queryData(url) {

        const retData = await fetch(url).then((response) => {

            return response.json();
        }).then((jsonData) => {

            objectData = jsonData;
            return objectData;
        }).catch((err) => {
            console.log('錯誤:', err);
        });

        console.log('retData:', objectData);
        return retData;

    }; 

```
利用 Fetch 取得資料
``` javascript
async function GetTable() {

        const URL = "http://127.0.0.1:8080/json/split";
        const req = new Request(URL, {
            method: 'GET',
            cache: 'reload'
        });

        const objData = await queryData(req);
        var icols = []
        
        console.log('columns:', objData.columns);

        $.each(objData.columns, function (index, val) {
            icols.push({
                title: val
            })

        });
        
        
 if ($.fn.DataTable.isDataTable('#dfGroupYield')) {
            $('#dfGroupYield').DataTable().destroy();
            $('#dfGroupYield').empty();
        };
        
```

``` html
  

 $('#dfGroupYield').DataTable({
            dom: "<'row'<'col-sm-12 col-md-4'l><'col-sm-12 col-md-6'f><'col-sm-12 col-md-2'B>>" +
                "<'row'<'col-sm-12'tr>>" +
                "<'row'<'col-sm-12 col-md-4'i><'col-sm-12 col-md-8'p>>",
            "destroy": true,
            buttons: ['excel', 'copy'],
            data: objData.data,
            columns: icols,
            "clear": true,
            iDisplayLength: 50,

        });
``` 

# Grafana Plugins - Phlowchart

![img](Phlowchart_icon.png)

*20 June 2022. Update: 2022/07/28.*

* [用途](#use)

* [安裝方式、有無支援 ElasticSearch](#install)

* [圖表產出教學](#teach)

* [所需資料格式介紹](#data)

<h2 id="use">用途</h2>

可用於從有向圖數據中呈現交互式流程圖。該面板依賴於 Infinity 數據源插件。

<h2 id="install">安裝方式、有無支援 ElasticSearch</h2>

搜尋 Grafana Plugins 中的 Phlowchart 並點擊 INSTALL 或打以下指令

    grafana-cli plugins install philipsgis-phlowchart-panel

無支援 ES，只支援 Infinity

<h2 id="teach">圖表產出教學</h2>

(1) 首先下載 Infinity 插件，並在 datasource 中加入此插件(但不用做任何設定)

![img](Phlowchart_install.png)

![img](Phlowchart_datasource.png)

(2) 進入dashboard，選擇 Infinity，並設定 Type 為 json 及 Source 為 inline 或是將 Source 定為 url 將官方範例文件的 edges 與 nodes json 貼到 grafana

![](Phlowchart_setting.png)

官方範例文件

[edges](https://raw.githubusercontent.com/philips-labs/grafana-bpm-plugin/main/sample_data/edges.json)
[nodes](https://raw.githubusercontent.com/philips-labs/grafana-bpm-plugin/main/sample_data/nodes.json)

(3) 將 Standard option 中的 unit 設定為 number，圖表即會呈現出來

![img](Phlowchart_setting(2).png)

![img](Phlowchart_sample.png)

<h2 id="data">所需資料格式介紹</h2>

參考官方說明 [reference](https://grafana.com/grafana/plugins/philipsgis-phlowchart-panel/)

```json

[
   {
      "id": "1",
      "type": "twoTextFourNumber",
      "title": "Vertex title 1",
      "sub_text": "Vertex sub text 1",
      "number1": 80,
      "number2": 45,
      "number3": 39,
      "number4": 4,
      "url": "http://www.domain.com/path/subpath/1"
   },
   {
      "id": "2",
      "type": "twoTextTwoNumber",
      "title": "Vertex title 2",
      "sub_text": "Vertex sub text 2",
      "number1": 116,
      "number2": 5,
      "number3": null,
      "number4": null,
      "url": "http://www.domain.com/path/subpath/2"
   },
   {
      "id": "3",
      "type": "oneTextThreeNumber",
      "title": "Vertex title 3",
      "sub_text": null,
      "number1": 93,
      "number2": 44,
      "number3": 32,
      "number4": null,
      "url": "http://www.domain.com/path/subpath/3"
   }
]

```

| Attribute Name | Type | Description |
|----|----|----|
| id | string | 頂點的唯一標識符。在定義連接有向圖頂點的邊時，此標識符用作源屬性和目標屬性。 |
| type | string | 這是頂點最重要的屬性。它定義瞭如何渲染特定的頂點。 |
| title | string | 此屬性指定頂點的主要文本。 |
| sub_text | string | 此屬性指定頂點的輔助文本。 |
| number1 | number | 此屬性指定頂點的第一個編號。 |
| number2 | number | 此屬性指定頂點的第二個編號。 |
| number3 | number | 此屬性指定頂點的第三個編號。 |
| number4 | number | 此屬性指定頂點的第四個編號。 |
| url | string | 該屬性將包含用戶在點擊頂點時將被定向到的 URL。 |


```json

[
   {
      "id": "1-2",
      "source": "1",
      "target": "2"
   },
   {
      "id": "2-3",
      "source": "2",
      "target": "3"
   }
]

```

| Attribute Name | Type | Description |
|----|----|----|
| id | string | 邊的唯一標識符。這必須是邊緣集合中的唯一值。 |
| source | string | 作為邊源的頂點的"id"屬性。箭頭連接器將從源頂點流向目標頂點。 |
| target | string | 作為邊緣目標的頂點的"id"屬性。箭頭連接器將從源頂點流向目標頂點。|

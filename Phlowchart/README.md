# Grafana Plugins - Phlowchart

![img](Phlowchart_icon.png)

*20 June 2022. Update: 2022/07/28.*

* [用途](#use)

* [安裝方式、有無支援 ElasticSearch](#install)

* [圖表產出教學](#teach)

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

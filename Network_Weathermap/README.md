# Grafana Plugins - Network Weathermap

![img](Network_Weathermap_icon.png)

*20 June 2022. Update: 2022/07/25.*

* [用途](#use)

* [安裝方式、有無支援 ElasticSearch](#install)

* [範例](#example)

* [目前研究進度](#research)

<h2 id="use">用途</h2>

網路天氣圖，顯示各網路傳輸速度與傳輸方向等

<h2 id="install">安裝方式、有無支援 ElasticSearch</h2>

建議直接在grafana套件中安裝

<h2 id="example">範例</h2>

![img](Network_Weathermap.png)

<h2 id="research">目前研究進度</h2>

[資料來源](https://github.com/StevenHsu22/Grafana/blob/plugins/Network_Weathermap/network_weather_test.csv)

設定欄位
![img](network_weather_test1.png)

在插件中選擇欄位，會出現 undefined 的數值 (待解決，由於範例是使用 Prometheus 或許是不太支持 ES)
![img](network_weather_test2.png)

[插件功能教學文件](https://github.com/StevenHsu22/Grafana/blob/plugins/Network_Weathermap/Network_Weathermap.pdf)

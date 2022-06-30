# Grafana 實作練習 - Plugins 篇

*21 June 2022. Update: 2022/06/29.*

*Grafana version : 9.0.0*

## Grafana Plugins

| Icon | Name | Icon | Name | Icon | Name |
| ---- | ---- | ---- | ---- | ---- | ---- |
| ![img](AJAX/ajax_icon.png)| [AJAX](https://github.com/StevenHsu22/Grafana/tree/plugins/AJAX)| ![img](Annotation_Panel/annotation_list_icon.png)|[Annotation Panel](https://github.com/StevenHsu22/Grafana/tree/plugins/Annotation_Panel)| ![img](Base64/base64_icon.png)|[Base64](https://github.com/StevenHsu22/Grafana/tree/plugins/Base64)|
| ![img](Boom_Theme/boom_theme_icon.png) | [Boom Theme](https://github.com/StevenHsu22/Grafana/tree/plugins/Boom_Theme) | ![img](Button/button_icon.png) | [Button](https://github.com/StevenHsu22/Grafana/tree/plugins/Button) | ![img](Calander/calendar_icon.png) | [Calander](https://github.com/StevenHsu22/Grafana/tree/plugins/Calander) |
| ![img](Clock/clock_icon.png) | [Clock](https://github.com/StevenHsu22/Grafana/tree/plugins/Clock) | ![img](Colored_SVG_Panel/colored_svg_panel_icon.png) | [Colored SVG Panel](https://github.com/StevenHsu22/Grafana/tree/plugins/Colored_SVG_Panel) | ![img](D3_Gauge/d3_gauge_icon.png) | [D3 Gauge](https://github.com/StevenHsu22/Grafana/tree/plugins/D3_Gauge) |
| ![img](Dashboard_list/dashboard_list_icon.png) | [Dashboard_list](https://github.com/StevenHsu22/Grafana/tree/plugins/Dashboard_list) | ![img](Discrete/discrete_icon.png) | [Discrete](https://github.com/StevenHsu22/Grafana/tree/plugins/Discrete) | ![img](Gantt/gantt_icon.png) | [Gantt](https://github.com/StevenHsu22/Grafana/tree/plugins/Gantt) |
| ![img](Heatmap/heatmap_icon.png) | [Heatmap](https://github.com/StevenHsu22/Grafana/tree/plugins/Heatmap) | ![img](Histogram/histogram_icon.png) | [Histogram](https://github.com/StevenHsu22/Grafana/tree/plugins/Histogram) | ![img](HTML_graphics/html_graphics_icon.png) | [HTML_graphics](https://github.com/StevenHsu22/Grafana/tree/plugins/HTML_graphics) |
| ![img](mapbox-panel/mapbox-panel_icon.png) | [mapbox-panel](https://github.com/StevenHsu22/Grafana/tree/plugins/mapbox-panel) | ![img](Mosaic/mosaic_icon.png) | [Mosaic](https://github.com/StevenHsu22/Grafana/tree/plugins/Mosaic) | ![img](Orchestra_Cities_Map/orchestra_icon.png) | [Orchestra Cities Map](https://github.com/StevenHsu22/Grafana/tree/plugins/Orchestra_Cities_Map) |
| ![img](Parity_Report/parity_report_icon.png) | [Parity Report](https://github.com/StevenHsu22/Grafana/tree/plugins/Parity_Report) | ![img](PictureIt/pictureIt_icon.png) | [PictureIt](https://github.com/StevenHsu22/Grafana/tree/plugins/PictureIt) | ![img](Polystat/polystat.png) | [Polystat](https://github.com/StevenHsu22/Grafana/tree/plugins/Polystat) |
| ![img](pyroscope-panel/pyroscope-panel_icon.png) | [pyroscope-panel](https://github.com/StevenHsu22/Grafana/tree/plugins/pyroscope-panel) | ![img](SCADAvis_Synoptic_Panel/SCADAvis_icon.png) | [SCADAvis Synoptic Panel](https://github.com/StevenHsu22/Grafana/tree/plugins/SCADAvis_Synoptic_Panel) | ![img](Service_Dependency_Graph/service_dependency_icon.png) | [Service Dependency Graph](https://github.com/StevenHsu22/Grafana/tree/plugins/Service_Dependency_Graph) |
| ![img](Singlestat/single_stat_icon.png) | [Singlestat](https://github.com/StevenHsu22/Grafana/tree/plugins/Singlestat) | ![img](Status_Panel/status_panel_icon.png) | [Status Panel](https://github.com/StevenHsu22/Grafana/tree/plugins/Status_Panel) | ![img](Text/text_icon.png) | [Text](https://github.com/StevenHsu22/Grafana/tree/plugins/Text) |
| ![img](Timepicker_Buttons_Panel/timepicker_buttons_panel_icon.png) | [Timepicker Buttons Panel](https://github.com/StevenHsu22/Grafana/tree/plugins/Timepicker_Buttons_Panel) | ![img](Track_Map/track_map_icon.png) | [Track Map](https://github.com/StevenHsu22/Grafana/tree/plugins/Track_Map) | ![img](TrafficLight/trafficlight_icon.png) | [TrafficLight](https://github.com/StevenHsu22/Grafana/tree/plugins/TrafficLight) |
| ![img](Untimely/untimely_icon.png) | [Untimely](https://github.com/StevenHsu22/Grafana/tree/plugins/Untimely) | ![img](Website_Navigation/website_navigation_icon.png) | [Website Navigation](https://github.com/StevenHsu22/Grafana/tree/plugins/Website_Navigation) |  |  |
| ![img](Annotations_list/Annotations_list_icon.png) | [Annotations_list](https://github.com/StevenHsu22/Grafana/tree/plugins/Annotations_list) | ![img](Bar_chart/bar_chart_icon.png) | [Bar_chart](https://github.com/StevenHsu22/Grafana/tree/plugins/Bar_chart) | ![img](Bar_gauge/Bar_gauge_icon.png) | [Bar_gauge](https://github.com/StevenHsu22/Grafana/tree/plugins/Bar_gauge) |
| ![img](Candlestick/Candlestick_icon.png) | [Candlestick](https://github.com/StevenHsu22/Grafana/tree/plugins/Candlestick) | ![img](Canvas/canvas_icon.png) | [Canvas](https://github.com/StevenHsu22/Grafana/tree/plugins/Canvas) | ![img](Debug/debug_icon.png) | [Debug](https://github.com/StevenHsu22/Grafana/tree/plugins/Debug) |
| ![img](Gauge/Gauge_icon.png) | [Gauge](https://github.com/StevenHsu22/Grafana/tree/plugins/Gauge) | ![img](Geomap/geomap_icon.png) | [Geomap](https://github.com/StevenHsu22/Grafana/tree/plugins/Geomap) | ![img](Heatmap_new/heatmap_new_icon.png) | [Heatmap_new](https://github.com/StevenHsu22/Grafana/tree/plugins/Heatmap_new) |
| ![img](Histogram_Labs/Histogram_labs_icon.png) | [Histogram_Labs](https://github.com/StevenHsu22/Grafana/tree/plugins/Histogram_Labs) | ![img](Network_Weathermap/Network_Weathermap_icon.png) | [Network_Weathermap](https://github.com/StevenHsu22/Grafana/tree/plugins/Network_Weathermap) | ![img](Time_series/Time_series_icon.png) | [Time_series](https://github.com/StevenHsu22/Grafana/tree/plugins/Time_series) |
| ![img](XY_Chart/XY_Chart.png) | [XY_Chart](https://github.com/StevenHsu22/Grafana/tree/plugins/XY_Chart) |  |  |  |  |
|  |  |  |  |  |









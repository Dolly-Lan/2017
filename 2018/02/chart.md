### vue中引用highchart

[文档](http://blog.jianshukeji.com/2017/09/use-highcharts-with-vue/)

> 需要注意的是 Highcharts 其他资源除了引入文件外，还需要额外的执行 HighchartsMore(Highcharts) 等操作（Highstock 是完全包含 Highcharts的）。

    import Highcharts from 'highcharts/highstock';
    import HighchartsMore from 'highcharts/highcharts-more';
    import HighchartsDrilldown from 'highcharts/modules/drilldown';
    import Highcharts3D from 'highcharts/highcharts-3d';
    import Highmaps from 'highcharts/modules/map';

    HighchartsMore(Highcharts)
    HighchartsDrilldown(Highcharts);
    Highcharts3D(Highcharts);
    Highmaps(Highcharts);

<template>
    <section class="chart-container">
        <el-row>
            <!-- <el-col :span="12">
                <div id="chartColumn" style="width:100%; height:400px;"></div>
            </el-col>
            <el-col :span="12">
                <div id="chartBar" style="width:100%; height:400px;"></div>
            </el-col> -->
            <el-col :span="24">
                <div id="chartLine" style="width:100%; height:800px;"></div>
            </el-col>
            <!-- <el-col :span="12">
                <div id="chartPie" style="width:100%; height:400px;"></div>
            </el-col> -->
            <!-- <el-col :span="24">
                <a href="http://echarts.baidu.com/examples.html" target="_blank" style="float: right;">more>></a>
            </el-col> -->
        </el-row>
    </section>
</template>

<script>
    import echarts from 'echarts'

    export default {
        data() {
            return {
                // chartColumn: null,
                // chartBar: null,
                chartLine: null,
                // chartPie: null
            }
        },

        methods: {
            /*drawColumnChart() {
                this.chartColumn = echarts.init(document.getElementById('chartColumn'));
                this.chartColumn.setOption({
                  title: { text: 'Column Chart' },
                  tooltip: {},
                  xAxis: {
                      data: ["衬衫", "羊毛衫", "雪纺衫", "裤子", "高跟鞋", "袜子"]
                  },
                  yAxis: {},
                  series: [{
                      name: '销量',
                      type: 'bar',
                      data: [5, 20, 36, 10, 10, 20]
                    }]
                });
            },
            drawBarChart() {
                this.chartBar = echarts.init(document.getElementById('chartBar'));
                this.chartBar.setOption({
                    title: {
                        text: 'Bar Chart',
                        subtext: '数据来自网络'
                    },
                    tooltip: {
                        trigger: 'axis',
                        axisPointer: {
                            type: 'shadow'
                        }
                    },
                    legend: {
                        data: ['2011年', '2012年']
                    },
                    grid: {
                        left: '3%',
                        right: '4%',
                        bottom: '3%',
                        containLabel: true
                    },
                    xAxis: {
                        type: 'value',
                        boundaryGap: [0, 0.01]
                    },
                    yAxis: {
                        type: 'category',
                        data: ['巴西', '印尼', '美国', '印度', '中国', '世界人口(万)']
                    },
                    series: [
                        {
                            name: '2011年',
                            type: 'bar',
                            data: [18203, 23489, 29034, 104970, 131744, 630230]
                        },
                        {
                            name: '2012年',
                            type: 'bar',
                            data: [19325, 23438, 31000, 121594, 134141, 681807]
                        }
                    ]
                });
            },*/
            drawLineChart() {
                this.chartLine = echarts.init(document.getElementById('chartLine'));
                this.chartLine.setOption({
                    title: {
                        text: '各测试项值'
                    },
                    tooltip: {
                        trigger: 'axis'
                    },
                    legend: {
                        data: ['整机', 'SOC+DDR', 'CPU_L','CPU+BM', 'GPU', 'CPU_MEM','其他指标'],
                        selected:{
                                    '整机':true,
                                    'SOC+DDR':false, 
                                    'CPU_L':false,
                                    'CPU+BM':false, 
                                    'GPU':false, 
                                    'CPU_MEM':false,
                                    '其他指标':false
                                }
                    },

                    grid: {
                        left: '3%',
                        right: '4%',
                        bottom: '3%',
                        containLabel: true
                    },
                    xAxis: {
                        type: 'category',
                        boundaryGap: false,
                        data: ['版本1', '版本2', '版本3', '版本4', '版本4.0', '版本5', '版本5.0']
                    },
                    yAxis: {
                        type: 'value'
                    },
                    series: [
                        {
                            name: '整机',
                            type: 'line',
                            stack: '总量',
                            data: [4.9, 5.3, 4.7, 8.4, 5.56, 9.89, 2.32],
                            smooth: true,  //true 为平滑曲线，false为直线
                            // itemStyle:{
                            //     normal:{
                            //         color: "#0F0" //图标颜色
                            //     }
                            // },
                            // lineStyle:{
                            //     normal:{
                            //         width:10,  //连线粗细
                            //         color: "#0F0"  //连线颜色
                            //     }
                            // },
                        },
                        {
                            name: 'SOC+DDR',
                            type: 'line',
                            stack: '总量',
                            data: [220, 182, 191, 234, 290, 330, 310],
                             smooth: true  //true 为平滑曲线，false为直线
                        },
                        {
                            name: 'CPU_L',
                            type: 'line',
                            stack: '总量',
                            data: [82, 93, 90, 93, 12, 13, 13],
                             smooth: true  //true 为平滑曲线，false为直线
                        },
                         {
                            name: 'CPU+BM',
                            type: 'line',
                            stack: '总量',
                            data: [120, 132, 101, 134, 90, 230, 210],
                             smooth: true  //true 为平滑曲线，false为直线
                        },
                        {
                            name: 'GPU',
                            type: 'line',
                            stack: '总量',
                            data: [220, 182, 191, 234, 290, 330, 310],
                             smooth: true  //true 为平滑曲线，false为直线
                        },
                        {
                            name: 'CPU_MEM',
                            type: 'line',
                            stack: '总量',
                            data: [820, 932, 901, 934, 1290, 1330, 1320],
                             smooth: true  //true 为平滑曲线，false为直线
                        },
                         {
                            name: '其他指标',
                            type: 'line',
                            stack: '总量',
                            data: [220, 182, 191, 234, 290, 330, 310],
                             smooth: true  //true 为平滑曲线，false为直线
                        },
                    ]
                });
            },
           /* drawPieChart() {
                this.chartPie = echarts.init(document.getElementById('chartPie'));
                this.chartPie.setOption({
                    title: {
                        text: 'Pie Chart',
                        subtext: '纯属虚构',
                        x: 'center'
                    },
                    tooltip: {
                        trigger: 'item',
                        formatter: "{a} <br/>{b} : {c} ({d}%)"
                    },
                    legend: {
                        orient: 'vertical',
                        left: 'left',
                        data: ['直接访问', '整机', 'SOC_DDR', '视频广告', 'CPU_L']
                    },
                    series: [
                        {
                            name: '访问来源',
                            type: 'pie',
                            radius: '55%',
                            center: ['50%', '60%'],
                            data: [
                                { value: 335, name: '直接访问' },
                                { value: 310, name: '整机' },
                                { value: 234, name: 'SOC_DDR' },
                                { value: 135, name: '视频广告' },
                                { value: 1548, name: 'CPU_L' }
                            ],
                            itemStyle: {
                                emphasis: {
                                    shadowBlur: 10,
                                    shadowOffsetX: 0,
                                    shadowColor: 'rgba(0, 0, 0, 0.5)'
                                }
                            }
                        }
                    ]
                });
            },*/
            drawCharts() {
                // this.drawColumnChart()
                // this.drawBarChart()
                this.drawLineChart()
                // this.drawPieChart()
            },
        },

        mounted: function () {
            this.drawCharts()
        },
        updated: function () {
            this.drawCharts()
        }
    }
</script>

<style scoped>
    .chart-container {
        width: 100%;
        float: left;
    }
    /*.chart div {
        height: 400px;
        float: left;
    }*/

    .el-col {
        padding: 30px 20px;
    }
</style>

<template>
  <div id="home">
    <div class="container">
      <header>中国菠萝产销对接大数据</header>
      <main class="top-data">
        <div class="t-data-left">
          <span class="title">公司+渠道+订单</span>
<<<<<<< HEAD
          <div class="china-over" ref="overlayGraph">
            <!-- <overlay-graph/>-->
          </div>
=======
          <!-- <div class="china-over" ref="overlayGraph">  -->
           <overlay-graph/>
          <!-- </div> -->
    
>>>>>>> 86ca6b698e67bc157c5bbb200619664ce4bc880c
        </div>
        <div class="t-data-center">
          <div class="t-data-center-top">
            <span class="title">全国菠萝价格行情</span>
            <div class="zhexian">
              <div class="month-quotation">
                <!-- <span class="month-title">近三十天价格行情</span> -->
                <div class="center" ref="month_quotation"></div>
              </div>
              <div class="year-quotation">
                <!-- <span class="year-title">2019年价格行情</span> -->
                <div class="center" ref="year_quotation"></div>
              </div>
            </div>
          </div>

          <div class="t-data-center-down">
            <span class="title">产地菠萝每月上市分布</span>
            <div class="purchase"></div>
            <div class="listingDistribution" ref="listingDistribution"></div>
          </div>
        </div>
        <div class="t-data-right">
          <span class="title">公司+农户+基地</span>
        </div>
      </main>
      <main class="down-data">
        <div class="down-data-main1">
          <span class="title">采购商订单发布</span>
          <div class="purchase-scroll">
            <dv-scroll-board :config="config" />
          </div>
        </div>

        <div class="down-data-main2">
          <span class="title">菠萝流通分布系统</span>
          <div class="circulation-distribution">
            <circulation-distribution/>
          </div>
        </div>
        <div class="down-data-main3">
          <span class="title">果农鲜果上市发布</span>
          <div class="fruit-growers-scroll">
            <dv-scroll-board :config="config" />
          </div>
        </div>
      </main>
    </div>
    <div ref="chart1" style="width:100%;height:376px"></div>
  </div>
</template>

<script>
import echarts from "echarts";
// import { dvScrollBoard } from '@jiaminghi/data-view'
require("../assets/map/china.json"); //引入地图
// Vue.use(dvScrollBoard)
import overlayGraph from "../components/overlayGraph.vue";
import circulationDistribution from "../components/circulationDistribution.vue";
// import Gheader from '../components/Gheader.vue';
// import Lunbo from '../components/lunbo.vue';
// import News from '../components/news.vue';
// import Guild from '../components/Guild.vue';
// import Top from '../components/reTop.vue';
// import Srt from '../components/Script.vue';
export default {
  data() {
    return {
      config: {
        // header: ['时间', '病害信息', '数量', '标段'],
        data: [
          ["2019-07-01 19:25:00", "路面危害-松散", "5", "xxxxxxx"],
          ["2019-07-02 17:25:00", "路面危害-路面油污清理", "13", "xxxxxxx"],
          ["2019-07-03 16:25:00", "交安设施-交通标志牌结构", "6", "xxxxxxx"],
          ["2019-07-04 15:25:00", "路基危害-防尘网", "2", "xxxxxxx"],
          ["2019-07-05 14:25:00", "交安设施-交通标志牌结构", "1", "xxxxxxx"],
          ["2019-07-06 13:25:00", "路面危害-松散", "3", "xxxxxxx"],
          ["2019-07-07 12:25:00", "路基危害-防尘网", "4", "xxxxxxx"],
          ["2019-07-08 11:25:00", "路面危害-路面油污清理", "2", "xxxxxxx"],
          ["2019-07-09 10:25:00", "交安设施-交通标志牌结构", "5", "xxxxxxx"],
          ["2019-07-10 09:25:00", "路基危害-防尘网", "3", "xxxxxxx"]
        ],
        index: true,
        columnWidth: [50, 170, 300],
        align: ["center"],
        rowNum: 7,
        headerBGC: "#1981f6",
        headerHeight: 45,
        oddRowBGC: "rgba(0, 44, 81, 0.8)",
        evenRowBGC: "rgba(10, 29, 50, 0.8)"
      }
    };
  },

  name: "ecahrts1",
  mounted() {
    console.log(this.$refs.chart1);
    this.initChart2();
    this.everyMonthListingDistribution();
<<<<<<< HEAD
    this.overlayGraph();
  },
  components: {
    overlayGraph,
    circulationDistribution
=======
    // this.overlayGraph()
>>>>>>> 86ca6b698e67bc157c5bbb200619664ce4bc880c
  },
  methods: {
    initChart2() {
      var base = +new Date(2016, 9, 3);
      var oneDay = 24 * 3600 * 1000;
      var valueBase = Math.random() * 300;
      var valueBase2 = Math.random() * 50;
      var data = [];
      var data2 = [];

      for (var i = 1; i < 10; i++) {
        var now = new Date((base += oneDay));
        var dayStr = [
          now.getFullYear(),
          now.getMonth() + 1,
          now.getDate()
        ].join("-");

        valueBase = Math.round((Math.random() - 0.5) * 20 + valueBase);
        valueBase <= 0 && (valueBase = Math.random() * 300);
        data.push([dayStr, valueBase]);

        valueBase2 = Math.round((Math.random() - 0.5) * 20 + valueBase2);
        valueBase2 <= 0 && (valueBase2 = Math.random() * 50);
        data2.push([dayStr, valueBase2]);
      }

      var option = {
        title: {
          text: "近三十天价格行情",
          textStyle: {
            color: "#DEF1FF",
            fontSize: 14
          } //
        },
        tooltip: {
          trigger: "axis",
          axisPointer: {
            type: "cross",
            label: {
              backgroundColor: {
                type: "linear",
                x: 0,
                y: 0,
                x2: 1,
                y2: 1,
                colorStops: [
                  {
                    offset: 0,
                    color: "#286CE9" // 0% 处的颜色
                  },
                  {
                    offset: 1,
                    color: "#01D1FF" // 100% 处的颜色
                  }
                ],
                globalCoord: false // 缺省为 false
              }
              //鼠标停留提示背景色
            }
          }
        },
        // legend: {
        //   data: [ "搜索引擎"]
        // },
        toolbox: {
          feature: {
            saveAsImage: {}
          }
        },
        grid: {
          left: "7%",
          right: "4%",
          bottom: "3%",
          containLabel: true,
          borderColor: "transparent",
          shadowColor: "blue",
          shadowBlur: 10,
          shadowOffsetX: 2,
          shadowOffsetX: 2,
          show: true
        },
        xAxis: [
          {
            name: "(日份)",
            // nameGap:20,//坐标轴名称与轴线之间的距离
            nameLocation: "start",
            type: "category",
            nameTextStyle: {
              //坐标轴名称的字体样式
              color: "#04CDF4"
            },
            axisLine: {
              //X轴（或Y轴）那条线的样式设置
              show: true,
              lineStyle: {
                color: "#5092C1",
                // width:5,
                width: 1,
                type: "solid",

                shadowColor: "blue",
                shadowBlur: 10,
                shadowOffsetX: 2,
                shadowOffsetX: 2
              }
            },
            axisPointer: {
              //鼠标移到折线点上的设置

              type: "line",
              lineStyle: {
                color: "#04CDF4"
              },
              shadowStyle: {
                color: "#04CDF4"
              }
            },
            splitArea: {
              //坐标轴在 grid 区域中的分隔区域
              // show:true,
              // areaStyle:{
              //   color:"blue",
              //   shadowColor: 'rgba(0, 0, 0, 0.5)',
              //   shadowBlur: 10
              // }
            },
            splitLine: {
              //坐标轴间隔线
              // show: true,
              // lineStyle: {
              //   // 使用深浅的间隔色
              //   color: ["blue", "green"],
              //   shadowColor: "green",
              //   shadowBlur: 10,
              //   type:'dashed'
              // }
            },
            boundaryGap: false,
            data: ["1日", "5日", "10日", "15日", "20日", "25日", "30日"]
          }
        ],
        //
        yAxis: [
          {
            splitLine: {
              //坐标轴间隔线
              show: true,
              lineStyle: {
                //   // 使用深浅的间隔色
                color: "#1C4E8A",
                shadowColor: "#1C4E8A",
                shadowBlur: 10,
                type: "solid"
              }
            },
            name: "(价格)",
            // nameGap:25,//坐标轴名称与轴线之间的距离
            type: "value",
            nameTextStyle: {
              //坐标轴名称的字体样式
              color: "#04CDF4"
            },
            nameLocation: "end",
            axisLine: {
              lineStyle: {
                width: 0,
                color: "#5092C1",
                type: "solid",
                shadowColor: "#04CDF4",
                shadowBlur: 10,
                shadowOffsetX: 2,
                shadowOffsetX: 2
              }
            }
          }
        ],
        series: [
          {
            name: "搜索引擎",
            type: "line",
            stack: "总量",
            itemStyle: {
              borderWidth: 3, //拐点边框颜色
              color: {
                type: "linear",
                x: 0,
                y: 0,
                x2: 0,
                y2: 1,
                colorStops: [
                  {
                    offset: 0,
                    color: "#04CDF4" // 0% 处的颜色
                  },
                  {
                    offset: 1,
                    color: "#0A357B" // 100% 处的颜色
                  }
                ],
                global: false // 缺省为 false
              }
            },
            lineStyle: {
              color: "#04CDF4",
              shadowColor: "#04CDF4",
              shadowBlur: 10,
              type: "solid"
            },
            label: {
              normal: {
                show: false,
                position: "top"
              }
            },
            areaStyle: { normal: {} },
            data: [20.0, 35.0, 40.0, 25.0, 25.08, 78.0, 45.0]
          }
        ]
      };
      // 基于准备好的dom，初始化echarts实例
      var monthChart = echarts.init(this.$refs.month_quotation);
      // 使用刚指定的配置项和数据显示图表。
      monthChart.setOption(option);

      // 年份
      var yearChart = echarts.init(this.$refs.year_quotation);
      // 使用刚指定的配置项和数据显示图表。
      yearChart.setOption(option);
      //增加一条折线数据
      // option.legend.data.push("win");
      // option.series.push({
      //   name: "win", // 系列名称
      //   type: "line", // 图表类型，折线图line、散点图scatter、柱状图bar、饼图pie、雷达图radar
      //   data: [112, 23, 45, 56, 233, 343, 454, 89, 343, 123, 45, 123]
      // });
      // myChart.setOption(option);
    },
    // 柱状图
    everyMonthListingDistribution() {
      let option = {
        legend: {
          right: 70, //位置
          itemWidth: 20, //图例标记的图形宽度
          itemHeight: 20
        }, //图例组件
        tooltip: {},
        dataset: {
          dimensions: ["product", "广东菠萝主义", "徐闻菠萝"],
          source: [
            {
              product: "1",

              广东菠萝主义: 85.8,
              徐闻菠萝: 93.7
            },
            {
              product: "2",
              广东菠萝主义: 73.4,
              徐闻菠萝: 55.1
            },
            {
              product: "3",

              广东菠萝主义: 65.2,
              徐闻菠萝: 82.5
            },
            {
              product: "4",

              广东菠萝主义: 53.9,
              徐闻菠萝: 39.1
            },
            {
              product: "5",

              广东菠萝主义: 85.8,
              徐闻菠萝: 93.7
            },
            {
              product: "6",
              广东菠萝主义: 73.4,
              徐闻菠萝: 55.1
            },
            {
              product: "7",

              广东菠萝主义: 65.2,
              徐闻菠萝: 82.5
            },
            {
              product: "8",

              广东菠萝主义: 53.9,
              徐闻菠萝: 39.1
            },
            {
              product: "9",

              广东菠萝主义: 85.8,
              徐闻菠萝: 93.7
            },
            {
              product: "10",
              广东菠萝主义: 73.4,
              徐闻菠萝: 55.1
            },
            {
              product: "11",

              广东菠萝主义: 65.2,
              徐闻菠萝: 82.5
            },
            {
              product: "12",

              广东菠萝主义: 53.9,
              徐闻菠萝: 39.1
            }
          ]
        },
        xAxis: {
          type: "category",
          name: "(月份)",
          // axisLabel:{
          //   show:false
          // },

          nameGap: 25, //坐标轴名称与轴线之间的距离
          nameLocation: "start",
          nameTextStyle: {
            //坐标轴名称的字体样式
            color: "#04CDF4"
          },
          axisTick: {
            //y轴刻度线
            show: true
          },
          axisLine: {
            //X轴（或Y轴）那条线的样式设置
            show: false,
            lineStyle: {
              color: "#5092C1",
              // width:5,
              width: 5,
              type: "solid",

              shadowColor: "blue",
              shadowBlur: 10,
              shadowOffsetX: 2,
              shadowOffsetX: 2
            }
          }
        },
        yAxis: {
          axisLabel: {
            //  去除y轴的数值显示
            formatter: function() {
              return "*";
            }
          },
          axisLine: {
            //X轴（或Y轴）那条线的样式设置
            show: false
          },
          axisTick: { show: true },
          splitLine: {
            //坐标轴间隔线
            show: true,
            lineStyle: {
              //   // 使用深浅的间隔色
              color: "#65C6E7",
              type: "solid",
              opacity: 0.5
            }
          },
          type: "value",

          nameTextStyle: {
            //坐标轴名称的字体样式
            color: "#04CDF4"
          },

          nameLocation: "end",
          axisLine: {
            lineStyle: {
              width: 0,
              color: "#5092C1",
              type: "solid",
              shadowColor: "#04CDF4",
              shadowBlur: 10,
              shadowOffsetX: 2,
              shadowOffsetX: 2
            }
          }
        },
        // Declare several bar series, each will be mapped
        // to a column of dataset.source by default.
        series: [
          {
            type: "bar",
            barGap: 0, //不同系列的柱间距离

            itemStyle: {
              color: new echarts.graphic.LinearGradient(0, 1, 0, 0, [
                {
                  offset: 0,
                  color: "#EC1B00"
                },
                {
                  offset: 1,
                  color: "#EB5A2F"
                }
              ])
            }
          },
          {
            type: "bar",
            barGap: 0,
            itemStyle: {
              color: new echarts.graphic.LinearGradient(0, 1, 0, 0, [
                {
                  offset: 0,
                  color: "#00ABB3"
                },
                {
                  offset: 1,
                  color: "#01F0FF"
                }
              ])
            }
          }
        ]
      };
      //
      var listingDistribution = echarts.init(this.$refs.listingDistribution);
      // 使用刚指定的配置项和数据显示图表。
      listingDistribution.setOption(option);
    },
    overlayGraph() {
      var focusing = [
        { name: "海门", value: 9 },
        { name: "鄂尔多斯", value: 12 },
        { name: "招远", value: 12 },
        { name: "舟山", value: 12 },
        { name: "齐齐哈尔", value: 14 },
        { name: "盐城", value: 15 }
      ];
      var data = [
        { name: "海门", value: 9 },
        { name: "鄂尔多斯", value: 12 },
        { name: "招远", value: 12 },
        { name: "舟山", value: 12 },
        { name: "齐齐哈尔", value: 14 },
        { name: "盐城", value: 15 },
        { name: "赤峰", value: 16 },
        { name: "青岛", value: 18 },
        { name: "乳山", value: 18 },
        { name: "金昌", value: 19 },
        { name: "泉州", value: 21 },
        { name: "莱西", value: 21 },
        { name: "日照", value: 21 },
        { name: "胶南", value: 22 },
        { name: "南通", value: 23 },
        { name: "拉萨", value: 24 },
        { name: "云浮", value: 24 },
        { name: "梅州", value: 25 },
        { name: "文登", value: 25 },
        { name: "上海", value: 25 },
        { name: "攀枝花", value: 25 },
        { name: "威海", value: 25 },
        { name: "承德", value: 25 },
        { name: "厦门", value: 26 },
        { name: "汕尾", value: 26 },
        { name: "潮州", value: 26 },
        { name: "丹东", value: 27 },
        { name: "太仓", value: 27 },
        { name: "曲靖", value: 27 },
        { name: "烟台", value: 28 },
        { name: "福州", value: 29 },
        { name: "瓦房店", value: 30 },
        { name: "即墨", value: 30 },
        { name: "抚顺", value: 31 },
        { name: "玉溪", value: 31 },
        { name: "张家口", value: 31 },
        { name: "阳泉", value: 31 },
        { name: "莱州", value: 32 },
        { name: "湖州", value: 32 },
        { name: "汕头", value: 32 },
        { name: "昆山", value: 33 },
        { name: "宁波", value: 33 },
        { name: "湛江", value: 33 },
        { name: "揭阳", value: 34 },
        { name: "荣成", value: 34 },
        { name: "连云港", value: 35 },
        { name: "葫芦岛", value: 35 },
        { name: "常熟", value: 36 },
        { name: "东莞", value: 36 },
        { name: "河源", value: 36 },
        { name: "淮安", value: 36 },
        { name: "泰州", value: 36 },
        { name: "南宁", value: 37 },
        { name: "营口", value: 37 },
        { name: "惠州", value: 37 },
        { name: "江阴", value: 37 },
        { name: "蓬莱", value: 37 },
        { name: "韶关", value: 38 },
        { name: "嘉峪关", value: 38 },
        { name: "广州", value: 38 },
        { name: "延安", value: 38 },
        { name: "太原", value: 39 },
        { name: "清远", value: 39 },
        { name: "中山", value: 39 },
        { name: "昆明", value: 39 },
        { name: "寿光", value: 40 },
        { name: "盘锦", value: 40 },
        { name: "长治", value: 41 },
        { name: "深圳", value: 41 },
        { name: "珠海", value: 42 },
        { name: "宿迁", value: 43 },
        { name: "咸阳", value: 43 },
        { name: "铜川", value: 44 },
        { name: "平度", value: 44 },
        { name: "佛山", value: 44 },
        { name: "海口", value: 44 },
        { name: "江门", value: 45 },
        { name: "章丘", value: 45 },
        { name: "肇庆", value: 46 },
        { name: "大连", value: 47 },
        { name: "临汾", value: 47 },
        { name: "吴江", value: 47 },
        { name: "石嘴山", value: 49 },
        { name: "沈阳", value: 50 },
        { name: "苏州", value: 50 },
        { name: "茂名", value: 50 },
        { name: "嘉兴", value: 51 },
        { name: "长春", value: 51 },
        { name: "胶州", value: 52 },
        { name: "银川", value: 52 },
        { name: "张家港", value: 52 },
        { name: "三门峡", value: 53 },
        { name: "锦州", value: 54 },
        { name: "南昌", value: 54 },
        { name: "柳州", value: 54 },
        { name: "三亚", value: 54 },
        { name: "自贡", value: 56 },
        { name: "吉林", value: 56 },
        { name: "阳江", value: 57 },
        { name: "泸州", value: 57 },
        { name: "西宁", value: 57 },
        { name: "宜宾", value: 58 },
        { name: "呼和浩特", value: 58 },
        { name: "成都", value: 58 },
        { name: "大同", value: 58 },
        { name: "镇江", value: 59 },
        { name: "桂林", value: 59 },
        { name: "张家界", value: 59 },
        { name: "宜兴", value: 59 },
        { name: "北海", value: 60 },
        { name: "西安", value: 61 },
        { name: "金坛", value: 62 },
        { name: "东营", value: 62 },
        { name: "牡丹江", value: 63 },
        { name: "遵义", value: 63 },
        { name: "绍兴", value: 63 },
        { name: "扬州", value: 64 },
        { name: "常州", value: 64 },
        { name: "潍坊", value: 65 },
        { name: "重庆", value: 66 },
        { name: "台州", value: 67 },
        { name: "南京", value: 67 },
        { name: "滨州", value: 70 },
        { name: "贵阳", value: 71 },
        { name: "无锡", value: 71 },
        { name: "本溪", value: 71 },
        { name: "克拉玛依", value: 72 },
        { name: "渭南", value: 72 },
        { name: "马鞍山", value: 72 },
        { name: "宝鸡", value: 72 },
        { name: "焦作", value: 75 },
        { name: "句容", value: 75 },
        { name: "北京", value: 79 },
        { name: "徐州", value: 79 },
        { name: "衡水", value: 80 },
        { name: "包头", value: 80 },
        { name: "绵阳", value: 80 },
        { name: "乌鲁木齐", value: 84 },
        { name: "枣庄", value: 84 },
        { name: "杭州", value: 84 },
        { name: "淄博", value: 85 },
        { name: "鞍山", value: 86 },
        { name: "溧阳", value: 86 },
        { name: "库尔勒", value: 86 },
        { name: "安阳", value: 90 },
        { name: "开封", value: 90 },
        { name: "济南", value: 92 },
        { name: "德阳", value: 93 },
        { name: "温州", value: 95 },
        { name: "九江", value: 96 },
        { name: "邯郸", value: 98 },
        { name: "临安", value: 99 },
        { name: "兰州", value: 99 },
        { name: "沧州", value: 100 },
        { name: "临沂", value: 103 },
        { name: "南充", value: 104 },
        { name: "天津", value: 105 },
        { name: "富阳", value: 106 },
        { name: "泰安", value: 112 },
        { name: "诸暨", value: 112 },
        { name: "郑州", value: 113 },
        { name: "哈尔滨", value: 114 },
        { name: "聊城", value: 116 },
        { name: "芜湖", value: 117 },
        { name: "唐山", value: 119 },
        { name: "平顶山", value: 119 },
        { name: "邢台", value: 119 },
        { name: "德州", value: 120 },
        { name: "济宁", value: 120 },
        { name: "荆州", value: 127 },
        { name: "宜昌", value: 130 },
        { name: "义乌", value: 132 },
        { name: "丽水", value: 133 },
        { name: "洛阳", value: 134 },
        { name: "秦皇岛", value: 136 },
        { name: "株洲", value: 143 },
        { name: "石家庄", value: 147 },
        { name: "莱芜", value: 148 },
        { name: "常德", value: 152 },
        { name: "保定", value: 153 },
        { name: "湘潭", value: 154 },
        { name: "金华", value: 157 },
        { name: "岳阳", value: 169 },
        { name: "长沙", value: 175 },
        { name: "衢州", value: 177 },
        { name: "廊坊", value: 193 },
        { name: "菏泽", value: 194 },
        { name: "合肥", value: 229 },
        { name: "武汉", value: 273 },
        { name: "大庆", value: 279 }
      ];
      var geoCoordMap = {
        海门: [121.15, 31.89],
        鄂尔多斯: [109.781327, 39.608266],
        招远: [120.38, 37.35],
        舟山: [122.207216, 29.985295],
        齐齐哈尔: [123.97, 47.33],
        盐城: [120.13, 33.38],
        赤峰: [118.87, 42.28],
        青岛: [120.33, 36.07],
        乳山: [121.52, 36.89],
        金昌: [102.188043, 38.520089],
        泉州: [118.58, 24.93],
        莱西: [120.53, 36.86],
        日照: [119.46, 35.42],
        胶南: [119.97, 35.88],
        南通: [121.05, 32.08],
        拉萨: [91.11, 29.97],
        云浮: [112.02, 22.93],
        梅州: [116.1, 24.55],
        文登: [122.05, 37.2],
        上海: [121.48, 31.22],
        攀枝花: [101.718637, 26.582347],
        威海: [122.1, 37.5],
        承德: [117.93, 40.97],
        厦门: [118.1, 24.46],
        汕尾: [115.375279, 22.786211],
        潮州: [116.63, 23.68],
        丹东: [124.37, 40.13],
        太仓: [121.1, 31.45],
        曲靖: [103.79, 25.51],
        烟台: [121.39, 37.52],
        福州: [119.3, 26.08],
        瓦房店: [121.979603, 39.627114],
        即墨: [120.45, 36.38],
        抚顺: [123.97, 41.97],
        玉溪: [102.52, 24.35],
        张家口: [114.87, 40.82],
        阳泉: [113.57, 37.85],
        莱州: [119.942327, 37.177017],
        湖州: [120.1, 30.86],
        汕头: [116.69, 23.39],
        昆山: [120.95, 31.39],
        宁波: [121.56, 29.86],
        湛江: [110.359377, 21.270708],
        揭阳: [116.35, 23.55],
        荣成: [122.41, 37.16],
        连云港: [119.16, 34.59],
        葫芦岛: [120.836932, 40.711052],
        常熟: [120.74, 31.64],
        东莞: [113.75, 23.04],
        河源: [114.68, 23.73],
        淮安: [119.15, 33.5],
        泰州: [119.9, 32.49],
        南宁: [108.33, 22.84],
        营口: [122.18, 40.65],
        惠州: [114.4, 23.09],
        江阴: [120.26, 31.91],
        蓬莱: [120.75, 37.8],
        韶关: [113.62, 24.84],
        嘉峪关: [98.289152, 39.77313],
        广州: [113.23, 23.16],
        延安: [109.47, 36.6],
        太原: [112.53, 37.87],
        清远: [113.01, 23.7],
        中山: [113.38, 22.52],
        昆明: [102.73, 25.04],
        寿光: [118.73, 36.86],
        盘锦: [122.070714, 41.119997],
        长治: [113.08, 36.18],
        深圳: [114.07, 22.62],
        珠海: [113.52, 22.3],
        宿迁: [118.3, 33.96],
        咸阳: [108.72, 34.36],
        铜川: [109.11, 35.09],
        平度: [119.97, 36.77],
        佛山: [113.11, 23.05],
        海口: [110.35, 20.02],
        江门: [113.06, 22.61],
        章丘: [117.53, 36.72],
        肇庆: [112.44, 23.05],
        大连: [121.62, 38.92],
        临汾: [111.5, 36.08],
        吴江: [120.63, 31.16],
        石嘴山: [106.39, 39.04],
        沈阳: [123.38, 41.8],
        苏州: [120.62, 31.32],
        茂名: [110.88, 21.68],
        嘉兴: [120.76, 30.77],
        长春: [125.35, 43.88],
        胶州: [120.03336, 36.264622],
        银川: [106.27, 38.47],
        张家港: [120.555821, 31.875428],
        三门峡: [111.19, 34.76],
        锦州: [121.15, 41.13],
        南昌: [115.89, 28.68],
        柳州: [109.4, 24.33],
        三亚: [109.511909, 18.252847],
        自贡: [104.778442, 29.33903],
        吉林: [126.57, 43.87],
        阳江: [111.95, 21.85],
        泸州: [105.39, 28.91],
        西宁: [101.74, 36.56],
        宜宾: [104.56, 29.77],
        呼和浩特: [111.65, 40.82],
        成都: [104.06, 30.67],
        大同: [113.3, 40.12],
        镇江: [119.44, 32.2],
        桂林: [110.28, 25.29],
        张家界: [110.479191, 29.117096],
        宜兴: [119.82, 31.36],
        北海: [109.12, 21.49],
        西安: [108.95, 34.27],
        金坛: [119.56, 31.74],
        东营: [118.49, 37.46],
        牡丹江: [129.58, 44.6],
        遵义: [106.9, 27.7],
        绍兴: [120.58, 30.01],
        扬州: [119.42, 32.39],
        常州: [119.95, 31.79],
        潍坊: [119.1, 36.62],
        重庆: [106.54, 29.59],
        台州: [121.420757, 28.656386],
        南京: [118.78, 32.04],
        滨州: [118.03, 37.36],
        贵阳: [106.71, 26.57],
        无锡: [120.29, 31.59],
        本溪: [123.73, 41.3],
        克拉玛依: [84.77, 45.59],
        渭南: [109.5, 34.52],
        马鞍山: [118.48, 31.56],
        宝鸡: [107.15, 34.38],
        焦作: [113.21, 35.24],
        句容: [119.16, 31.95],
        北京: [116.46, 39.92],
        徐州: [117.2, 34.26],
        衡水: [115.72, 37.72],
        包头: [110, 40.58],
        绵阳: [104.73, 31.48],
        乌鲁木齐: [87.68, 43.77],
        枣庄: [117.57, 34.86],
        杭州: [120.19, 30.26],
        淄博: [118.05, 36.78],
        鞍山: [122.85, 41.12],
        溧阳: [119.48, 31.43],
        库尔勒: [86.06, 41.68],
        安阳: [114.35, 36.1],
        开封: [114.35, 34.79],
        济南: [117, 36.65],
        德阳: [104.37, 31.13],
        温州: [120.65, 28.01],
        九江: [115.97, 29.71],
        邯郸: [114.47, 36.6],
        临安: [119.72, 30.23],
        兰州: [103.73, 36.03],
        沧州: [116.83, 38.33],
        临沂: [118.35, 35.05],
        南充: [106.110698, 30.837793],
        天津: [117.2, 39.13],
        富阳: [119.95, 30.07],
        泰安: [117.13, 36.18],
        诸暨: [120.23, 29.71],
        郑州: [113.65, 34.76],
        哈尔滨: [126.63, 45.75],
        聊城: [115.97, 36.45],
        芜湖: [118.38, 31.33],
        唐山: [118.02, 39.63],
        平顶山: [113.29, 33.75],
        邢台: [114.48, 37.05],
        德州: [116.29, 37.45],
        济宁: [116.59, 35.38],
        荆州: [112.239741, 30.335165],
        宜昌: [111.3, 30.7],
        义乌: [120.06, 29.32],
        丽水: [119.92, 28.45],
        洛阳: [112.44, 34.7],
        秦皇岛: [119.57, 39.95],
        株洲: [113.16, 27.83],
        石家庄: [114.48, 38.03],
        莱芜: [117.67, 36.19],
        常德: [111.69, 29.05],
        保定: [115.48, 38.85],
        湘潭: [112.91, 27.87],
        金华: [119.64, 29.12],
        岳阳: [113.09, 29.37],
        长沙: [113, 28.21],
        衢州: [118.88, 28.97],
        廊坊: [116.7, 39.53],
        菏泽: [115.480656, 35.23375],
        合肥: [117.27, 31.86],
        武汉: [114.31, 30.52],
        大庆: [125.03, 46.58]
      };

      var convertData = function(data) {
        console.log(data, "data1");
        var res = [];
        for (var i = 0; i < data.length; i++) {
          var geoCoord = geoCoordMap[data[i].name];

          if (geoCoord) {
            res.push({
              name: data[i].name,
              value: geoCoord.concat(data[i].value) //geoCoord.concat(data[i].value)连接两个或多个数组
            });
          }
        }
        console.log(res, "6587");
        return res;
      };

      var option = {
        // backgroundColor: 'trsparent',
        title: {
          // text: '全国主要城市空气质量',
          // subtext: 'data from PM25.in',
          sublink: "http://www.pm25.in",
          left: "center",
          textStyle: {
            color: "#C1CEE2"
          }
        },
        tooltip: {
          trigger: "item"
        },
        legend: {
          orient: "vertical",
          y: "bottom",
          x: "right",
          data: ["pm2.5"],
          textStyle: {
            color: "#fff"
          }
        },
        geo: {
          map: "china",
          label: {
            emphasis: {
              show: false
            }
          },
          roam: true,
          itemStyle: {
            normal: {
              areaColor: "#093983",
              borderColor: "#84B8FF"
            },
            emphasis: {
              areaColor: "#2A60BB"
            }
          }
        },
        series: [
          {
            // name: 'pm2.5',
            type: "scatter",
            coordinateSystem: "geo",
            data: convertData(data),
            symbolSize: function(val) {
              return val[2] / 10;
            },
            label: {
              normal: {
                formatter: "{b}",
                position: "right",
                show: false
              },
              emphasis: {
                show: true
              }
            },
            itemStyle: {
              normal: {
                color: "#6B8BBA"
              }
            }
          },
          {
            //
            name: "Top 5",
            type: "effectScatter",
            coordinateSystem: "geo",
            data: convertData(focusing), //热点城市设置
            symbolSize: 20, //热点大小
            effectType: "ripple",
            showEffectOn: "render",
            rippleEffect: {
              brushType: "stroke"
            },
            hoverAnimation: true,
            label: {
              normal: {
                formatter: "{b}",
                position: "right",
                show: true
              }
            },
            itemStyle: {
              normal: {
                color: "#05a9d8",
                shadowBlur: 10,
                shadowColor: "#05a7d8"
              }
            },
            zlevel: 1
          }
        ]
      };

      var overlayGraphChart =this.$echarts.init(this.$refs.overlayGraph);
      // 使用刚指定的配置项和数据显示图表。
      overlayGraphChart.setOption(option);
    }
  }
};
</script>

<style scoped>
#home {
  height: 100%;
  width: 100%;
  font-size: 0.12rem;
  box-sizing: border-box;
  background: url(../assets/img/bg.png) no-repeat center center;
  background-size: 100% 100%;
  /* overflow: hidden;  */
  position: fixed;
  top: 0;
  left: 0;
}

#home .container {
  height: 100%;
  width: 100%;
  box-sizing: border-box;
}
.container header {
  width: 100%;
  height: 100px;
  text-align: center;
  font-size: 40px;
  line-height: 70px;
  color: #7efafc;
  background: url(../assets/img/header_bg.png) no-repeat center center;
  background-size: 100% 100%;
}
.container .title {
  width: 264px;
  height: 40px;
  /* background: rgba(22, 48, 128, 1); */
  /* border: 1px solid rgba(94, 220, 255, 1); */
  font-size: 18px;
  text-align: center;
  color: rgba(222, 241, 255, 1);
  margin-top: 18px;
}
.container .top-data {
  height: 60%;
  width: 100%;
  display: flex;
  margin-bottom: 1%;
}
.top-data .t-data-left,
.top-data .t-data-center,
.top-data .t-data-right {
  /* flex: 1; */
  height: 100%;
}
.top-data .t-data-left {
  margin-left: 1%;
  width: 32%;
  display: flex;
  flex-direction: column;
  align-items: center;
  background: url(../assets/img/company_add_order.png) no-repeat center center;
  background-size: 100% 100%;
}
.t-data-left .china-over {
  height: 90%;
  width: 99%;
}
.china-over .overlay-graph {
  height: 95%;
  width: 98%;
}
.top-data .t-data-center {
  margin: 0 1%;
  width: 32%;
}
.t-data-center .t-data-center-top,
.t-data-center .t-data-center-down {
  height: 48.5%;
  width: 100%;
  display: flex;
  flex-direction: column;
  align-items: center;

  /*  */
}

.t-data-center-down .listingDistribution {
  height: 95%;
  width: 100%;
}
.t-data-center .t-data-center-top {
  /* height: 50%; */
  background: url(../assets/img/pineapple_price.png) no-repeat center center;
  background-size: 100% 100%;
  margin-bottom: 3%;
}
.t-data-center-top .zhexian {
  width: 100%;
  height: 90%;
  display: flex;
}
.t-data-center-top .zhexian .month-quotation,
.t-data-center-top .zhexian .year-quotation {
  width: 50%;
  height: 100%;
  padding-left: 22px;
  display: flex;
  flex-direction: column;
}
.month-quotation .month-title,
.year-quotation .year-title {
  width: 130px;
  height: 14px;
  font-size: 14px;
  font-weight: bold;
  color: rgba(222, 241, 255, 1);
}
.month-quotation .center,
.year-quotation .center {
  height: 92%;
  width: 100%;
}
.t-data-center .t-data-center-down {
  /* height: 50%; */
  background: url(../assets/img/Listing_distribution.png) no-repeat center
    center;
  background-size: 100% 100%;
}
.top-data .t-data-right {
  margin-right: 1%;
  width: 32%;
  background: url(../assets/img/company_farmer_base.png) no-repeat center center;
  background-size: 100% 100%;
  display: flex;
  justify-content: center;
}
.container .down-data {
  height: 35%;
  width: 100%;
  display: flex;

  /* justify-content: space-around  */
}
.down-data .down-data-main1,
.down-data .down-data-main2,
.down-data .down-data-main3 {
  width: 32%;
  height: 80%;
  margin-bottom: 1%;
  display: flex;
  flex-direction: column;
  align-items: center;
}
.down-data .down-data-main1 {
  background: url(../assets/img/order_purchar.png) no-repeat center center;
  background-size: 100% 100%;
  margin-left: 1%;
}
.down-data-main1 .purchase-scroll {
  height: 92%;
  width: 100%;
}
.down-data .down-data-main2 {
  background: url(../assets/img/circulation_distribution.png) no-repeat center
    center;
  background-size: 100% 100%;
  margin: 0 1%;
}
.down-data-main2 .circulation-distribution {
  height:92%;
  width: 98%;
}
.down-data-main3 .fruit-growers-scroll {
  height: 92%;
  width: 100%;
}
.down-data .down-data-main3 {
  background: url(../assets/img/release_purchase.png) no-repeat center center;
  background-size: 100% 100%;
  margin-right: 1%;
}
</style>
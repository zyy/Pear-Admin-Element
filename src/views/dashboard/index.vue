<template>
  <div class="dashboard-container">
    <div class="dashboard-text">
      <el-row :gutter="20">
        <el-col :span="6">
          <div class="grid-content bg-purple">
            <el-card class="box-card console-card">
              <el-row :gutter="10">
                <el-col :span="16">
                  <div class="console-card-left"></div>
                </el-col>
                <el-col :span="8">
                  <div class="console-card-right"></div>
                </el-col>
              </el-row>
            </el-card>
          </div>
        </el-col>
        <el-col :span="6">
          <div class="grid-content bg-purple">
              <el-card class="box-card console-card">
              <el-row :gutter="10">
                <el-col :span="16">
                  <div class="console-card-left"></div>
                </el-col>
                <el-col :span="8">
                  <div class="console-card-right"></div>
                </el-col>
              </el-row>
            </el-card>
          </div>
        </el-col>
        <el-col :span="6">
          <div class="grid-content bg-purple">
            <el-card class="box-card console-card">
              <el-row :gutter="10">
                <el-col :span="16">
                  <div class="console-card-left"></div>
                </el-col>
                <el-col :span="8">
                  <div class="console-card-right"></div>
                </el-col>
              </el-row>
            </el-card>
          </div>
        </el-col>
        <el-col :span="6">
          <div class="grid-content bg-purple">
             <el-card class="box-card console-card">
              <el-row :gutter="10">
                <el-col :span="16">
                  <div class="console-card-left"></div>
                </el-col>
                <el-col :span="8">
                  <div class="console-card-right"></div>
                </el-col>
              </el-row>
            </el-card>
          </div>
        </el-col>
      </el-row>
      <el-row :gutter="20">
        <el-col :span="18">
          <div class="grid-content bg-purple">
            <el-card class="box-card">
              <div id="myChart" :style="{width: '100%px', height: '350px'}"></div>
            </el-card>
          </div>
        </el-col>
        <el-col :span="6">
          <div class="grid-content bg-purple">
            <el-card class="box-card"></el-card>
          </div>
        </el-col>
      </el-row>
      <el-row :gutter="20">
        <el-col :span="18">
          <div class="grid-content bg-purple">
            <el-card class="box-card">
              <el-table :data="tableData" style="width: 100%">
                <el-table-column prop="name" label="姓名"></el-table-column>
                <el-table-column prop="province" label="省份"></el-table-column>
                <el-table-column prop="city" label="市区"></el-table-column>
                <el-table-column prop="address" label="地址"></el-table-column>
              </el-table>
            </el-card>
          </div>
        </el-col>
        <el-col :span="6">
          <div class="grid-content bg-purple">
            <el-card class="box-card"></el-card>
          </div>
        </el-col>
      </el-row>
    </div>
  </div>
</template>

<script>
import { mapGetters } from "vuex";

export default {
  name: "Dashboard",
  computed: {
    ...mapGetters(["name"])
  },
  data() {
    return {
      tableData: [
        {
          name: "王小虎",
          province: "上海",
          city: "普陀区",
          address: "上海市普陀区金沙江路"
        },
        {
          name: "王小虎",
          province: "上海",
          city: "普陀区",
          address: "上海市普陀区金沙江路"
        },
        {
          name: "王小虎",
          province: "上海",
          city: "普陀区",
          address: "上海市普陀区金沙江路"
        },
        {
          name: "王小虎",
          province: "上海",
          city: "普陀区",
          address: "上海市普陀区金沙江路"
        },
        {
          name: "王小虎",
          province: "上海",
          city: "普陀区",
          address: "上海市普陀区金沙江路"
        },
        {
          name: "王小虎",
          province: "上海",
          city: "普陀区",
          address: "上海市普陀区金沙江路"
        },
        {
          name: "王小虎",
          province: "上海",
          city: "普陀区",
          address: "上海市普陀区金沙江路"
        }
      ]
    };
  },
  mounted() {
    let echarts = this.drawLine();
  },
  methods: {
    drawLine() {
      // 基于准备好的dom，初始化echarts实例
      let myChart = this.$echarts.init(document.getElementById("myChart"));
      // 绘制图表
      myChart.setOption({
        tooltip: {
          trigger: "axis"
        },
        xAxis: [
          {
            type: "category",
            data: [
              "2019-01",
              "2019-02",
              "2019-03",
              "2019-04",
              "2019-05",
              "2019-06"
            ],
            axisLine: {
              lineStyle: {
                color: "#999"
              }
            }
          }
        ],
        yAxis: [
          {
            type: "value",
            splitNumber: 4,
            splitLine: {
              lineStyle: {
                type: "dashed",
                color: "#DDD"
              }
            },
            axisLine: {
              show: false,
              lineStyle: {
                color: "#333"
              }
            },
            nameTextStyle: {
              color: "#999"
            },
            splitArea: {
              show: false
            }
          }
        ],
        series: [
          {
            name: "课时",
            type: "line",
            data: [23, 60, 20, 36, 23, 85],
            lineStyle: {
              normal: {
                width: 8,
                color: {
                  type: "linear",

                  colorStops: [
                    {
                      offset: 0,
                      color: "#A9F387" // 0% 处的颜色
                    },
                    {
                      offset: 1,
                      color: "#48D8BF" // 100% 处的颜色
                    }
                  ],
                  globalCoord: false // 缺省为 false
                },
                shadowColor: "rgba(72,216,191, 0.3)",
                shadowBlur: 10,
                shadowOffsetY: 20
              }
            },
            itemStyle: {
              normal: {
                color: "#fff",
                borderWidth: 10,
                /*shadowColor: 'rgba(72,216,191, 0.3)',
								shadowBlur: 100,*/
                borderColor: "#A9F387"
              }
            },
            smooth: true
          }
        ]
      });
      return { myChart: myChart };
    }
  }
};
</script>
<style lang="scss" scoped>
.dashboard {
  &-container {
    margin: 20px;
  }
  &-text {
    font-size: 30px;
    line-height: 46px;
  }
}

.el-row {
  margin-bottom: 15px;
}
.console-card {
  height: 120px;
}
.console-card-left {
  border-right: #eceff9 1px solid;
  height: 80px;
  text-align: center;
  line-height: 80px;
}
.console-card-right {
  height: 80px;
}
</style>

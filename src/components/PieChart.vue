<template>
  <div class="chart-container">
    <div class="public">
      <span class="text-bold" style="color:#31318e; font-size: 2vw">40%</span>
      <span style="color:#142843">Public</span>
    </div>
    <div class="adv-con">
      <span class="text-bold" style="color:#76dfef;font-size: 2vw">20%</span>
      <span style="color:#142843">Advisors & Consultants</span>
    </div>
    <div class="kirobo">
      <span class="text-bold" style="color:#0f62b0;font-size: 2vw">15%</span>
      <span style="color:#142843">Kirobo’s Equity</span>
    </div>
    <div class="founder">
      <span class="text-bold" style="color:#009abc;font-size: 2vw">25%</span>
      <span style="color:#142843">Founder’s & Team</span>
    </div>
    <div ref="chart" :class="className" :style="{height:height,width:width}"></div>
  </div>
</template>

<script>
import echarts from "echarts";

import { debounce } from "@/utils";
export default {
  props: {
    minimized: {
      type: Boolean
    },
    className: {
      type: String,
      default: "chart"
    },
    width: {
      type: String,
      default: "100%"
    },
    height: {
      type: String,
      default: "100%"
    },
    autoResize: {
      type: Boolean,
      default: true
    },
    chartData: {
      type: Object
    }
  },
  data() {
    return {
      chart: null
    };
  },
  mounted() {
    console.log(this);
    this.initChart();
    if (this.autoResize) {
      this.__resizeHanlder = debounce(() => {
        if (this.chart) {
          console.log("this.chart", this.chart);
          this.chart.resize();
        }
      }, 0);
      window.addEventListener("resize", this.__resizeHanlder);
      console.log("this.__resizeHanlder", this.__resizeHanlder);
    }
  },
  beforeDestroy() {
    if (!this.chart) {
      return;
    }
    if (this.autoResize) {
      window.removeEventListener("resize", this.__resizeHanlder);
    }
    this.chart.dispose();
    this.chart = null;
  },

  watch: {
    protectedPrecent: {
      deep: true,
      handler(val) {
        this.setOptions(val);
      }
    }
  },
  methods: {
    setOptions() {
      let option = {
        tooltip: {
          trigger: "item",
          formatter: "{a} <br/>{b}: {d}%"
        },
        color: ["#31318e", "#0f62b0", "#009abc", "#76dfef"],
        series: [
          {
            name: "KiroboSmartWallet",
            type: "pie",
            radius: ["80%", "90%"],
            avoidLabelOverlap: true,
            // roseType: "radius",
            labelLine: {
              normal: {
                lineStyle: {
                  color: "rgba(0, 0, 0, 0.3)"
                },
                smooth: 0.2,
                length: 10,
                length2: 20
              }
            },
            animationType: "scale",
            animationEasing: "elasticOut",
            animationDelay: function(idx) {
              return Math.random() * 200;
            },
            label: {
              normal: {
                show: false,
                position: "center"
              }
            },
            labelLine: {
              normal: {
                show: true
              }
            },
            data: [
              { value: 40, name: "直接访问" },
              { value: 15, name: "邮件营销" },
              { value: 25, name: "联盟广告" },
              { value: 20, name: "视频广告" }
            ]
          }
        ]
      };

      this.chart.setOption(option);
    },
    initChart() {
      this.chart = echarts.init(this.$refs.chart);
      this.setOptions(this.chartData);
    }
  }
};
</script>

<style>
.chart-container {
  position: relative;
  font-size: 1.5vw;
  display: flex;
  margin: 100px;
  width: 31.25vw;
  height: 31.25vw;
  justify-content: center;
  align-items: center;
}
.public {
  position: absolute;
  display: flex;
  flex-flow: column;
  right: -10%;
  top: 10%;
}
.adv-con {
  position: absolute;
  display: flex;
  flex-flow: column;
  transform: translate(-100%, 0);
  left: 17%;
  top: 0;
}
.kirobo {
  position: absolute;
  display: flex;
  flex-flow: column;
  bottom: -10%;
  right: 0;
}
.founder {
  position: absolute;
  display: flex;
  flex-flow: column;
  transform: translate(-100%, 0);
  left: 10%;
  bottom: 20%;
}
</style>


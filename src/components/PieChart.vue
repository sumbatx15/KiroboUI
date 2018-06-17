<template>
  <div class="chart-container">
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
      default: "600px"
    },
    height: {
      type: String,
      default: "600px"
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
          this.chart.resize();
        }
      }, 0);
      window.addEventListener("resize", this.__resizeHanlder);
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
    },
    mainDrawer: {
      deep: true,
      handler() {
        this.__resizeHanlder();
      }
    },
    minimized: {
      handler() {
        this.__resizeHanlder();
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
        color: ["#31318e", "#0f62b0","#009abc","#76dfef"],
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
              { value: 25, name: "视频广告" },
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
}
</style>


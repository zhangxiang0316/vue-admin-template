/**
* create by zhangxiang on 2021-11-20 14:40
* 类注释：
* 备注：
*/
<template>
  <el-card :body-style="{padding:'0px'}">
    <div :id="id" class="lineChart" :style="{height:height}" />
  </el-card>
</template>

<script type="text/ecmascript-6">
import * as echarts from 'echarts/core'
import { GridComponent } from 'echarts/components'
import { LineChart } from 'echarts/charts'
import { UniversalTransition } from 'echarts/features'
import { CanvasRenderer } from 'echarts/renderers'

echarts.use([GridComponent, LineChart, CanvasRenderer, UniversalTransition])
export default {
  name: 'LineChart',
  components: {},
  props: {
    id: {
      type: String,
      default: 'line-chart'
    },
    height: {
      type: String,
      default: '300px'
    }
  },
  data() {
    return {}
  },
  computed: {},
  activated() {
  },
  mounted() {
  },
  created() {
  },
  methods: {
    initChart(xData, yData) {
      const chartDom = document.getElementById(this.id)
      this.myChart = echarts.init(chartDom)
      let option = null
      option = {
        xAxis: {
          type: 'category',
          data: xData
        },
        yAxis: {
          type: 'value',
          axisLine: {
            show: true
          }
        },
        series: [
          {
            data: yData,
            type: 'line'
          }
        ]
      }
      this.myChart.resize({ height: this.height })
      option && this.myChart.setOption(option)
    }
  }
}
</script>

<style scoped lang="scss">
.lineChart {
  width: 100%;
}
</style>

/**
* create by zx on 2021/11/25 09:25
* 类注释：
* 备注：
*/
<template>
  <el-card :body-style="{padding:'0px'}">
    <div :id="id" style="width: 100%;" />
  </el-card>
</template>

<script type="text/ecmascript-6">
import * as echarts from 'echarts/core'
import { GridComponent } from 'echarts/components'
import { BarChart } from 'echarts/charts'
import { CanvasRenderer } from 'echarts/renderers'

echarts.use([GridComponent, BarChart, CanvasRenderer])
export default {
  name: 'BarChart',
  components: {},
  props: {
    id: {
      type: String,
      default: 'bar-chart'
    },
    height: {
      type: String,
      default: '300px'
    }
  },
  data() {
    return {
      myChart: null
    }
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
      this.myChart = echarts.init(document.getElementById(this.id))
      const option = {
        xAxis: {
          type: 'category',
          data: xData
        },
        yAxis: {
          type: 'value'
        },
        series: [
          {
            data: yData,
            type: 'bar',
            showBackground: true,
            backgroundStyle: {
              color: 'rgba(180, 180, 180, 0.2)'
            }
          }
        ]
      }
      this.myChart.resize({ height: this.height })
      option && this.myChart.setOption(option)
    }
  }
}
</script>

<style scoped>

</style>

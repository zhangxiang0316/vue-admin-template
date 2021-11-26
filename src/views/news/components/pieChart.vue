/**
* create by zx on 2021/11/25 09:33
* 类注释：
* 备注：
*/
<template>
  <el-card :body-style="{padding:'0px'}">
    <div :id="id" style="width: 100%;" :style="{height:height}" />
  </el-card>
</template>

<script type="text/ecmascript-6">
import * as echarts from 'echarts/core'
import {
  TitleComponent,
  TooltipComponent,
  VisualMapComponent
} from 'echarts/components'
import { PieChart } from 'echarts/charts'
import { LabelLayout } from 'echarts/features'
import { CanvasRenderer } from 'echarts/renderers'

echarts.use([
  TitleComponent,
  TooltipComponent,
  VisualMapComponent,
  PieChart,
  CanvasRenderer,
  LabelLayout
])
export default {
  name: 'PieChart',
  components: {},
  props: {
    id: {
      type: String,
      default: 'pre-chart'
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
    initChart(data) {
      this.myChart = echarts.init(document.getElementById(this.id))
      const option = {
        backgroundColor: '#2c343c',
        title: {
          text: 'Customized Pie',
          left: 'center',
          top: 20,
          textStyle: {
            color: '#ccc'
          }
        },
        tooltip: {
          trigger: 'item'
        },
        visualMap: {
          show: false,
          min: 80,
          max: 600,
          inRange: {
            colorLightness: [0, 1]
          }
        },
        series: [
          {
            name: 'Access From',
            type: 'pie',
            radius: '55%',
            center: ['50%', '50%'],
            data: data.sort(function(a, b) {
              return a.value - b.value
            }),
            roseType: 'radius',
            label: {
              color: 'rgba(255, 255, 255, 0.3)'
            },
            labelLine: {
              lineStyle: {
                color: 'rgba(255, 255, 255, 0.3)'
              },
              smooth: 0.2,
              length: 10,
              length2: 20
            },
            itemStyle: {
              color: '#c23531',
              shadowBlur: 200,
              shadowColor: 'rgba(0, 0, 0, 0.1)'
            },
            animationType: 'scale',
            animationEasing: 'elasticOut',
            animationDelay: function(idx) {
              return Math.random() * 200
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

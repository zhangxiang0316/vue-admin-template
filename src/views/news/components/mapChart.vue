/**
* create by zhangxiang on 2021-11-21 12:43
* 类注释：
* 备注：
*/
<template>
  <el-card :body-style="{padding:'10px'}">
    <div
      :id="id"
      style=" height: 300px; width: 100%;"
    />
  </el-card>
</template>

<script type="text/ecmascript-6">
import * as echarts from 'echarts'
import './map/js/china.js' // 引入中国地图数据
// 还要特别引入china.json，这样中国地图才会出现，不然只会出现右下角的南海诸岛
import china from './map/json/china.json'

echarts.registerMap('china', china)
export default {
  name: 'MapChart',
  components: {},
  props: {
    id: {
      type: String,
      default: 'map-chart'
    }
  },
  data() {
    return {
      data: [
        { 'name': '南海诸岛', 'value': 0 },
        { 'name': '北京', 'value': 0 },
        { 'name': '天津', 'value': 10 },
        { 'name': '上海', 'value': 0 },
        { 'name': '重庆', 'value': 0 },
        { 'name': '河北', 'value': 15 },
        { 'name': '河南', 'value': 0 },
        { 'name': '云南', 'value': 0 },
        { 'name': '辽宁', 'value': 19},
        { 'name': '黑龙江', 'value': 0 },
        { 'name': '湖南', 'value': 0 },
        { 'name': '安徽', 'value': 0 },
        { 'name': '山东', 'value': 0 },
        { 'name': '新疆', 'value': 0 },
        { 'name': '江苏', 'value': 0 },
        { 'name': '浙江', 'value': 0 },
        { 'name': '江西', 'value': 0 },
        { 'name': '湖北', 'value': 0 },
        { 'name': '广西', 'value': 0 },
        { 'name': '甘肃', 'value': 0 },
        { 'name': '山西', 'value': 0 },
        { 'name': '内蒙古', 'value': 0 },
        { 'name': '陕西', 'value': 0 },
        { 'name': '吉林', 'value': 0 },
        { 'name': '福建', 'value': 0 },
        { 'name': '贵州', 'value': 0 },
        { 'name': '广东', 'value': 0 },
        { 'name': '青海', 'value': 0 },
        { 'name': '西藏', 'value': 0 },
        { 'name': '四川', 'value': 0 },
        { 'name': '宁夏', 'value': 0 },
        { 'name': '海南', 'value': 0 },
        { 'name': '台湾', 'value': 0 },
        { 'name': '香港', 'value': 0 },
        { 'name': '澳门', 'value': 0 }
      ]
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
    initChart() {
      const chartDom = document.getElementById(this.id)
      const myChart = echarts.init(chartDom)
      let option = null

      option = {
        tooltip: {
          trigger: 'item',
          backgroundColor: '#f08519'
        },
        legend: {
          orient: 'vertical',
          left: 'left',
          data: ['']
        },
        dataRange: { // 地图颜色深浅
          orient: 'horizontal',
          min: 0,
          max: 8000,
          show: false
        },
        selectedMode: 'single',
        series: [
          {
            name: '',
            type: 'map',
            mapType: 'china',
            itemStyle: {
              normal: {
                borderColor: 'rgba(0, 0, 0, 0.2)'
              },
              emphasis: {
                shadowOffsetX: 0,
                shadowOffsetY: 0,
                shadowBlur: 20,
                borderWidth: 0,
                shadowColor: 'rgba(0, 0, 0, 0.5)'
              }
            },
            showLegendSymbol: true,
            label: {
              normal: {
                show: true
              },
              emphasis: {
                show: true
              }
            },
            data: this.data
          }
        ]
      }
      option && myChart.setOption(option)
    }
  }
}
</script>

<style scoped lang="less" rel="stylesheet/less">

</style>

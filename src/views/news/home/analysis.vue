/**
* create by zhangxiang on 2021-11-20 10:56
* 类注释：
* 备注：
*/
<template>
  <div class="analysis">
    <template v-for="(item,index) in list">
      <map-chart v-if="index==1" :id="`line-chart${index}`" ref="lineChart" :key="index" style="margin: 1%;width: 31%;float: left" />
      <line-chart
        v-else
        :id="`line-chart${index}`"
        ref="lineChart"
        :key="index"
        style="margin: 1%;width: 31%;float: left"
      />
    </template>
  </div>
</template>

<script type="text/ecmascript-6">
import lineChart from '@/views/news/components/lineChart'
import mapChart from '@/views/news/components/mapChart'

export default {
  name: 'Analysis',
  components: {
    lineChart,
    mapChart
  },
  props: {},
  data() {
    return {
      list: [
        {
          xData: ['Mon', 'Tue', 'Wed', 'Thu', 'Fri', 'Sat', 'Sun'],
          yData: [150, 230, 224, 112, 135, 569, 260]
        },
        {
          xData: ['Mon', 'Tue', 'Wed', 'Thu', 'Fri', 'Sat', 'Sun'],
          yData: [150, 230, 224, 112, 135, 569, 260]
        },
        {
          xData: ['Mon', 'Tue', 'Wed', 'Thu', 'Fri', 'Sat', 'Sun'],
          yData: [150, 230, 224, 112, 135, 569, 260]
        },
        {
          xData: ['Mon', 'Tue', 'Wed', 'Thu', 'Fri', 'Sat', 'Sun'],
          yData: [150, 230, 224, 112, 135, 569, 260]
        },
        {
          xData: ['Mon', 'Tue', 'Wed', 'Thu', 'Fri', 'Sat', 'Sun'],
          yData: [150, 230, 224, 112, 135, 569, 260]
        },
        {
          xData: ['Mon', 'Tue', 'Wed', 'Thu', 'Fri', 'Sat', 'Sun'],
          yData: [150, 230, 224, 112, 135, 569, 260]
        },
        {
          xData: ['Mon', 'Tue', 'Wed', 'Thu', 'Fri', 'Sat', 'Sun'],
          yData: [150, 230, 224, 112, 135, 569, 260]
        },
        {
          xData: ['Mon', 'Tue', 'Wed', 'Thu', 'Fri', 'Sat', 'Sun'],
          yData: [150, 230, 224, 112, 135, 569, 260]
        },
        {
          xData: ['Mon', 'Tue', 'Wed', 'Thu', 'Fri', 'Sat', 'Sun'],
          yData: [150, 230, 224, 112, 135, 569, 260]
        }
      ]
    }
  },
  computed: {},
  activated() {
  },
  mounted() {
    this.loadData()
  },
  created() {
  },
  methods: {
    loadData() {
      this.list.map((item, index) => {
        this.$refs.lineChart[index].initChart(item.xData, item.yData)
      })
    }
  }
}
</script>

<style scoped lang="scss">
.analysis {
  padding: 10px;
}

</style>

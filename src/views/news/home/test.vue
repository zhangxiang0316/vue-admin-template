<template>
  <div class="parent">
    <pie-chart ref="pieChart" class="div1" :height="height1" />
    <line-chart ref="lineChart" class="div2" :height="height2" />
    <bar-chart ref="barChart" class="div3" :height="height3" />
    <map-chart ref="mapChart" class="div4" :height="height4" />
    <div class="div5" style="background: #2042cc" />
    <div class="div6" style="background: #2042cc" />
    <div class="div7" style="background: #2042cc" />
    <div class="div8" style="background: #2042cc" />
    <div class="div9" style="background: #2042cc" />
  </div>
</template>

<script>
// import screenfull from 'screenfull'
import mapChart from '@/views/news/components/mapChart'
import lineChart from '@/views/news/components/lineChart'
import barChart from '@/views/news/components/barChart'
import pieChart from '@/views/news/components/pieChart'

export default {
  components: {
    mapChart,
    lineChart,
    barChart,
    pieChart
  },
  data() {
    return {
      height4: '500px',
      height2: '500px',
      height3: '500px',
      height1: '500px',

      fullscreen: false, // 是否全屏
      goCount: 0 // 退出第几次
    }
  },
  mounted() {
    this.init()
    const self = this
    window.onresize = function() {
      console.log('33333333333')
      self.init()
    }
  },
  methods: {
    init() {
      this.height1 = document.getElementsByClassName('div1')[0].offsetHeight + 'px'
      this.height2 = document.getElementsByClassName('div2')[0].offsetHeight + 'px'
      this.height3 = document.getElementsByClassName('div3')[0].offsetHeight + 'px'
      this.height4 = document.getElementsByClassName('div4')[0].offsetHeight + 'px'
      console.log(this.height1, this.height2)
      this.$nextTick(() => {
        this.$refs.mapChart.initChart()
        this.$refs.lineChart.initChart(['Mon', 'Tue', 'Wed', 'Thu', 'Fri', 'Sat', 'Sun'], [150, 230, 224, 112, 135, 569, 260])
        this.$refs.barChart.initChart(['Mon', 'Tue', 'Wed', 'Thu', 'Fri', 'Sat', 'Sun'], [150, 230, 224, 112, 135, 569, 260])
        this.$refs.pieChart.initChart([{ value: 335, name: 'Direct' }, { value: 310, name: 'Email' }, { value: 274, name: 'Union Ads' }, { value: 235, name: 'Video Ads' }, { value: 400, name: 'Search Engine' }])
      })
    },
    checkFull() {
      // 判断浏览器是否处于全屏状态 （需要考虑兼容问题）
      // 火狐浏览器
      let isFull =
        document.mozFullScreen ||
        document.fullScreen ||
        // 谷歌浏览器及Webkit内核浏览器
        document.webkitIsFullScreen ||
        document.webkitRequestFullScreen ||
        document.mozRequestFullScreen ||
        document.msFullscreenEnabled
      if (isFull === undefined) {
        isFull = false
      }
      return isFull
    }
  }
}

</script>

<style lang="scss" scoped>
.parent {
  padding: 5px;
  height: 100%;
  display: grid;
  grid-template-columns: repeat(24, 1fr);
  grid-template-rows: repeat(12, 1fr);
  grid-column-gap: 5px;
  grid-row-gap: 5px;
  background: #aaa;
}

.div1 { grid-area: 1 / 1 / 5 / 7; }
.div2 { grid-area: 5 / 1 / 9 / 7; }
.div3 { grid-area: 9 / 1 / 13 / 7; }
.div4 { grid-area: 1 / 7 / 9 / 19; }
.div5 { grid-area: 1 / 19 / 5 / 25; }
.div6 { grid-area: 5 / 19 / 9 / 25; }
.div7 { grid-area: 9 / 7 / 13 / 13; }
.div8 { grid-area: 9 / 13 / 13 / 19; }
.div9 { grid-area: 9 / 19 / 13 / 25; }

</style>

/**
* create by zx on 2021/11/15 10:17
* 类注释：
* 备注：
*/
<template>
  <div class="home">
    <div class="fixed-header">
      <mHeader style="margin: 0 auto" />
    </div>
    <div class="main">
      <router-view />
    </div>
  </div>
</template>

<script type="text/ecmascript-6">
import mHeader from '@/views/home/components/header'
export default {
  name: 'Home',
  components: {
    mHeader
  },
  props: {},
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
  methods: {}
}
</script>

<style lang="scss" scoped>
@import '~@/styles/mixin.scss';
@import "~@/styles/variables.scss";
.home{
  min-width: 1000px;
  .fixed-header {
    position: fixed;
    top: 0;
    right: 0;
    z-index: 9;
    width: 100%;
    background: #181f41;
    height: 50px;
    transition: width 0.28s;
  }
  .main{
    min-height: calc(100vh - 50px);
    padding-top: 50px;
  }
}
</style>

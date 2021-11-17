/**
* create by zx on 2021/11/17 14:49
* 类注释：
* 备注：
*/
<template>
  <div class="homeItem">
    <div class="title">{{ detail.title }}</div>
    <detail-disc :introduce="detail.disc" class="disc" />
  </div>
</template>

<script type="text/ecmascript-6">
import detailDisc from '@/views/home/components/detailDisc'
export default {
  name: 'HomeItem',
  components: {
    detailDisc
  },
  props: {
    detail: {
      type: Object,
      default: () => {
        return {}
      }
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
  methods: {}
}
</script>

<style scoped lang="scss">
.homeItem{
  margin: 10px;
  .title{
    font-size: 17px;
    color: #222;
    line-height: 30px;
    font-weight: 800;
  }
  .disc{
    font-size: 15px;
    color: #666;
    line-height: 18px;
  }
}

</style>

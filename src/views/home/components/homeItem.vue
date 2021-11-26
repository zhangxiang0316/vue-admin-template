/**
* create by zx on 2021/11/17 14:49
* 类注释：
* 备注：
*/
<template>
  <div class="homeItem">
    <div class="title">{{ detail.title }}</div>
    <!--    <detail-disc :value="detail.disc" class="disc" :index="index" />-->
    <v-clamp :max-lines="3" style="font-size: 15px;color: #666">
      {{ detail.disc }}
      <button
        v-show="clamped"
        slot="after"
        slot-scope="{ expand, collapse, toggle, clamped }"
        class="toggle btn btn-sm"
        @click="toggle"
      > 展开</button>
    </v-clamp>
  </div>
</template>

<script type="text/ecmascript-6">
// import detailDisc from '@/views/home/components/detailDisc'
import VClamp from 'vue-clamp'
export default {
  name: 'HomeItem',
  components: {
    // detailDisc,
    VClamp
  },
  props: {
    index: {
      type: Number,
      default: -1
    },
    detail: {
      type: Object,
      default: () => {
        return {}
      }
    }
  },
  data() {
    return {
      expanded: false
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
    toggle(e) {
      console.log(e)
    }
  }
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

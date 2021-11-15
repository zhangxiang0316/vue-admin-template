/**
* create by zx on 2021/11/15 10:39
* 类注释：
* 备注：
*/
<template>
  <div class="tab">
    <div
      v-for="(tab,index) in tabs"
      :key="index"
      class="tab-item"
      :class="{'tab-item-select':index===selectIndex}"
      @click="tabClick(tab,index)"
    >{{ tab.name }}</div>
  </div>
</template>

<script type="text/ecmascript-6">
export default {
  name: 'Tab',
  components: {},
  props: {
    tabs: {
      type: Array,
      default: []
    }
  },
  data() {
    return {
      selectIndex: 0
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
    tabClick(tab, index) {
      this.selectIndex = index
      this.$router.push({ path: tab.path })
    }
  }
}
</script>

<style lang="scss" scoped>
.tab{
  display: flex;
  .tab-item{
    color: white;
    min-width: 32px;
    cursor: pointer;
    margin-left: 30px;
    line-height: 48px;
  }
  .tab-item-select{
    border-bottom: 3px solid white;
  }
}

</style>

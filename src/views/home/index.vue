/**
* create by zx on 2021/11/15 13:22
* 类注释：
* 备注：
*/
<template>
  <div class="index">
    <div style="flex:2;overflow-y: scroll;height: 100%">
      <home-item v-for="(item,index) in list" :key="index" :detail="item" />
    </div>
    <div style="flex: 1">dsfsfsf</div>
  </div>
</template>

<script type="text/ecmascript-6">
import homeItem from '@/views/home/components/homeItem'
export default {
  name: 'Index',
  components: {
    homeItem
  },
  props: {},
  data() {
    return {
      list: []
    }
  },
  computed: {

  },
  activated() {
  },
  mounted() {
  },
  created() {
    this.loadList()
  },
  methods: {
    loadList() {
      this.$api.home.getHomeList().then(res => {
        this.list = res.data
      })
    }
  }
}
</script>

<style scoped lang="scss">
/* 整个滚动条 */
  ::-webkit-scrollbar {
  /* 对应纵向滚动条的宽度 */
  width: 0px;
  /* 对应横向滚动条的宽度 */
  height: 10px;
}
.index{
  max-width: 1000px;
  height: 100% ;
  margin: 0 auto;
  display: flex;
}

</style>

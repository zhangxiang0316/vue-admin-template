/**
* create by zx on 2021/11/15 10:32
* 类注释：
* 备注：
*/
<template>
  <div class="header">
    <div class="content">
      <div style="font-size: 25px;cursor: pointer" @click="$router.push({path:'/home/index'})">Demo</div>
      <tab :tabs="[{name:'首页',path:'/home/index'},{name:'精品',path:'/home/boutique'},{name:'发现'}]" />
      <el-input>
        <i slot="suffix" class="el-icon-search search" />
      </el-input>
      <el-button style="height: 35px;margin-top: 7px;margin-left: 20px" round>查找</el-button>
    </div>
  </div>
</template>

<script type="text/ecmascript-6">
import tab from '@/views/home/components/tab'
export default {
  name: 'Header',
  components: {
    tab
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

.header{
  height: 50px;
  max-width: 1000px;
  line-height: 50px;
  color: white;
  .content{
    margin: 0 auto;
    display: flex;
  }
  ::v-deep  .el-input__inner{
    border-radius: 30px;
    width: 300px;
    height: 35px;
    border: 1px solid transparent;
    background: #ffffff22;
  }
  ::v-deep .el-input{
    width: 300px;
    height: 35px;
    margin-left: 50px;
  }
  ::v-deep .el-button.is-round{
    padding: 7px 23px;
  }
  .search{
    font-size: 16px;
    margin-right: 8px;
    cursor: pointer;
    padding-top: 17px;
    color: #aaa;
  }
}

</style>

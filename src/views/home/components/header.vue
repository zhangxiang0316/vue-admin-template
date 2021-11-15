/**
* create by zx on 2021/11/15 10:32
* 类注释：
* 备注：
*/
<template>
  <div class="header">
    <div class="content">
      <div style="font-size: 25px">Demo</div>
      <tab :tabs="[{name:'首页'},{name:'精品'},{name:'发现'}]" />
      <el-input>
        <i slot="suffix" class="el-icon-search search"></i>
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
::v-deep  .el-input__inner{
  border-radius: 30px;
  height: 35px;
  border: 1px solid transparent;
  background: #464C67;
}

::v-deep .el-input{
  width: 300px;
  height: 35px;
  margin-left: 100px;
}
::v-deep .el-button.is-round{
  padding: 7px 23px;
}
.header{
  background: #181f41;
  height: 50px;
  line-height: 50px;
  color: white;
  .content{
    width: 70%;
    margin: 0 auto;
    display: flex;
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

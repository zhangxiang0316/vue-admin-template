/**
* create by zx on 2021/11/17 15:39
* 类注释：
* 备注：
*/
<template>
  <div class="wrapper">
    <input :id="`exp${index}`" class="exp" type="checkbox">
    <div class="text">
      <label class="btn" :for="`exp${index}`" />
      {{ value }}
    </div>
  </div>
</template>

<script type="text/ecmascript-6">
export default {
  name: 'DetailDisc',
  props: {
    index: {
      type: Number,
      default: -1
    },
    value: { // 文字
      type: String,
      default: ''
    },
    theBackgroundColor: { // 文字伪类背景颜色
      type: String,
      default: '#f9f9f9'
    }
  },
  data() {
    return {

    }
  },
  watch: {
  },
  methods: {

  }
}
</script>

<style scoped lang="scss">
.wrapper {
  width: 100%;
  display: flex;
  overflow: hidden;
  font-size: 15px;
  color: #666;
}
.text {
  font-size: 15px;
  overflow: hidden;
  text-overflow: ellipsis;
  text-align: justify;
  position: relative;
  line-height: 21px;
  max-height: 63px;
  transition: .3s max-height;
}
.text::before {
  content: '';
  height: calc(100% - 26px);
  float: right;
}
.text::after {
  content: '';
  width: 999vw;
  height: 999vw;
  position: absolute;
  box-shadow: inset calc(100px - 999vw) calc(30px - 999vw) 0 0 #fff;
  margin-left: -100px;
}
.btn{
  position: relative;
  float: right;
  clear: both;
  margin-left: 20px;
  font-size: 15px;
  padding: 0 8px;
  background: #3F51B5;
  height:20px;
  line-height: 20px;
  border-radius: 4px;
  color:  #fff;
  cursor: pointer;
}
.btn::after{
  content:'展开'
}
.exp{
  display: none;
}
.exp:checked+.text{
  max-height: none;
}
.exp:checked+.text::after{
  visibility: hidden;
}
.exp:checked+.text .btn::before{
  visibility: hidden;
}
.exp:checked+.text .btn::after{
  content:'收起'
}
.btn::before{
  content: '...';
  position: absolute;
  left: -5px;
  color: #333;
  transform: translateX(-100%)
}

</style>

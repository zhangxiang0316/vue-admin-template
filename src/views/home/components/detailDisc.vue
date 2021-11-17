/**
* create by zx on 2021/11/17 15:39
* 类注释：
* 备注：
*/
<template>
  <div class="detailDisc">
    <div :class="showTotal ? 'total-introduce' : 'detailed-introduce'">
      <div ref="desc" class="intro-content" :title="introduce">
        <span v-if="introduce" class="merchant-desc">{{ introduce }}</span>
        <div v-if="showExchangeButton" class="unfold" @click="showTotalIntro">
          <p>{{ exchangeButton ? '展开' : '收起' }}</p>
        </div>
      </div>
    </div>
  </div>
</template>

<script type="text/ecmascript-6">
export default {
  name: 'DetailDisc',
  props: {
    introduce: {
      type: String,
      default: ''
    }
  },
  data() {
    return {
      showTotal: false, // 简介全部显示
      exchangeButton: true, // 展开/收起文字改变
      showExchangeButton: false // 是否显示 展开/收起 文字
    }
  },
  watch: {
  },
  methods: {
    showTotalIntro() {
      this.showTotal = !this.showTotal
      this.exchangeButton = !this.exchangeButton
    }
  }
}
</script>

<style scoped lang="scss">
.total-introduce{
  height: auto;
  overflow: hidden;
  font-size: 15px;
  color: #666;
  .intro-content{
    .merchant-desc{
      width: 100%;
      line-height: 20px;
    }
  }
  .unfold{
    display: block;
    float: right;
    width: 80px;
    height: 20px;
    z-index: 8;
    text-align: center;
    p{
      margin: 0;
      line-height: 20px;
      color: #0098ff;
    }
  }
}
.detailed-introduce{
  font-size: 15px;
  color: #666;
  position: relative;
  overflow: hidden;
  .intro-content{
    //最大高度设为3倍的行间距
    max-height: 60px;
    line-height: 20px;
    word-wrap: break-word;
    word-break: break-all;
    background-color: #fff;
    color: #fff;
    overflow: hidden;
    .merchant-desc{
      width: 100%;
      line-height: 20px;
    }
    &::after,
    &::before{
      content: attr(title);
      position: absolute;
      left: 0;
      top: 0;
      width: 100%;
      color: #666;
    }
    &::before{
      display: block;
      overflow: hidden;
      z-index: 1;
      max-height: 60px;
      background: #FFF;
    }
    &::after{
      display: -webkit-box;
      -webkit-box-orient: vertical;
      height: 60px;
      // 截取行数
      -webkit-line-clamp: 3;
      text-overflow: ellipsis;
      box-sizing: border-box;
      // 行首缩进字符数，值为[(截取行数-1)*尾部留空字符数]
      text-indent: -6em;
      // 尾部留空字符数
      padding-right: 3em;

    }
    .unfold {
      z-index: 8;
      width: 80px;
      height: 20px;
      outline: 0;
      position: absolute;
      right: 0;
      bottom: 0;
      text-align: center;
      p {
        margin: 0;
        color: #0098ff;
      }
    }
  }
}
</style>

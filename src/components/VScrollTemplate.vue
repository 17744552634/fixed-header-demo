<template>
  <!--<scroller lock-x class="center-content" height="500px" margin-top="100px" @on-scroll="onScroll" ref="scrollerEvent">-->
    <!--<div class="box2">-->
      <!--<p v-for="i in 30">placeholder {{i}}</p>-->
    <!--</div>-->
  <!--</scroller>-->
  <div class="center-div-content">
    <p v-for="i in 30">placeholder {{i}}</p>
  </div>
</template>

<script>
  import { Scroller } from 'vux'
  export default {
    name: 'VScrollTemplate',
    data () {
      return {
        data: {
          showList1: true,
          scrollTop: 0,
          onFetching: false,
          bottomCount: 20
        }
      }
    },
    components: {
      Scroller
    },
    methods: {
      onScroll (pos) {
        this.scrollTop = pos.top
      },
    }
  }
</script>

<style scoped lang="less">
  .center-div-content{
    margin-top: 100px;
    max-height: 500px;
    min-height: 300px;
    overflow-y: scroll;
    width: 100%;
    box-sizing: border-box;
  }
  .center-div-content .inner-div{
    height: 1000px;
  }
  .center-content {
    margin-top: 100px;
    height: 1000px;
    width: 100%;
    box-sizing: border-box;
    /*border: 1px solid #000;*/
  }
</style>

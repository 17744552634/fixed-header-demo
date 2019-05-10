<template>
  <div class="div-infor">
    <header class="header-content"></header>
    <!--<x-header style="position:fixed;top:0px" 133131"></x-header>-->

    <VScrollTemplate/>
    <footer class="footer-content">
      <input @focus="inputFocus" @blur="inputBlur"/>
    </footer>
    <div class="mb"></div>
  </div>
</template>

<script>
  import VScrollTemplate from './VScrollTemplate'
  import {XHeader} from 'vux'

  export default {
    name: 'HelloWorld',
    data() {
      return {
        msg: 'Welcome to Your Vue.js App',
        docmHeight: document.body.clientHeight,//默认
        showHeight: document.body.clientHeight,//实际
        hideshow: true //是否显示
      }
    },
    components: {
      VScrollTemplate,
      XHeader
    },
    mounted() {
      this.docmHeight = document.body.clientHeight;//默认
      this.showHeight = document.body.clientHeight;//实际
    },
    methods: {
      inputFocus() {

        new Promise((resolve, reject) => {
          this.showHeight = document.body.clientHeight;
          if (this.showHeight) {
            resolve(this.showHeight/2)
          }
        }).then((c) => {
          var h = document.getElementsByClassName('header-content')[0];
          h.style.position = 'fixed';
          h.style.top = c + 'px';
          var b = document.body;
          b.style.overflow = 'hidden';
        })

      },
      inputBlur(){
        var h = document.getElementsByClassName('header-content')[0];
        h.style.position = 'fixed';
        h.style.top = '0px';
        var b = document.body;
        b.style.overflow = 'auto';
      }

    }
  }

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .mb{
    display: none;
    position: fixed;
    top: 0;
    bottom: 0;
    left: 0;
    right: 0;
    background-color: #333333;
  }
  .div-infor{
    /*padding: 3px;*/
    /*border: 3px solid #e59313;*/
    position: relative;
  }
  .header-content {
    width: 100%;
    height: 100px;
    background-color: darkblue;
    position: fixed;
    left: 0;
    top: 0;
  }

  .footer-content {
    width: 100%;
    height: 100px;
    background-color: bisque;
    display: flex;
    justify-content: center;
    align-items: center;
  }
</style>

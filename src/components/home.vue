<template>
  <div class="page-box">
    <header-search  v-on:showPanel = "result">
          <template>
            <router-link tag="span" to="/cityList">
              <span>{{this.city}}</span>
              <i class="iconfont icon-xiala"></i>
            </router-link>
          </template>
      </header-search>
      <div class="page-box" :style="{ opacity : this.shadow ? 0.1 : 1}" >
        <bmap v-on:cityName = "getCityName"></bmap>
        <tools></tools>
        <footer-nav></footer-nav>
      </div>
  </div>
</template>

<script>
import header from './home/header.vue'
import bmap from './home/map.vue'
import footer from './home/footer.vue'
import tools from './tools/tools.vue'

export default {
  name: 'home',
  data(){
    return {
      shadow : '',
      isClick:'',
      city:'长沙',
    }
  },
  // created(){
  //   this.$root.Hub.$on('cityChange',value =>{
  //     this.print(value);
  //   })
  // },
  // 在组件销毁时别忘了解除事件绑定
  // beforeDestroy() {
  //   this.$root.Bus.$off('cityChange')
  // },
  components:{
    "header-search": header,
    "bmap": bmap,
    "footer-nav":footer,
    'tools':tools,
  },
  methods:{
    result : function(data){
      this.shadow = data;
    },
    getCityName:function(data){
      this.city = data;
    },
    // print:function(value){
    //   console.log('点击的是——'+value);
    //   this.city = value;
    //   console.log('显示的是——'+this.city);
    // }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style>
@import "../assets/css/public.css";
@import "../assets/css/font.css";
</style>

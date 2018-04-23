<template>
    <li class="tool" :class="{'c' : isClick}" @click="cc">
        <i class="iconfont icon-bi"></i>
        <span class="tool-name">画圈</span>
    </li>
</template>
<script>
import DistanceTool from 'bmaplib.distancetool'

export default {
  name:'bi',
  data(){
      return {
          isClick: false,
      }
  },
  mounted(){
  },
  methods:{
      cc:function(){
          this.isClick = !this.isClick;
      }
  }

}
</script>
<style>
@import '../../../assets/css/tools/tools.scss';
.c{
    color: #FFE4B5;
     box-shadow: 3px 1px 5px #888888;
}
</style>


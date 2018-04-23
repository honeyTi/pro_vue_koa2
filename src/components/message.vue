<template>
  <div>
      <header class="header">
        <ul class="information-nav">
            <li class="active">消息</li>
            <li>通知</li>
            <li>需求</li>
        </ul>
    </header>
     <div class="contain-box contain-bottom">
        <div class="click-all new-click">
             <ul class="information-contain">
                <li class="information-contain-li1"><p class="title">武林大厦,市中医院周边！</p></li>
                <li class="information-contain-li2">
                    <p>房子干净清爽，基本生活家电齐全；简单打扫整理即可入住,装修还不错，中档偏上有的,入住随时方便……</p>
                    <p class="inf-float inf-float2">08/04/13:06</p>
                </li>
            </ul>
        </div>
     </div>
    <footer-nav></footer-nav>
  </div>
  
</template>
<script>
import footer from './home/footer.vue'

export default {
  name:'message',
  components:{
    "footer-nav":footer
  },
}
</script>
<style>
@import '../assets/css/public.css';
@import '../assets/css/messages.css'
</style>

<template>
  <div>
    <header class="header">
        <span class="title">预约</span>
    </header>
    <div class="contain-box contain-bottom">
        <!--没接单的 -->
        <div class="contain-main-box order-main fist-li btnclick"  data-target-page="order__take" data-target-doc="order">
            <div class="contain-flex1">
                <img class="contain-main-img" src="../assets/images/index/content_img_list@2x.png" alt=""></div>
            <div class="contain-main-flex4">
                <ul class="contain-ul" >
                    <li class="order-li1">
                        <span class="order-text1">先生/女士您好：</span>
                        <span class="order-time">08/03/16:02</span>
                    </li>
                    <li><p class="order-text2">我想看<span class="order-adress">[xx大楼]</span>的房源，请帮我安排，请帮我安排,我想看。</p>
                    </li>
                    <li><p class="order-text3">看房时间：08/03</p></li>
                    <li><p class="btn-order" id="click-changetext" data-target-text="已接单，待反馈">接单</p></li>
                </ul>
            </div>
        </div>
        <!--已接单的-->
        <div class="contain-main-box order-main btnclick" data-target-page="order__finish" data-target-doc="order">
            <div class="contain-flex1">
                <img class="contain-main-img" src="../assets/images/index/content_img_list@2x.png" alt=""></div>
            <div class="contain-main-flex4">
                <ul class="contain-ul">
                    <li class="order-li1">
                        <span class="order-text1">先生/女士您好：</span>
                        <span class="order-time">08/03/16:02</span>
                    </li>
                    <li><p class="order-text2">我想看<span class="order-adress">[xx大楼]</span>的房源，请帮我安排，请帮我安排,我想看。</p>
                    </li>
                    <li><p class="order-text3">看房时间：08/03</p></li>
                    <li class="contain-li4"><p class="order-text4">已接单，待反馈</p></li>
                </ul>
            </div>
        </div>
    </div>
    <footer-nav></footer-nav>
  </div>
  
</template>
<script>
import footer from './home/footer.vue'

export default {
  name:'meeting',
  components:{
    "footer-nav":footer
  },
}
</script>
<style>
@import '../assets/css/public.css';
@import '../assets/css/meeting.css';
</style>

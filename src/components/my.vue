<template>
  <div>
    <header class="header clearfloat">
        <span class="title">我</span>
        <i class="install-icon"></i>
    </header>
     <div class="contain-box contain-bottom">
        <ul class="my-box-ul">
            <li class="click-islogin fist-li">
                <!--未登陆注册的模块-->
                <ul class="my-box-information no-login" >
                    <router-link to='/login' tag="li">
                        <img class="myhead-img" src="../assets/images/my/log in_user-head@2x.png" alt="">
                        <span class="mybox-inf" style="display:block" v-if="ifshow">点击注册/登录<i class="mylogin-right mylogin-right-to"></i></span>
                        <span class="mybox-inf" style="display:block" v-if="!ifshow">{{user}}<i class="mylogin-right mylogin-right-to"></i></span>
                  </router-link>
                    <li class="">
                        <ul class="display-flex ">
                            <li class="my-infor-li22 "><span class="text-change">0</span>收藏</li>
                            <li class="my-infor-li22"><span class="text-change">0</span>积分</li>
                        </ul>
                    </li>
                </ul>
                <!--登陆的模块-->
                <ul class="my-box-information yes-login">
                    <li class="my-infor-li1 clearfloat btnclick">
                        <img class="myhead-img" src="../assets/images/my/log in_user-head@2x.png" alt="">
                        <span class="mybox-inf2">{{user}}</span>
                        <span>修改资料</span>
                        <i class="mylogin-right mylogin-right2"></i>
                    </li>
                    <li class="my-infor-li2">
                        <ul class="display-flex ">
                            <li class="my-infor-li22 "><span class="text-change">64</span>收藏</li>
                            <li class="my-infor-li22"><span class="text-change">624</span>积分</li>
                        </ul>
                    </li>
                </ul>
            </li>
            <router-link class="contain-my-box" tag="li" to="" v-for="item in list" :key="item.id">
               {{item}}<i class="mylogin-right"></i>
            </router-link>
        </ul>
    </div>
    <footer-nav></footer-nav>
  </div>
  
</template>
<script>
import footer from "./home/footer.vue";

export default {
  name: "my",
  data() {
    return {
      list: [
        "我发布的需求",
        " 我发布的房源",
        "我预约的房源",
        "历史交易",
        "过期房源"
      ],
      user: '点击登录/注册',
      type: '',
      ifshow: true
    };
  },
  components: {
    "footer-nav": footer
  },
  mounted: function () {
    console.log(this.user);
    let userName = sessionStorage.getItem("name");
    let userType = sessionStorage.getItem("type");
    userName !== "" ? (this.user = userName) : (this.user = "点击登录/注册");
    userName !== "" ? (this.ifshow = false) : (this.ifshow = true);
    userType !== "" ? (this.type = userType) : (this.type = "");
    console.log(this.user);
    console.log(this.ifshow);
  }
};
</script>
<style>
@import "../assets/css/public.css";
@import "../assets/css/my.css";
</style>

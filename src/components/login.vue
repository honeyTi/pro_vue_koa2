<template>
<div>
     <header class="header clearfloat">
        <router-link tag="i" class="return btnclick" to="/home"></router-link>
        <span class="title">登录</span>
    </header>
    
    <div class="contain-box">
        <ul class="login_contain">
            <li class="label-li1 clearfloat">
                <div class="basic-label id_bg">账号：</div>
                <div class="basic-inputbox">
                    <input class="basic-input" type="tel" id="username" v-model="name" placeholder="请输入您的手机号">
                </div>
            </li>
            <li class="label-li1 label-last clearfloat">
                <div class="basic-label password_bg">密码：</div>
                <div class="basic-inputbox">
                    <input class="basic-input" type="password" id="password" v-model="psd" placeholder="请输入您的账号密码">
                </div>
            </li>
        </ul>
        <div class="login-btn">
            <button id="btn-login" class="btn-basic btnclick" @click="log">登陆</button>
        </div>
        <div class="login-btn login_btn2">
            <router-link class="enroll btnclick" tag="span" to="/register">注册</router-link>
            <router-link class="forgert-pass btnclick" tag="span" to="/forgetpassword">忘记密码?</router-link>
        </div>
    </div>
</div>
</template>
<script>
import axios from "axios";
export default {
  name: "login",
  data() {
    return {
      name: "",
      psd: ""
    };
  },
  methods: {
    log() {
      axios
        .get(
          "http://localhost:3000/login",
          {
            params: {
              name: this.name,
              psd: this.psd
            }
          },
          "json"
        )
        .then(
          data => {
            if (data.data.code === "1") {
              console.log(data.result);
              this.$vux.toast.text("登录成功", "middle");
              sessionStorage.setItem("name", data.data.result[0].user_tel);
              sessionStorage.setItem("type", data.data.result[0].user_type);
              setTimeout(() => {
                this.$router.push({ name: "my" });
              }, 1000);
            } else {
              this.$vux.toast.text("账号密码有误", "middle");
            }
          },
          () => {
            this.$vux.toast.text("服务器无法连接", "middle");
          }
        );
    }
  }
};
</script>
<style>
@import "../assets/css/public.css";
@import "../assets/css/login.css";
</style>

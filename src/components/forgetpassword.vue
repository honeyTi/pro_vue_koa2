<template>
  <div>
     <header class="header clearfloat">
        <i class="return btnclick"></i>
        <span class="title ">忘记密码</span>
        <router-link class="return-login btnclick" tag="span" to="/login">登录</router-link>
    </header>
    <div class="contain-box" id="forget">

        <ul class="login_contain">
            <li class="label-li1 clearfloat">
                <label class="basic-label id_bg">账号：</label>
                <div class="basic-inputbox">
                    <input class="basic-input" type="text" value="" placeholder="请输入您的手机号">
                </div>
            </li>
            <li class="label-li1 clearfloat">
                <label class="identy_bg basic-label">验证码：</label>
                <div class="basic-inputbox">
                    <div class="clearfloat">
                        <input class="input-code" type="text" value="" placeholder="请输入您的验证码">
                        <button class="get-code" data-loading="还剩{d}秒" data-time="5">获取验证码</button>
                    </div>
                </div>
            </li>
            <li class="label-li1 clearfloat">
                <label class="basic-label password_bg">密码：</label>
                <div class="basic-inputbox">
                    <input class="basic-input" type="text" value="" placeholder="请输入您的登录密码">
                </div>
            </li>
            <li class="label-li1 label-last clearfloat">
                <label class="basic-label password_bg">密码：</label>
                <div class="basic-inputbox">
                    <input class="basic-input" type="text" value="" placeholder="请输入您的登录密码">
                </div>
            </li>
        </ul>

        <div class="login-btn">
            <button class="btn-basic btnclick">确定</button>
        </div>
    </div> 
  </div>
</template>

<script>
export default {
  name:"forgetpassword"
}
</script>
<style>
@import "../assets/css/public.css";
@import "../assets/css/login.css";
</style>



<template>
  <div>
    <header class="header clearfloat">
        <i class="return btnclick"></i>
        <span class="title">注册</span>
        <router-link class="return-login btnclick" tag="span" to="/login">登录</router-link>
    </header>
    <div class="contain-box">
        <ul class="login_contain">
            <li class="label-li1 clearfloat">
                <label class="basic-label id_bg">账号：</label>
                <div class="basic-inputbox">
                    <input id="usernameregister" v-model="tel" class="basic-input" type="text" placeholder="请输入您的手机号">
                </div>
            </li>
            <li class="label-li1 clearfloat">
                <div id="makesure" class="identy_bg basic-label">验证码：</div>
                <div class="basic-inputbox">
                    <div class="clearfloat">
                        <input id="ipt-getcode" class="input-code" type="text" v-model="num" placeholder="请输入您的验证码">
                        <button class="get-code" data-loading="还剩{d}秒" data-time="5">获取验证码</button>
                    </div>
                </div>
            </li>
            <li class="label-li1 clearfloat">
                <div class="basic-label password_bg">密码：</div>
                <div class="basic-inputbox">
                    <input id="write-password" class="basic-input"  type="password" v-model="psd" placeholder="请输入您的登录密码">
                </div>
            </li>
            <li class="label-li1 clearfloat">
                <div class="basic-label password_bg">确认密码：</div>
                <div class="basic-inputbox">
                    <input id="sure-password"  class="basic-input" type="password" placeholder="请输入您的登录密码">
                </div>
            </li>
            <li class="label-li1 label-last clearfloat">
                <div class="basic-label identity_bg">身份：</div>
                <div class="basic-inputbox input-select">
                    <div class="basic-input">
                        <group>
                            <selector v-model="select" :options="items"></selector>
                        </group>
                    </div>
                </div>
            </li>
        </ul>
        <div class="login-btn">
            <button id="register-sure" class="btn-basic click-pop" data-target-id="sure" @click="login">确定</button>
        </div>
    </div>
  </div>
</template>
<script>
    import axios from "axios";
import { setTimeout } from 'timers';

    export default {
        name:"register",
        data () {
            return {
                tel: '',
                num: '',
                psd: '',
                select: '',
                items: ['经纪人', '小业主', '运营商', '代理商', '开发商']
            }
        },
        methods: {
            login() {
                this.$vux.toast.text('注册成功', 'middle')
                axios.get('http://localhost:3000/register',{params: {
                    tel: this.tel,
                    num: this.num,
                    psd: this.psd,
                    select: this.select
                }}).then(
                    (data) => {
                        this.$vux.toast.text('注册成功', 'middle');
                        setTimeout(() => {
                            this.$router.push({name: 'login'});
                        },1000)
                    },
                    () => {
                        this.$vux.toast.text('请求失败', 'middle')
                    }
                )
            }
        }
    }
</script>

<style>
@import "../assets/css/public.css";
@import "../assets/css/login.css";
/* @import "../assets/css/login/register.css"; */
</style>



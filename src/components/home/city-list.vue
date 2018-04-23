<template>
    <div class="city-list">
        <header class="header clearfloat">
            <router-link tag="i" to="/home" class="return btnclick"></router-link>
            <span class="title">选择城市</span>
        </header>
        <div class="contain-box">
            <span class="citytext">当前定位城市</span>
            <ul>
                <!-- <router-link tag="li" to="/home" class="city-li" @click = "changeCity">{{this.city[0]}}</router-link> -->
                <li class="city-li" @click = "changeCity">{{this.city[0]}}</li>
            </ul>
            <span class="citytext">热门城市</span>
            <ul>
                <!-- <router-link tag="li" to="/home" class="city-li" @click = "changeCity">{{this.city[1]}}</router-link> -->
                <li class="city-li" @click = "changeCity">{{this.city[1]}}</li>
            </ul>
        </div>
    </div>
</template>
<script>
export default {
    name:'cityList',
    data(){
        return{
            city:['永州','长沙'],
            now: '',
        }
    },
    methods:{
        changeCity:function(e){
            this.now = e.target.innerText;
            this.$root.Hub.$emit('cityChange',this.now);
        },
    }
}
</script>
<style scoped>
@import "../../assets/css/public.css";
.city-list{
    position: fixed;
    top:100rem;
    left: 0;
    right: 0;
    bottom: 0;
    background-color: #fff;
    z-index: 2;
    height: 0;
}
.citytext{
    display: block;
    text-align: left;
    padding: .6rem;
}
    .city-li{
        background-color: #fff;
        padding: 1rem .6rem;
        text-align: left;
}
@keyframes begin{
    from {height: 0}
    to {height: 100%}
}
@keyframes end{
    from {height: 100%}
    to {height: 0}
}
</style>


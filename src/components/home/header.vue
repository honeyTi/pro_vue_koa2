<template lang="html">
    <div class="search">
		<div class="search-box">
			<div v-bind:style="{width: !panelShow ? (leftWidth || 5) + 'rem' : '0'}" class="search-left">
				<slot></slot>
			</div>
            <div class="returnBtn" :style="{display: panelShow ? 'block' : 'none'}" @click="hide"><i class="iconfont icon-fanhui"></i></div>
			<div class="search-input">
				<form action="#" onSubmit="return false">
					<i class="iconfont icon-sousuo"></i>
					<input @keyup.13="submitFn($event)" type="search"
						v-on:focus.self="show" placeholder="小区、商圈、地铁">
				</form>
			</div>
			<div :style="{width: panelShow ? '3rem' : '0'}"  class="searchBtn">搜索</div>
			<search-panel
				:style="{animation: animation + ' .6s forwards'}"
				ref="panel"></search-panel>
		</div>
</div>
</template>
<script>
import searchPanel from './search-panel.vue';

export default {
    name: 'header',
    data(){
        return {
            panelShow: null
        }
    },
    props: ['leftWidth'],
    computed: {
        animation() {
            return this.panelShow == null ? '' : this.panelShow ? 'begin' : 'end'
        }
    },
    components:{
        'search-panel' : searchPanel
    },
    methods: {
        show() {
            this.panelShow = true;
            this.$emit("showPanel",this.panelShow);
        },
        hide() {
            this.panelShow = false;
            this.$emit("showPanel",this.panelShow);
        },
        // @keyup.13
        // 键盘代码13  回车 or 搜索 按钮
        submitFn({target}) {
            if(this.$route.query.reload == 1) {
                this.$router.replace('/list?houseName=' + target.value);
                this.$router.go(0)
            } else {
                this.$router.push('/list?reload=1&houseName=' + target.value)
            }

            // this.$router.push('/list?houseName=' + target.value)
            //this.$router.go({name: 'user', params: {userId: 1}});
        }
    },
    // vue-router 导航钩子
    beforeRouteLeave(){

    }
}
</script>

<style scoped>
@import "../../assets/css/home/header.css";
</style>



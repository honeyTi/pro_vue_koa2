<template lang="html">
    <!--底部-->
	<footer class="footer">
		<ul class="footer-nav">
			<a to="" v-for="(item,index) in list" @click="routeTo(item)">
				<li class="btnclick" v-if="index === 2">
					<i class="icon-footer-middle">
						<img :src="item.imgUrl" class="icon-footer-middle"></img>
					</i>
				</li>
				<li class="btnclick" v-else>
					<i class="icon-footer">	
						<img :src="item.imgUrl" class="icon-footer"></img>
					</i>
					<span class="click-color">{{item.name}}</span>
				</li>
			</a>
		</ul>
	</footer>
</template>

<script>
export default {
	name:"footer",
	data(){
      return {
		  isClick : false,
		  currentLink: '',
		  list: [
					{
						link:'/home',
						imgUrl:require('../../assets/images/footer-nav/bottom_nor_icon04@2x.png'),
						changeUrl:require('../../assets/images/footer-nav/bottom_press_icon04@2x.png'),
						name:'首页'
					},
					{
						link:'/meeting',
						imgUrl:require('../../assets/images/footer-nav/bottom_nor_icon03@2x.png'),
						changeUrl:require('../../assets/images/footer-nav/bottom_press_icon03@2x.png'),
						name:'预约'
						},
					{
						link:'/announce',
						imgUrl:require('../../assets/images/footer-nav/bottom_icon05@2x.png'),
						name:''},
					{
						link:'/message',
						imgUrl:require('../../assets/images/footer-nav/bottom_nor_icon02@2x.png'),
						changeUrl:require('../../assets/images/footer-nav/bottom_press_icon02@2x.png'),
						name:'信息'},
					{
						link:'/my',
						imgUrl:require('../../assets/images/footer-nav/bottom_nor_icon01@2x.png'),
						changeUrl:require('../../assets/images/footer-nav/bottom_press_icon01@2x.png'),
						name:'我'
						},
				],
	  }
    },
	methods:{
		routeTo:function(item){
			this.$router.push(item.link);
			console.log(item.link);
			this.isClick = true;
		}
	},
  
}
</script>

<style>
@import '../../assets/css/home/footer.css';
.clickColor{
	color: orangered;
}
</style>



<template>
    <!-- <div id="map" class="map"></div> -->
    <baidu-map class="bm-view" :center="center" :zoom="12">
        <bm-geolocation anchor="BMAP_ANCHOR_BOTTOM_RIGHT" :showAddressBar="true" :autoLocation="true"
        @locationSuccess="getCityName"></bm-geolocation>
  </baidu-map>
</template>

<script>
// import BMap from 'BMap'

export default {
    name:'map',
    data() {
        return {
            cityName:'',
            center:'长沙',
        }
    },
     created(){
        this.$root.Hub.$on('cityChange',value =>{
        this.print(value);
        })
    },
    mounted(){
    },
    methods:{
        getCityName:function(res){
            this.cityName = res.addressComponent.city;
            this.$emit("cityName",this.cityName.substr(0,2));
        },
        print:function(value){
            console.log('点击的是——'+value);
            this.center = value;
            console.log('定位的是——'+this.center);
        }
    }
    
}
</script>

<style>
/* 地图的基本配置 */
 html {
    height: 100%
}
body {
    height: 100%;
    margin: 0;
    padding: 0;
} 
/*#map {
    height: 100%;
}*/
 /* 去掉地图左下角的百度LOGO */  
.anchorBL {  
    display:none  
} 
.bm-view {
  /* width: 100%; */
  height: 100%;
}
</style>


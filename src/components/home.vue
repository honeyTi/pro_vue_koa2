<template>
  <div class="page-box">
    <header-search  v-on:showPanel = "result">
          <template>
            <router-link tag="span" to="/cityList">
              <span>{{this.city}}</span>
              <i class="iconfont icon-xiala"></i>
            </router-link>
          </template>
    </header-search>
      <div class="page-box" :style="{ opacity : this.shadow ? 0.1 : 1}" >
        <bmap v-on:cityName = "getCityName" v-bind:cityChange="city"></bmap>
        <tools></tools>
        <footer-nav></footer-nav>
      </div>
  </div>
</template>

<script>
import header from "./home/header.vue";
import bmap from "./home/map.vue";
import footer from "./home/footer.vue";
import tools from "./tools/tools.vue";

export default {
  name: "home",
  data() {
    return {
      shadow: "",
      isClick: "",
      city: "长沙"
    };
  },
  components: {
    "header-search": header,
    bmap: bmap,
    "footer-nav": footer,
    tools: tools
  },
  methods: {
    result: function(data) {
      this.shadow = data;
    },
    getCityName: function(data) {
      this.city = data;
    }
  },
  mounted: function () {
    console.log(this.$route.params.city);
    if (this.$route.params.city !== undefined) {
      this.city = this.$route.params.city;
      this.getCityName(this.city);
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style>
@import "../assets/css/public.css";
@import "../assets/css/font.css";
</style>

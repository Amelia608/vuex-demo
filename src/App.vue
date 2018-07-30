<template>
  <div id="app">
    <span>{{count}}</span>
    <div v-show="headShow">
      <h3>我是头部信息</h3>
    </div>
    <button @click="showHeader">显示头部</button>
    <button @click="hideHeader">隐藏头部</button>
  </div>
</template>

<script>
import { mapGetters, mapActions } from "vuex";
export default {
  name: "app",
  data() {
    return {
      msg: "Welcome to Your Vue.js App",
      count: 0
    };
  },
  computed: mapGetters(["headShow", "loading", "footerShow"]),
  mounted() {},
  methods: {
    showHeader() {
      this.$store.dispatch("HEAD_SHOW_SUCCESS1");
    },
    hideHeader() {
      this.$store.dispatch("SHOW_HEAD_FAIL1");
    }
  }
};
</script>

<style lang="scss">
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>

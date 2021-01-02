<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png" />
    <div>微信导航组件练习</div>
    <div class="navbars">
      <nav-bar></nav-bar>
      <nav-bar :obj="noRightMenu"></nav-bar>
      <nav-bar :obj="customBg" :bg="bg"></nav-bar>
      <nav-bar :obj="customMid">
        <tab-bar slot="mid"></tab-bar>
      </nav-bar>
      <nav-bar :obj="customRight">
        <img src="../src/assets/logo.png" alt slot="right" class="rightIcon" />
      </nav-bar>
    </div>
  </div>
</template>

<script>
import NavBar from "@/components/NavBar.vue";
import TabBar from "@/components/TabBar.vue";
export default {
  name: "App",
  components: {
    NavBar,
    TabBar
  },
  data() {
    return {
      noRightMenu: {
        title: "不带右边菜单导航条",
        hasRight: false
      },
      customRight: {
        title: "自定义右边菜单导航条",
        hasRight: false
      },
      customBg: {
        title: "自定义背景导航条",
        hasRight: false
      },
      customMid: {
        title: "自定义标题位置导航条",
        hasRight: false,
        noTitle: true
      },
      bg: {
        background: "#f40",
        borderBottom: "2px #999 solid"
      }
    };
  }
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.navbars {
  width: 800px;
  height: auto;
  background: #a7b0b9;
}
.rightIcon {
  width: 50px;
  height: 50px;
}
.tabbar {
  width: 60%;
}
</style>

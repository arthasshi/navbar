<template>
  <div class="container" :style="bg">
    <div class="back" v-html="'<'"></div>
    <div class="title" v-show="!obj.noTitle">{{obj.title}}</div>
    <div class="mid">
      <slot name="mid"></slot>
    </div>
    <div class="menu" v-if="obj.hasRight">。。。</div>
    <div class="right">
      <slot name="right"></slot>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    obj: {
      type: Object,
      default: () => {
        return {
          title: "默认标题导航条",
          hasRight: true,
          noTitle: false
        };
      }
    },
    bg: {
      type: Object,
      default: () => {
        return {
          background: "#fff",
          borderBottom: "1px #f5f5f5 solid"
        };
      }
    }
  }
};
</script>

<style scoped>
.container {
  widows: 100%;
  height: 88px;
  position: relative;
}
.back {
  position: absolute;
  left: 0;
  top: 0;
  height: 88px;
  width: 120px;
  font-size: 26px;
  line-height: 88px;
  text-align: center;
}
.title {
  height: 88px;
  width: 100%;
  position: absolute;
  left: 0;
  top: 0;
  line-height: 88px;
  text-align: center;
}
.menu {
  position: absolute;
  right: 0;
  top: 0;
  height: 88px;
  width: 120px;
  line-height: 88px;
  text-align: center;
}
.right {
  position: absolute;
  right: 0;
  top: 0;
  height: 88px;
  width: 120px;
  display: flex;
  flex-direction: row;
  justify-content: center;
  align-items: center;
}
.mid {
  height: 88px;
  width: 100%;
  position: absolute;
  left: 0;
  top: 0;
  display: flex;
  flex-direction: row;
  justify-content: center;
  align-items: center;
}
</style>
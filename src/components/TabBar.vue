<template>
  <div class="container">
    <div
      class="def-item"
      @click="current=index"
      :class="{'active-item':index==current}"
      v-for="(item,index) in tabs"
      :key="index"
    >{{item}}</div>
  </div>
</template>

<script>
export default {
  props: {
    tabs: {
      type: Array,
      default: () => {
        return ["tab1", "tab2"];
      }
    }
  },
  data() {
    return {
      current: 0
    };
  }
};
</script>

<style  scoped>
.container {
  width: auto;
  height: auto;
  display: flex;
  flex-direction: row;
  justify-content: space-around;
  align-items: center;
  background: burlywood;
  border-radius: 8px;
}
.def-item {
  font-size: 20px;
  border-radius: 8px;
  width: 50%;
  padding: 10px;
}
.active-item {
  background: #f40;
  color: #fff;
}
</style>
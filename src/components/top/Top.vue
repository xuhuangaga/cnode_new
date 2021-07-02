<template>
  <div>
    <div class="header">
      <div class="header-box w1100 m-auto flex-j-between a-center">
        <!-- 使用头部左边组件 -->
        <TopLeft></TopLeft>
        <!-- 使用头部右边组件 -->
        <TopRight></TopRight>
      </div>
    </div>
  </div>
</template>

<script>
//引入头部左边组件
import TopLeft from "../topleft/TopLeft";
//引入头部右边组件
import TopRight from "../topright/TopRight";
export default {
  name: "",
  props: {},
  data() {
    return {};
  },
  components: {
    //注册头部左边组件
    TopLeft,
    //注册头部右边组件
    TopRight
  },
  methods: {},
  mounted() {},
  computed: {},
  watch: {}
};
</script>

<style lang='scss' scoped>
/* 头部 */
.header {
  background-color: rgb(68, 68, 68);
  .header-box {
    height: 50px;
  }
}

</style>
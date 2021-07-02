<template>
  <div class="container">
    <!-- 头部组件 -->
    <Top></Top>
    <!-- 中部组件 -->
    <Content></Content>
    <!-- 底部组件 -->
    <Bottom></Bottom>
  </div>
</template>

<script>
//引入头部组件
import Top from "../components/top/Top";
//引入中部组件
import Content from "../components/content/Content";
//引入底部组件
import Bottom from '../components/bottom/Bottom'
export default {
  name: "",
  props: {},
  data() {
    return {};
  },
  components: {
    //注册组件
    Top,
   Content,
   Bottom
  },
  methods: {},
  mounted() {},
  computed: {},
  watch: {}
};
</script>

<style lang='scss' scoped>
/* 容器div */
.container {
  margin: 0 auto;
  width: 1350px;
  min-width: 1124px;
  max-width: 100%;
  height: 100%;
}
</style>

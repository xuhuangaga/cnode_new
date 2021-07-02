<template>
  <div>
    <div class="flex-j-between header-r f-c-c m-r10 f-size14">
      <div class="home">首页</div>
      <div>新手入门</div>
      <div>API</div>
      <div>关于</div>
      <div>注册</div>
      <div class="login" id="head_logindv">登录</div>
    </div>
  </div>
</template>

<script>
export default {
  name: "",
  props: {},
  data() {
    return {};
  },
  components: {},
  methods: {},
  mounted() {},
  computed: {},
  watch: {}
};
</script>

<style lang='scss' scoped>
/* 头部右边盒子 */
.header-r {
  width: 400px;
  div {
    cursor: pointer;
  }

  div:hover {
    color: #fff;
  }
}
</style>
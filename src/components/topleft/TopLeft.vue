<template>
  <div>
    <div class="header-l">
      <div class="flex-j-between">
        <div class="header-l-img">
          <img
            src="../../assets/images/cnodejs_light.svg"
            class="c-hand home"
          />
        </div>
        <div class="p-relative">
          <i class="iconfont icon-sousuo f-w-bold"></i>
          <input type="text" id="ipt" />
        </div>
      </div>
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
/* 头部左边盒子 */
.header-l {
  width: 420px;
  .flex-j-between {
    /* logo盒子 */
    .header-l-img {
      width: 120px;
      /* logo图片 */
      img {
        width: auto;
      }
    }
  }

  /* 顶部输入框 */
  .p-relative {
    // 搜索图标
    .icon-sousuo {
      color: rgb(89, 90, 89) !important;
      position: absolute;
      left: 6px;
      top: 5px;
    }
    #ipt {
      width: 230px;
      background-color: rgb(136, 136, 136);
      border: none;
      outline: none;
      height: 30px;
      border-radius: 20px;
      padding: 5px 5px 5px 24px;
      height: 20px;
      color: #666;
    }

    /* 顶部输入框hover效果 */
    #ipt:hover {
      background-color: #fff;
    }
  }
}
</style>
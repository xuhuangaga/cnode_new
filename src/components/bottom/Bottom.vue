<template>
  <div>
    <!-- 底部 -->
    <div class="footer bg-c-w m-t20 f-size14 p-b20">
      <div class="w1100 m-auto">
        <div class="flex a-center f-title">
          <div>RSS</div>
          <div class="sx m-l10 m-r10 f-c-c"></div>
          <div>源码地址</div>
        </div>
        <div class="m-t">
          CNode 社区为国内最专业的 Node.js 开源技术社区，致力于 Node.js
          的技术研究。
        </div>
        <div class="m-t">
          服务器搭建在<img src="../../assets/images/digitalocean.png" class="c-hand" />
          ，存储赞助商为<img src="../../assets/images/qiniu.png" class="c-hand" />
        </div>

        <div class="m-t">
          新手搭建 Node.js 服务器，推荐使用无需备案的
          <a class="f-a t-d-none c-hand"
            >DigitalOcean(https://www.digitalocean.com/)</a
          >
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
.footer {
  color: rgb(119, 128, 135);
  .sx {
    height: 16px;
  }
  .m-auto {
    .f-title {
      color: rgb(102, 102, 102);
    }
    .m-t {
      margin-top: 6px;
      .f-a {
        color: rgb(0, 151, 219);
      }

      .f-a:hover {
        color: rgb(0, 85, 128);
        text-decoration: underline;
      }
    }
  }
}
</style>
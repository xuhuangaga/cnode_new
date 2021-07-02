<template>
  <div>
    <!-- 中部右边 -->
    <div class="middle-r">
      <div class="middle-r-dv1 p-t20 p-l-r10 p-b10 bg-c-w">
        <div class="f-size16">CNode：Node.js专业中文社区</div>
        <div class="f-size14 m-t20 flex">
          您可以
          <div class="log-reg login c-hand">登录</div>
          或
          <div class="log-reg login c-hand">注册</div>
          ,也可以
        </div>
        <div v-if="username" class=" f-size14 m-t10">
          用户名:{{ username }}
          <div class="github f-c-w t-a-center m-t10 c-hand" @click="signOut">
            退出登录
          </div>
        </div>
        <div v-else class="github f-c-w t-a-center m-t10 c-hand" @click="login">
          通过 GitHub 登录
        </div>
      </div>
      <div class="p-10 topic b-t-lr-r-5 f-size14 m-t10">
        无人回复的问题
      </div>
      <div class="topic-dv p-10 bg-c-w f-size14">
        <div class="sl-one c-hand">使用 Socket.IO 进行授权和握手</div>
        <div class="sl-one c-hand">
          是否可以使用nginx转发websocket实现Node远程调试？
        </div>
        <div class="sl-one c-hand">
          typescript+nodejs报错：Cannot redeclare block-scoped variable.....
        </div>
        <div class="sl-one c-hand">现在firefox的更新是不是在更新tab?</div>
        <div class="sl-one c-hand">web如何检测Ipad上safari处于分屏模式</div>
      </div>
      <div class="p-10 topic b-t-lr-r-5 f-size14 m-t10">
        积分榜 TOP 100 >>
      </div>
      <div class="topic-dv p-10 bg-c-w f-size14">
        <div class="flex">
          <div>22720</div>
          <div class="m-l10">
            <div class="t-d-none integral c-hand">i5ting</div>
          </div>
        </div>
        <div class="flex">
          <div>15840</div>
          <div class="m-l10">
            <div class="t-d-none integral c-hand">alsotang</div>
          </div>
        </div>
        <div class="flex">
          <div>10045</div>
          <div class="m-l10">
            <div class="t-d-none integral c-hand">atian25</div>
          </div>
        </div>
        <div class="flex">
          <div>9350</div>
          <div class="m-l10">
            <div class="t-d-none integral c-hand">leapon</div>
          </div>
        </div>
        <div class="flex">
          <div>8780</div>
          <div class="m-l10">
            <div class="t-d-none integral c-hand">jiyinyiyong</div>
          </div>
        </div>
        <div class="flex">
          <div>7800</div>
          <div class="m-l10">
            <div class="t-d-none integral c-hand">yakczh</div>
          </div>
        </div>
        <div class="flex">
          <div>6855</div>
          <div class="m-l10">
            <div class="t-d-none integral c-hand">im-here</div>
          </div>
        </div>
        <div class="flex">
          <div>6135</div>
          <div class="m-l10">
            <div class="t-d-none integral c-hand">DevinXian</div>
          </div>
        </div>
        <div class="flex">
          <div>5815</div>
          <div class="m-l10">
            <div class="t-d-none integral c-hand">chapgaga</div>
          </div>
        </div>
        <div class="flex">
          <div>5375</div>
          <div class="m-l10">
            <div class="t-d-none integral c-hand">magicdawn</div>
          </div>
        </div>
      </div>
      <div class="p-10 topic b-t-lr-r-5 f-size14 m-t10">
        友情社区
      </div>
      <div class="friend-comm-dv p-10 bg-c-w">
        <div class="c-hand friend-comm">
          <img src="../../assets/images/ruby-china-20150529.png" />
        </div>
        <div class="c-hand friend-comm m-t-b10">
          <img src="../../assets/images/golangtc-logo.png" alt="" />
        </div>
        <div class="c-hand friend-comm">
          <img src="../../assets/images/phphub-logo.png" alt="" />
        </div>
      </div>
      <div class="p-10 topic b-t-lr-r-5 f-size14 m-t10">
        客户端二维码
      </div>
      <div class="p-10 bg-c-w">
        <div class="t-a-center">
          <img
            src="//static.cnodejs.org/FtG0YVgQ6iginiLpf9W4_ShjiLfU"
            width="200px"
            height="200px"
          />
        </div>

        <div class="c-hand integral f-size14 t-a-center">客户端源码地址</div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "",
  props: {},
  data() {
    return {
      username: ""
    };
  },
  components: {},
  methods: {
    //登录
    login() {
      localStorage.setItem("username", "admin");
      this.username = localStorage.getItem("username");
    },
    //退出登录
    signOut() {
      localStorage.removeItem("username");
      this.username = "";
    }
  },
  mounted() {
    this.username = localStorage.getItem("username");
  },
  computed: {},
  watch: {}
};
</script>

<style lang='scss' scoped>
.topic {
  background-color: rgb(246, 246, 246);
}

.topic-dv div {
  height: 30px;
  color: rgb(119, 128, 135);
}

.middle-r {
  width: 300px;
  color: rgb(51, 51, 51);
  .middle-r-dv1 {
    .flex {
      #userName {
        color: #778087;
      }
    }
    .remark {
      font-style: italic;
    }
  }
  .middle-r-dv1 {
    .log-reg {
      color: rgb(119, 144, 185);
      text-decoration: none;
      margin: 0px 4px;
    }

    .log-reg:hover {
      text-decoration: underline;
    }
    .github {
      background-color: rgb(91, 192, 222);
      width: 150px;
      border-radius: 3px;
      height: 34px;
      line-height: 34px;
    }

    .github:hover {
      background-color: rgb(47, 150, 180);
    }
    .topic-dv {
      .integral {
        color: rgb(119, 128, 135);
      }

      .integral:hover {
        text-decoration: underline;
      }
    }
  }

  .friend-comm-dv {
    .friend-comm {
      img {
        width: 150px;
        height: 100%;
      }
    }
  }
}
</style>
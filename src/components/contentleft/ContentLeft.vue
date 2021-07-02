<template>
  <div>
    <!-- 中部左边 -->
    <div class="middle-l">
      <div class="middle-l-box flex f-size14 a-center b-t-lr-r-5">
        <div class="tab c-hand" v-for="(item,index) in arr" :key="index" :class="{'tab-active':num===index}" @click="tabItem(index)">
          {{item.name}}
          </div>
      </div>
      <div class="bg-c-w middle-c" id="topic">
        <div v-if="list.length === 0" class="t-a-center p-tb20 f-size14">
          加载中...
        </div>
        <template v-else>
          <div
            v-for="(item, index) in list"
            class="flex-j-between a-center topic_dv"
          >
            <div class="middle-c-l flex a-center">
              <div><img class="head-pic" :src="item.author.avatar_url" /></div>
              <div class="flex num_dv">
                <div class="reading-volume" title="回复数">
                  {{ item.reply_count }}
                </div>
                <div class="slash">/</div>
                <div class="visits" title="点击数">{{ item.visit_count }}</div>
              </div>
              <div v-if="item.top === true">
                <div class="tips">置顶</div>
              </div>
              <div v-else>
                <div v-if="item.tab === 'share'" class="tips1">分享</div>
                <div v-else class="tips1">问答</div>
              </div>
              <div class="topic-title" data="" :title="item.title">
                {{ item.title }}
              </div>
            </div>
            <div class="middle-c-r">
              <div class="comment-date">
                {{ getTime(item.last_reply_at, new Date()) }}
              </div>
            </div>
          </div>
        </template>
      </div>
    </div>
  </div>
</template>

<script>
import axios from "axios";
import dayjs from "dayjs";
export default {
  name: "",
  props: {},
  data() {
    return {
      list: [],
      arr:[
        {
          name:'全部'
        },
         {
          name:'精华'
        },
         {
          name:'分享'
        },
         {
          name:'问答'
        },
         {
          name:'招聘'
        },
         {
          name:'客户端测试'
        },
      ],
      num:0
    };
  },
  components: {},
  methods: {
    //判断时间是在多少秒 多少分 多少时......之前
    getTime(a, b) {
      let minute = 1000 * 60;
      let hour = minute * 60;
      let day = hour * 24;
      let week = day * 7;
      let month = day * 30;
      let year = month * 12;
      let time1 = dayjs(b).valueOf(); //当前的时间戳
      let time2 = dayjs(a).valueOf(); //指定时间的时间戳
      let time = time1 - time2;

      let result = null;
      if (time < 0) {
        result = "--";
      } else if (time / year >= 1) {
        result = parseInt(time / year) + "年前";
      } else if (time / month >= 1) {
        result = parseInt(time / month) + "个月前";
      } else if (time / week >= 1) {
        result = parseInt(time / week) + "周前";
      } else if (time / day >= 1) {
        result = parseInt(time / day) + "天前";
      } else if (time / hour >= 1) {
        result = parseInt(time / hour) + "小时前";
      } else if (time / minute >= 1) {
        result = parseInt(time / minute) + "分钟前";
      } else {
        result = "刚刚";
      }
      return result;
    },
    //获取数据
    getDate() {
      axios
        .get("https://cnodejs.org/api/v1/topics")
        .then(res => {
          // console.log(res);
          if (res.status === 200) {
            this.list = res.data.data;
          }
        })
        .catch(err => {
          console.log(`请求失败.${err}`);
        });
    },
    //tab切换
    tabItem(index){
      this.num = index
    }
  },
  mounted() {
    this.getDate();
  },
  computed: {},
  watch: {}
};
</script>

<style lang='scss' scoped>
.middle-l {
  width: 780px;
  border-radius: 5px;
  .middle-l-box {
    background-color: rgb(246, 246, 246);
    height: 40px;
    .tab {
      color: rgb(128, 189, 1);
      padding: 3px 6px;
      border-radius: 5px;
      margin-left: 20px;
    }

    .tab:hover {
      color: rgb(0, 85, 128);
    }
    .tab-active {
      color: #fff;
      background-color: rgb(128, 189, 1);
    }

    .tab-active:hover {
      color: #fff;
    }
  }
  .middle-c {
    .topic_dv {
      padding: 10px;
      font-size: 14px;
      border-top: 1px solid #f0f0f0;
      .middle-c-l {
        width: 700px;
        .head-pic {
          width: 30px;
          height: 30px;
          border-radius: 3px;
          cursor: pointer;
          margin-right: 6px;
        }
        .num_dv {
          width: 70px;
          text-align: center;

          .reading-volume {
            color: #9e78c0;
            font-size: 14px;
          }

          .slash {
            margin: 0 3px;
            font-size: 10px;
          }

          .visits {
            font-size: 10px;
            color: #b4b4b4;
          }
        }
        .tips {
          background: #80bd01;
          padding: 2px 4px;
          color: #fff;
          font-size: 12px;
          border-radius: 3px;
          margin-left: 3px;
        }

        .tips1 {
          background: rgb(229, 229, 229);
          padding: 2px 4px;
          color: rgb(153, 153, 153);
          font-size: 12px;
          border-radius: 3px;
          margin-left: 3px;
        }
        .topic-title {
          max-width: 70%;
          white-space: nowrap;
          display: inline-block;
          vertical-align: middle;
          font-size: 16px;
          line-height: 30px;
          text-overflow: ellipsis;
          overflow: hidden;
          margin-left: 6px;
        }

        .topic-title:hover {
          text-decoration: underline;
        }
      }
      .middle-c-r {
        .comment-date {
          color: #778087;
          font-size: 11px;
        }
      }
    }
    .topic_dv:hover {
      background-color: #f0f0f0;
    }
  }
}
</style>
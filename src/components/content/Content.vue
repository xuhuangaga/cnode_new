<template>
  <div>
    <!-- 中部 -->
    <div class="middle">
      <div class="middle-box w1100 flex-j-between m-auto p-tb20">
        <!-- 中部左边组件 -->
        <ContentLeft></ContentLeft>
        <!-- 中部右边组件 -->
       <ContentRight></ContentRight>
      </div>
    </div>
  </div>
</template>

<script>
//引入中部左边组件
import ContentLeft from '../contentleft/ContentLeft'
//引入中部右边组件
import ContentRight from '../contentright/ContentRight'
export default {
  name: '',
  props:{},
  data () {
    return {
    }
  },
  components: {
    //注册组件
    ContentLeft,
    ContentRight
  },
  methods: {},
  mounted() {},
  computed: {},
  watch: {}
}
</script>

<style lang='scss' scoped>
/* 中部 */
.middle {
  background-color: rgb(225, 225, 225);
}
</style>
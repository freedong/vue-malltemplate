<template lang="html">
    <div class="wrap">
      <v-header class="header">
        <h1 slot="title">商品分类</h1>
      </v-header>
      <section class="view">
          <!-- 侧边栏 -->
          <v-aside :datas="allData.aside" />
          <!-- 主体内容路由 -->
          <router-view :datas="allData.aside" />
      </section>
    </div>
</template>

<script>
import Header from '@/common/_header.vue'
import Aside from '@/components/category/aside.vue'
import category1111 from '@/http/mock.js' //模拟数据
export default {
  name:'Category',
  components:{
    'v-header': Header,
    'v-aside': Aside
  },
  data() {
    return {
      allData:{}
    }
  },
  created(){
    this.$api({
      method:'post',
      url:'/category'
    }).then((res) => {
      this.allData = res.data
      console.log(res.data.aside);
    }).catch((error) => {
      console.log(error)
    })
  }
}
</script>

<style lang="less" scoped>
.wrap {
  width: 100%;
  height: 100%;
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  -webkit-box-orient: vertical;
  -webkit-box-direction: normal;
  -ms-flex-flow: column nowrap;
  flex-flow: column nowrap;

  .view {
    width: 100%;
    height: 100%;
    display: -webkit-box;
    display: -ms-flexbox;
    display: flex;
  }
}
</style>

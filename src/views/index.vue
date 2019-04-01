<template lang="html">
    <!-- 在首页父组件发送http请求,后将数据通过props传递给子组件,可减少请求次数,减少服务器压力 -->
    <div class="index">
        <!-- 头部栏组件 -->
        <v-header />
        <!-- 轮播图 -->
        <v-swiper :swiperData="datas.swiper" />
        <!-- 服务 -->
        <v-service/>
        <!-- 版块一 -->
        <v-section1 :list="datas.section1.list" :banner="datas.section1.banner"></v-section1>
        <!-- 版块二 -->
        <v-section2 :list="datas.section2.list" :banner='datas.section2.banner'/>
        <!-- 版块三 -->
        <v-section3/>
        <!-- 版块四 -->
        <v-section4 :list="datas.section4.list" :banner='datas.section4.banner'/>
        <!-- 底线 -->
        <v-baseline/>
        <!-- 底部栏 -->
        <v-footer/>
    </div>
</template>

<script>
import Header from '@/components/index/header.vue'
import Swiper from '@/components/index/swiper.vue'
import Service from '@/components/index/service.vue'
import Section1 from '@/components/index/section1.vue'
import Section2 from '@/components/index/section2.vue'
import Section3 from '@/components/index/section3.vue'
import Section4 from '@/components/index/section4.vue'
import Baseline from '@/common/_baseline.vue'
import Footer from '@/common/_footer.vue'
import index from '@/http/mock.js' //模拟数据
export default {
  name:'index',
  components:{
    'v-header':Header,
    'v-swiper':Swiper,
    'v-service': Service,
    'v-section1': Section1,
    'v-section2': Section2,
    'v-section3': Section3,
    'v-section4': Section4,
    'v-baseline': Baseline,
    'v-footer': Footer
  },
  data(){
    return {
      datas:{
        swiper:[],
        section1:{},
        section2:{},
        section3:{},
        section4:{},
      }
    }
  },
  beforeCreate() {
    this.$api({
      method: 'post',
      url: '/index'
    }).then((response) => {
      this.datas = response.data;
      console.log(response);
    }).catch(function(error) {
      alert(error)
    })
  }
}
</script>

<style lang="css">
</style>

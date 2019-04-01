<template lang="html">
    <div class="car">
        <!-- slot分发内容 让子组件混合父组件的内容 -->
        <v-header>
          <h1 slot="title">购物车</h1>
        </v-header>
        <!-- 根据购物车是否有商品加载不同的组件 -->
        <!-- 有商品组件 -->
        <v-something v-if="count" />
        <!-- 无商品组件 -->
        <v-nothing v-else />
        <!-- 底部栏 -->
        <v-footer/>
    </div>
</template>

<script>
import Header from '@/common/_header.vue'
import Footer from '@/components/car/footer.vue'
import Nothing from '@/components/car/nothing.vue'
import Something from '@/components/car/something.vue'
export default {
  name:'Car',
  components:{
    'v-header':Header,
    'v-nothing':Nothing,
    'v-something':Something,
    'v-footer':Footer
  },
  computed:{
    count(){
      return this.$store.state.detail.count
    }
  },
  mounted(){
    // 防止刷新页面数据为空
    if (this.$store.state.detail.count=="") {
      this.$store.commit('RESET_COUNT')
    }
  }
}
</script>


<style lang="less" scoped>
.car {
  width: 100%;
  padding-bottom: 14vw;
}
</style>

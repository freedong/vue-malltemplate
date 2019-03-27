<template lang="html">
    <!-- 在首页父组件发送http请求,后将数据通过props传递给子组件,可减少请求次数,减少服务器压力 -->
    <div class="index">
        <!-- 头部栏组件 -->
        <v-header />
    </div>
</template>

<script>
import Header from '@/components/index/header.vue'
export default {
  name:'index',
  components:{
    'v-header':Header,
  }
}
</script>

<style lang="css">
</style>

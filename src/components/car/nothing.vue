<template lang="html">
    <div class="nothing">
        <!-- 去登陆 -->
        <v-gologin/>
        <!-- 购物车 -->
        <div class="nothing-img">
            <img src="../../assets/car/images/cart.svg" alt="">
        </div>
        <!-- 去逛逛 -->
        <router-link :to="{ name: '分类' }" class="nothing-toshop">
          <p>购物车是空的</p>
          <router-link :to="{ name: '分类' }">去逛逛</router-link>
        </router-link>
    </div>
</template>

<script>
import Gologin from '@/components/car/gologin.vue'
export default {
  name:'nothing',
  components:{
    'v-gologin': Gologin
  },
}
</script>


<style lang="less" scoped>
  .nothing {
    width: 100%;
    text-align: center;
    .nothing-img {
      text-align: center;
      background-color: rgba(251, 240, 217,0.3);

    }
    .nothing-toshop {
      display: -webkit-flex;
      display: -ms-flex;
      display: flex;
      justify-content: space-between;
      padding: 2vw 6vw;
      align-items: center;
      background-color: rgba(244, 244, 244, 0.3);
      &:active {
        background-color: #f2f2f2;
      }
       a {
         padding:1vw 2vw;
         background-color: #ffb300;
         border-radius: 1.5vw;
         color:#fff;
       }
    }
  }
</style>

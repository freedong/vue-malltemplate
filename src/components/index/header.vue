<template lang="html">
    <mt-header title="电商联盟">
        <router-link :to="{ name: '', params: {} }" slot="right">
            <mt-button icon="search"></mt-button>
        </router-link>
    </mt-header>
</template>

<script>
export default {
  name:'header',
}
</script>

<style lang="less" scoped>

</style>

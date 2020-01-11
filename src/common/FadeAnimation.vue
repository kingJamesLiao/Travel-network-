<template>
  <div>
    <transition name="heaven">
      <slot></slot>
    </transition>
  </div>
</template>

<script>
  export default {
    name:'FadeAnimation',
  }
</script>

<style lang='less' scoped>
    .heaven-enter,.heaven-leave-to{
        opacity:0;
      }
    .heaven-enter-active,.heaven-leave-active{
        transition:opacity .5s;
      }

</style>

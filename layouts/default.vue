<template>
  <div class="main-wrapper">
    <HeaderShop/>
    <slot/>
    <FooterShop/>
  </div>
</template>

<script>
import HeaderShop from '~/components/header/HeaderShop.vue'
import FooterShop from '~/components/footer/FooterShop.vue'
export default {
  components: {
    HeaderShop,
    FooterShop
  }
}
</script>

<style>
.main-wrapper {
  max-width: 1440px;
  margin: 0 auto;
}
@media screen and (max-width: 1279px){
  .main-wrapper {
    width: 100%;
  }
}
</style>

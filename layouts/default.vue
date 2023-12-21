<template>
  <div class="main-wrapper">
    <HeaderShop/>
    <Nuxt/>
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
@import '~/assets/css/fonts_family/Inter-Font.css';
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

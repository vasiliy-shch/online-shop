<template>
  <div class="main-wrapper">
    <HeaderShop/>
    <slot/>
  </div>
</template>

<script>
import HeaderShop from '../components/HeaderShop.vue'
export default {
  components: {
    HeaderShop
  }
}
</script>

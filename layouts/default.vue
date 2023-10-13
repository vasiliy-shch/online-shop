<template>
  <div>
    <slot name="header">
        <HeaderShop></HeaderShop>
    </slot>
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

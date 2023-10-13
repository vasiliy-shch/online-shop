<template>
    <div class="header">
        <HeaderLogo/>
    </div>
</template>

<script>
import HeaderLogo from '../components/HeaderLogo.vue'
export default {
  components: {
    HeaderLogo
  }
}
</script>

<style>
.header {
    display: flex;
    height: 86px;
}
</style>

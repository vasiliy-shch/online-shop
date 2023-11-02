<template>
  <div class="header__navbar">
    <HeaderMenuButton/>
    <HeaderLinks/>
    <HeaderLanguages/>
    <HeaderShip/>
  </div>
</template>

<script>
import HeaderLinks from '~/components/header/navbar/HeaderLinks.vue'
import HeaderMenuButton from '~/components/header/navbar/HeaderMenuButton.vue'
import HeaderLanguages from '~/components/header/navbar/HeaderLanguages.vue'
import HeaderShip from '~/components/header/navbar/HeaderShip.vue'
export default {
  components: {
    HeaderLinks,
    HeaderMenuButton,
    HeaderLanguages,
    HeaderShip
  }
}
</script>

<style>
.header__navbar {
    display: flex;
}
</style>

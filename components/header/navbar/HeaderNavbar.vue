<template>
  <div class="header__navbar">
    <HeaderMenuButton/>
    <HeaderLinks/>
    <HeaderLanguages/>
    <HeaderCountry/>
  </div>
</template>

<script>
import HeaderLinks from '~/components/header/navbar/HeaderLinks.vue'
import HeaderMenuButton from '~/components/header/navbar/HeaderMenuButton.vue'
import HeaderLanguages from '~/components/header/navbar/HeaderLanguages.vue'
import HeaderCountry from '~/components/header/navbar/HeaderCountry.vue'
export default {
  components: {
    HeaderLinks,
    HeaderMenuButton,
    HeaderLanguages,
    HeaderCountry
  }
}
</script>

<style>
.header__navbar {
    display: flex;
}
</style>

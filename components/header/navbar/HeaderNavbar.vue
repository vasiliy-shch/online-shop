<template>
  <div class="header__navbar">
    <HeaderMenuButton/>
    <HeaderLinks class="mobile__display_none"/>
    <HeaderLanguages class="mobile__display_none"/>
    <HeaderCountry class="mobile__display_none"/>
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
@media screen and (max-width: 879px) {
  .mobile__display_none {
      display: none;
  }
}
</style>

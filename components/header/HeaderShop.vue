<template>
  <div class="header">
    <div class="header__main">
      <div class="header__main_mobile">
        <HeaderMenuButton class="desktop__display_none"/>
        <HeaderLogo/>
        <HeaderActionIcons class="desktop__display_none"/>
      </div>
      <HeaderForm/>
      <HeaderActionIcons class="mobile__display_none"/>
    </div>
    <div class="header__rest mobile__display_none">
      <HeaderNavbar/>
    </div>
  </div>
</template>

<script>
import HeaderLogo from '~/components/header/logo/HeaderLogo'
import HeaderForm from '~/components/header/form/HeaderForm'
import HeaderActionIcons from '~/components/header/actionIcons/HeaderActionIcons.vue'
import HeaderNavbar from '~/components/header/navbar/HeaderNavbar.vue'
import HeaderMenuButton from '~/components/header/navbar/HeaderMenuButton.vue'
export default {
  components: {
    HeaderLogo,
    HeaderForm,
    HeaderActionIcons,
    HeaderNavbar,
    HeaderMenuButton
  }
}
</script>

<style scoped>
.header {
  max-width: 1440px;
  margin: 0 auto;
}
@media screen and (max-width: 879) {
  .header {
    width: 360px;
    margin: 0 auto;
  }
}
.header__main {
    display: flex;
    height: 96px;
}
@media screen and (max-width: 879px) {
  .header__main {
    align-items: center;
    flex-direction: column;
    display: flex;
  }
}
.header__rest {
  display: flex;
  height: 56px;
  border-top: 1px solid #E0E0E0;
  border-bottom: 1px solid #E0E0E0;
}
@media screen and (max-width: 879px) {
  .mobile__display_none {
    display: none;
  }
}
@media screen and (min-width: 880px) {
  .desktop__display_none {
    display: none;
  }
}
@media screen and (max-width: 879px) {
  .header__main_mobile {
    display: flex;
    width: 360px;
  }
}
</style>

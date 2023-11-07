<template>
  <div class="header">
    <div class="header__main">
      <HeaderLogo/>
      <HeaderForm/>
    </div>
    <div class="header__rest">
      <HeaderNavbar/>
    </div>
  </div>
</template>

<script>
import HeaderLogo from '~/components/header/logo/HeaderLogo'
import HeaderForm from '~/components/header/form/HeaderForm'
import HeaderNavbar from '~/components/header/navbar/HeaderNavbar.vue'
export default {
  components: {
    HeaderLogo,
    HeaderForm,
    HeaderNavbar
  }
}
</script>

<style>
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
    height: 86px;
}
@media screen and (max-width: 879px) {
  .header__main {
  display: block;
  }
}
.header__rest {
  display: flex;
  height: 56px;
  border-top: 1px solid #E0E0E0;
  border-bottom: 1px solid #E0E0E0;
}
</style>

<template>
    <div class="header__logo">
        <HeaderImage/>
        <HeaderBrand/>
    </div>
</template>

<script>
import HeaderBrand from '~/components/header/logo/HeaderBrand'
import HeaderImage from '~/components/header/logo/HeaderImage'
export default {
  components: {
    HeaderBrand,
    HeaderImage
  }
}
</script>

<style>
.header__logo {
    width: 150px;
    height: 46px;
    margin: 20px 0px 20px 131px;
    display: flex;
}
@media screen and (max-width: 879px) {
  .header__logo {
    width: 116px;
    height: 36px;
    margin: 10px 0 10px 18px;
  }
}
</style>

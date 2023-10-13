<template>
    <div class="header__logo">
    <HeaderImage/>
    <HeaderBrand/>
    </div>
</template>

<script>
import HeaderBrand from '../components/HeaderBrand.vue'
import HeaderImage from '../components/HeaderImage.vue'
export default {
  components: {
    HeaderBrand,
    HeaderImage
  },
  data () {
    return {
    }
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
</style>

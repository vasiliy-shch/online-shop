<template>
  <div class="header__form">
    <HeaderInput/>
    <HeaderFilter/>
    <HeaderButton/>
  </div>
</template>

<script>
import HeaderInput from '../../../components/header/__form/HeaderInput'
import HeaderFilter from '../__form/HeaderFilter.vue'
import HeaderButton from '../__form/HeaderButton.vue'
export default {
  components: {
    HeaderInput,
    HeaderFilter,
    HeaderButton
  }
}
</script>

<style>
.header__form {
    display: flex;
    width: 664px;
    height: 39px;
    margin: 22px 90px 24px 45px;
    border: 1px solid #0D6EFD;
    border-radius: 6px;
    box-shadow: 0 4px 4px rgba(0,0,0,0.25)
}
@media screen and (max-width: 879px) {
  .header__form {
    width: 330px;
    border: 1px solid #8B96A5;
    background-color: #EFF2F4;
    margin: 0 15px;
  }
}
</style>

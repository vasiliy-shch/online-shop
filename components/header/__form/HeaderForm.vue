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
    width: 665px;
    height: 40px;
    margin: 22px 89px 23px 46px;
    border: 1px solid #0D6EFD;
    border-radius: 6px;
}
@media screen and (max-width: 879px) {
  .header__form {
    flex-direction: row-reverse;
    width: 330px;
    border: 1px solid #8B96A5;
    background-color: #EFF2F4;
  }
}
</style>

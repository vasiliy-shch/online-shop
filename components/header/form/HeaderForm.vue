<template>
  <div class="header__form">
    <HeaderInput/>
    <HeaderFilter/>
    <HeaderButton/>
  </div>
</template>

<script>
import HeaderInput from '~/components/header/form/HeaderInput.vue'
import HeaderFilter from '~/components/header/form/HeaderFilter.vue'
import HeaderButton from '~/components/header/form/HeaderButton.vue'
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
    max-width: 664px;
    height: 39px;
    margin: 22px 90px 24px 45px;
    border: 1px solid #0D6EFD;
    border-radius: 6px;
    box-shadow: 0 4px 4px rgba(0,0,0,0.25)
}
@media screen and (max-width: 879px) {
  .header__form {
    min-width: 330px;
    max-width: 100%;
    border: 1px solid #8B96A5;
    background-color: #EFF2F4;
    margin: 0 15px;
    justify-content: space-between;
  }
}
</style>

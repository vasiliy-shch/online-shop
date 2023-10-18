<template>
  <div class="header">
    <HeaderLogo/>
    <HeaderForm/>
  </div>
</template>

<script>
import HeaderLogo from '../../components/header/__logo/HeaderLogo'
import HeaderForm from '../../components/header/__form/HeaderForm'
export default {
  components: {
    HeaderLogo,
    HeaderForm
  }
}
</script>

<style>
.header {
    display: flex;
    height: 86px;
}
@media screen and (max-width: 879px) {
  .header {
  display: block;
  }
}
</style>

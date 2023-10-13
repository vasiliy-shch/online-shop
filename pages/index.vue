<template>
  <div>
    <page slot="header"></page>
  </div>
</template>

<script>
import page from '../layouts/default'
export default {
  components: {
    page
  },
  name: 'IndexPage'
}
</script>

<style>
body {
  margin: 0;
}
</style>

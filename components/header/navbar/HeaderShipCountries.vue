<template>
    <div>
      <div
      v-for="country in countries"
      :key="country.id">
        <img :src="country.url">
      </div>
    </div>
</template>

<script>
export default {
  data () {
    return {
      countries: [
        {
          id: 1,
          name: 'Russia',
          style: 'header__ship_select russia',
          url: '/images/flags/ru.svg'
        },
        {
          id: 2,
          name: 'US of America',
          style: 'header__ship_select',
          url: '/images/flags/us.svg'
        },
        {
          id: 3,
          name: 'Italia'
        },
        {
          id: 4,
          name: 'Germany'
        },
        {
          id: 5,
          name: 'Great Britain'
        },
        {
          id: 6,
          name: 'France'
        },
        {
          id: 7,
          name: 'Denmark'
        },
        {
          id: 8,
          name: 'China'
        },
        {
          id: 9,
          name: 'Australia'
        },
        {
          id: 10,
          name: 'United Emirates'
        }
      ]
    }
  }
}
</script>

<style>

</style>

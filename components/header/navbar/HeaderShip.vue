<template>
    <div class="header__ship">
    <h2 class="header__ship_title"> Ship to </h2>
        <select class="header__ship_select">
            <option
            v-for="country in countries"
            :key="country.id"
            :class="country.style"
            :url="country.url"
            >
             {{ country.name }}
            </option>
        </select>
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
.header__ship {
    margin: 16px 0 16px 32px;
    width: 115px;
    height: 24px;
    font-size: 16px;
    font-weight: normal;
    display: flex;
    align-items: center;

}
.header__ship_title {
    font-size: 16px;
    font-weight: normal;
}
.header__ship_select {
    width: 55px;
    height: 24px;
}
.russia {
    background-image: url(~/images/flags/ru.svg);
    background-size: 22px 16px;
}
</style>

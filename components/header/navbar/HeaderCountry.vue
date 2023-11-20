<template>
<div class="header__ship_country">
    <div v-if="!isEdit">
        <div @click="show" class="ship__country_title">
          Ship to
          <img class="ship__country_image"
            :src="selectedCountry.url"
          >
          <button class="ship__country_button"></button>
        </div>
    </div>
    <div v-else-if="isEdit">
        <div @click="hide" class="ship__country_title">
          Ship to
          <img class="ship__country_image"
            :src="selectedCountry.url"
          >
          <div class="ship__country_button"></div>
        </div>
        <div class="ship__country_list">
          <div
            v-for="country in countries"
            :key="country.id"
            :class="[ 'ship__country',
              selectedCountry.id === country.id ?
              'ship__country_selected' : '' ]"
            @click="select(country)"
            >
              <span class="ship__country_titleInList">
                {{ country.name }}
              </span>
              <img class="ship__country_image" :src=country.url>
          </div>
        </div>
    </div>
</div>
</template>

<script>
export default {
  data () {
    return {
      isEdit: false,
      selectedCountry: {
        id: 1,
        url: require('~/assets/images/flags/ru.svg')
      },
      countries: [
        {
          id: 1,
          name: 'Russia',
          styles: 'ship__country_selected',
          url: require('~/assets/images/flags/ru.svg')
        },
        {
          id: 2,
          name: 'US of America',
          styles: '',
          url: require('~/assets/images/flags/us.svg')
        },
        {
          id: 3,
          name: 'Italia',
          styles: '',
          url: require('~/assets/images/flags/it.svg')
        },
        {
          id: 4,
          name: 'Germany',
          styles: '',
          url: require('~/assets/images/flags/ge.svg')
        },
        {
          id: 5,
          name: 'Great Britain',
          styles: '',
          url: require('~/assets/images/flags/gb.svg')
        },
        {
          id: 6,
          name: 'France',
          styles: '',
          url: require('~/assets/images/flags/fr.svg')
        },
        {
          id: 7,
          name: 'Denmark',
          styles: '',
          url: require('~/assets/images/flags/dk.svg')
        },
        {
          id: 8,
          name: 'China',
          styles: '',
          url: require('~/assets/images/flags/cn.svg')
        },
        {
          id: 9,
          name: 'Australia',
          styles: '',
          url: require('~/assets/images/flags/au.svg')
        },
        {
          id: 10,
          name: 'United Emirates',
          styles: 'ship__country_borderBottom',
          url: require('~/assets/images/flags/ae.svg')
        }
      ]
    }
  },
  methods: {
    show () {
      this.isEdit = true
    },
    hide () {
      this.isEdit = false
    },
    select (country) {
      this.selectedCountry = country
      this.isEdit = false
    }
  }
}
</script>

<style>
.header__ship_country {
  width: 115px;
  margin-left: 26px;
}
.ship__country_list {
  border: 1px solid #EFF2F4;
  width: 200px;
  box-shadow: 0 4px 4px rgba(0,0,0,0.25)
}
.ship__country {
  display: flex;
  justify-content: space-between;
  text-align: center;
  align-items: center;
  width: 200px;
  height: 36px;
  font-family: 'Inter';
  font-size: 16px;
  font-weight: normal;
  cursor: pointer;
}
.ship__country:hover {
  background-color: #E5F1FF;
}
.ship__country_selected {
  color: #0D6EFD;
}
.ship__country_title {
    font-family: 'Inter';
    font-size: 16px;
    font-weight: normal;
    cursor: pointer;
    display: flex;
    align-items: center;
    margin: 16px 0;
}
.ship__country_title:hover {
  opacity: 0.6;
}
.ship__country_image {
  height: 16px;
  width: 22px;
  margin-left: 6px;
}
.ship__country_button {
  background-color: white;
  border: none;
  background-image: url(~/assets/images/apperance.svg);
  width: 24px;
  height: 24px;
  background-repeat: no-repeat;
  margin-left: 9px;
  cursor: pointer;
}
.ship__country_titleInList {
  margin: 8px 0 8px 16px;
}
</style>

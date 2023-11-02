<template>
  <div class="header__ship_select-list">
    <div v-if=select>
      <HeaderShipCountry
      v-for="country in countries"
      :id="country.id"
      :name="country.name"
      :key="country.id"
      :styles="country.styles"
      :src="country.url"
      :selected="country.selected"
      @check="checked"
      />
    </div>
    <div v-else>
      <HeaderShipCountry
      v-for="country in selectedCountry"
      :id="country.id"
      :name="country.name"
      :key="country.id"
      :styles="country.styles"
      :src="country.url"
      :selected="country.selected"
      @check="checked"
      />
    </div>
  </div>
</template>

<script>
import HeaderShipCountry from '~/components/header/navbar/HeaderShipCountry.vue'
export default {
  components: {
    HeaderShipCountry
  },
  emits: ['hide'],
  props: {
    isEdit: Boolean
  },
  data () {
    return {
      countries: [
        {
          id: 1,
          name: 'Russia',
          styles: '',
          url: require('~/assets/images/flags/ru.svg'),
          selected: false
        },
        {
          id: 2,
          name: 'US of America',
          styles: '',
          url: require('~/assets/images/flags/us.svg'),
          selected: false
        },
        {
          id: 3,
          name: 'Italia',
          styles: '',
          url: require('~/assets/images/flags/it.svg'),
          selected: false
        },
        {
          id: 4,
          name: 'Germany',
          styles: '',
          url: require('~/assets/images/flags/ge.svg'),
          selected: false
        },
        {
          id: 5,
          name: 'Great Britain',
          styles: '',
          url: require('~/assets/images/flags/gb.svg'),
          selected: false
        },
        {
          id: 6,
          name: 'France',
          styles: '',
          url: require('~/assets/images/flags/fr.svg'),
          selected: false
        },
        {
          id: 7,
          name: 'Denmark',
          styles: '',
          url: require('~/assets/images/flags/dk.svg'),
          selected: false
        },
        {
          id: 8,
          name: 'China',
          styles: '',
          url: require('~/assets/images/flags/cn.svg'),
          selected: false
        },
        {
          id: 9,
          name: 'Australia',
          styles: '',
          url: require('~/assets/images/flags/au.svg'),
          selected: false
        },
        {
          id: 10,
          name: 'United Emirates',
          styles: '',
          url: require('~/assets/images/flags/ae.svg'),
          selected: false
        }
      ],
      selectedCountry: [],
      select: true
    }
  },
  methods: {
    checked (id) {
      this.countries = this.countries.map((country) => {
        if (country.id === id) {
          country.styles = 'ship__country_selected'
          country.selected = true
          this.select = false
          this.$emit('hide')
          console.log(country.id)
        } else {
          country.styles = ''
          country.selected = false
        }
        return country
      })
      this.selectedCountry = this.countries.filter((country) => {
        return country.id === id
      })
    }
  }
}
</script>

<style scoped>
.header__ship_select-list {
    cursor: pointer;
    width: 200px;
    margin-top: 5px;
    border: 1px solid #EFF2F4;
    border-top: none;
}
/* .header__ship_select:hover {
    background-color: #E5F1FF;
} */
</style>

<template>
    <div>
      {{ isEdit }}
     <div class="header__ship" v-if="isEdit">
      <h2 class="header__ship_title" @click="show"> Ship to  </h2>
      <HeaderShipCountriesList
      :isEdit="isEdit"
      />
     </div>
     <div v-else>
      <div>
        <h2 class="header__ship_title" @click="show"> Ship  </h2> 
      </div>
     </div>
    </div>
</template>

<script>
import HeaderShipCountriesList from '~/components/header/navbar/HeaderShipCountriesList.vue'
export default {
  components: {
    HeaderShipCountriesList
  },
  data () {
    return {
      isEdit: false
    }
  },
  methods: {
    show: function () {
      this.isEdit = true
    },
    hide: function () {
      this.isEdit = false
    }
  }
}
</script>

<style scoped>
.header__ship {
    margin: 16px 0 16px 32px;
    width: 115px;
    height: 24px;
    font-size: 16px;
    font-weight: normal;
    display: block;
    align-items: center;

}
.header__ship_title {
    font-family: 'Inter';
    font-size: 16px;
    font-weight: normal;
}
.header__ship_select {
    width: 55px;
    height: 24px;
}
</style>

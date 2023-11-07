<template>
  <select class="header__filter">
    <option
    class="header__category"
    v-for="category in categorys"
    :key="category.id"
    >
        {{ category.name }}
    </option>
  </select>
</template>

<script>
export default {
  data () {
    return {
      categorys: [
        {
          id: 1,
          name: 'All category'
        },
        {
          id: 2,
          name: 'home'
        },
        {
          id: 3,
          name: 'electronic'
        },
        {
          id: 4,
          name: 'computer'
        },
        {
          id: 5,
          name: 'animals'
        },
        {
          id: 6,
          name: 'automobile'
        },
        {
          id: 7,
          name: 'sports'
        }
      ]
    }
  }
}
</script>

<style>
.header__filter {
    font-family: 'Inter';
    font-size: 16px;
    width: 145px;
    height: 39px;
    outline: none;
    border: none;
    border-left: 1px solid #0D6EFD;
    background-color: white;
    padding: 10px 7px 10px 7px;
    appearance: none;
    background-image: url('~/assets/images/apperance.svg');
    background-repeat: no-repeat;
    background-position-x: calc(100% - 8px);
    background-position-y: calc(100% - 8px);
}
.header__category {
    width: 140px;
    height: 19px;
    cursor: pointer;
    font-size: 16px;
}
@media screen and (max-width: 879px) {
    .header__filter {
        display: none;
    }
}
</style>

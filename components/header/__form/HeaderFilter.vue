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
          name: 'all category'
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
          name: 'sports and outdoor'
        }
      ]
    }
  }
}
</script>

<style>
.header__filter {
    width: 145px;
    height: 40px;
    outline: none;
    border: none;
    border-left: 1px solid #0D6EFD;
    background-color: white;
    padding: 11px 5px 10px 10px;
}
.header__category {
    cursor: pointer;
    font-size: 16px;
}
@media screen and (max-width: 879px) {
    .header__filter {
        display: none;
    }
}
</style>

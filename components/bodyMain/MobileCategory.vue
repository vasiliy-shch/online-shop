<template>
  <div class="mobileCategories">
    <a
    class="mobileCategory"
    v-for="category in categories"
    :href="category.href"
    :key="category.id"
    >
      <span class="mobileCategory__title">{{ category.name }}</span>
    </a>
  </div>
</template>

<script>
export default {
  data () {
    return {
      categories: [
        {
          id: 1,
          name: 'All category',
          href: '#'
        },
        {
          id: 2,
          name: 'Gadgets',
          href: '#'
        },
        {
          id: 3,
          name: 'Clothes',
          href: '#'
        },
        {
          id: 4,
          name: 'Accessories',
          href: '#'
        },
        {
          id: 5,
          name: 'Phones',
          href: '#'
        },
        {
          id: 6,
          name: 'Laptops',
          href: '#'
        }
      ]
    }
  }
}
</script>

<style>
.mobileCategories {
  display: none;
}
@media screen and (max-width: 879px) {
  .mobileCategories {
    font-family: 'Inter';
    display: flex;
    height: 36px;
    margin: 16px 0 0 16px;
    max-width: 879px;
    overflow-x: scroll;
  }
}
.mobileCategory {
  display: flex;
  max-width: 120px;
  text-decoration: none;
  color: #0D6EFD;
  background-color: #EFF2F4;
  border-radius: 6px;
  margin-right: 4px;
  box-shadow: 0 4px 4px rgba(0,0,0,0.25);
  align-items: center;
  padding: 9px 2.055% 8px;
  font-size: 16px;
  line-height: 19px;
  font-weight: 400;
  white-space: nowrap;
}
.mobileCategory__title {
  display: flex;
}
</style>

<template>
  <swiper 
    class="mobileCategories"
    :slidesPerView="3.5"
    :breakpoints="breakpoints"
    :slideShadows="true"
  >
    <swiper-slide 
      v-for="category in categories"
      :key="category.id"
    >
      <a
        class="mobileCategory"
        :href="category.href"
      >
        <span class="mobileCategory__title">{{ category.name }}</span>
      </a>
    </swiper-slide>
  </swiper>
</template>

<script>
import { Swiper, SwiperSlide } from 'swiper/vue';
export default {
  components: {
    Swiper,
    SwiperSlide
  },
  data () {
    return {
      breakpoints: {
        480: {
          slidesPerView: 4.5
        },
        600: {
          slidesPerView: 6
        },
      },
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
@import 'swiper/css';
.mobileCategories {
  display: none;
}
@media screen and (max-width: 879px) {
  .mobileCategories {
    font-family: 'Inter';
    display: flex;
    height: 40px;
    margin: 16px 0 0 16px;
    max-width: 879px;
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

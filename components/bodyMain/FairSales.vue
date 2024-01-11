<template>
  <section class="fairSales">
    <div class="fairSales__calendar">
      <div class="fairSales__calendarTextBlock">
        <h3 class="fairSales__title"> Deals and offers </h3>
        <span class="fairSales__subtitle"> Hygiene equipments </span>
      </div>
      <FairSalesCounter/>
    </div>
    <swiper
      class="fairSales__cards"
      :slidesPerView="2.5"
      :breakpoints="breakpoints"
      :modules="modules"
      :pagination="{
        clickable: true,
      }"
    >
      <swiper-slide
        v-for="card in saleCards"
        :key="card.id"
        :href="card.href"
      >
        <a class="fairSales__card">
          <img class="fairSales__cardImage" :src="card.image">
          <span class="fairSales__cardTitle">{{ card.name }}</span>
          <span class="fairSales__cardPercent"> -{{ card.sale }}% </span>
        </a>
      </swiper-slide>
    </swiper>
  </section>
</template>

<script>
import FairSalesCounter from '~/components/bodyMain/FairSalesCounter.vue'
import smartWatch from '~/assets/images/bodyMain/cards/smartWatch.svg'
import laptops from '~/assets/images/bodyMain/cards/laptops.svg'
import goProCameras from '~/assets/images/bodyMain/cards/goProCameras.svg'
import gamingHeadphones from '~/assets/images/bodyMain/cards/gamingHeadphones.svg'
import canonCameras from '~/assets/images/bodyMain/cards/canonCameras.svg'
import { Swiper, SwiperSlide } from 'swiper/vue';
import { Grid, Pagination } from 'swiper/modules';
export default {
  components: {
    FairSalesCounter,
    Swiper,
    SwiperSlide
  },
  setup () {
    return {
      modules: [ Grid, Pagination ],
    };
  },
  data () {
    return {
      breakpoints: {
        420: {
          slidesPerView: 3,
        },
        560: {
          slidesPerView: 4,
        },
        700: {
         slidesPerView: 5,
        }
      },
      saleCards: [
        {
          id: 1,
          name: 'Smart watches',
          image: smartWatch,
          sale: 25,
          href: '#'
        },
        {
          id: 2,
          name: 'Laptops',
          image: laptops,
          sale: 15,
          href: '#'
        },
        {
          id: 3,
          name: 'GoPro cameras',
          image: goProCameras,
          sale: 40,
          href: '#'
        },
        {
          id: 4,
          name: 'Headphones',
          image: gamingHeadphones,
          sale: 25,
          href: '#'
        },
        {
          id: 5,
          name: 'Canon cameras',
          image: canonCameras,
          sale: 25,
          href: '#'
        }
      ]
    }
  }
}
</script>

<style>
@import 'swiper/css';
@import 'swiper/css/grid';
@import 'swiper/css/pagination';
.fairSales {
  width: 1180px;
  height: 240px;
  display: grid;
  grid-template-columns: 285px auto;
  background-color: white;
  margin: 30px auto 0;
  border: 1px solid #E0E0E0;
  border-radius: 6px;
}
@media screen and (max-width: 879px) {
  .fairSales {
    width: 100%;
    height: 245px;
    display: flex;
    flex-direction: column;
    margin-top: 10px;
    border-radius: 0;
    border-left: none;
    border-right: none;
  }
}
.fairSales__calendar {
  margin: 20px 0 0 20px;
}
@media screen and (max-width: 879px) {
  .fairSales__calendar {
    display: flex;
    margin: 0 0 0 16px;
    justify-content: space-between;
  }
}
.fairSales__title {
  font-family: 'Inter';
  font-size: 20px;
  line-height: 28px;
  font-weight: 500;
  margin: 0;
  letter-spacing: -0.2px;
}
@media screen and (max-width: 879px) {
  .fairSales__title {
    font-size: 18px;
    letter-spacing: 0;
    line-height: 22px;
    margin-top: 14px;
  }
}
.fairSales__subtitle {
  font-family: 'Inter';
  font-size: 16px;
  color: #8B96A5;
}
@media screen and (max-width: 879px) {
  .fairSales__subtitle {
    color: #505050;
    font-size: 13px;
    line-height: 16px;
  }
}
.fairSales__cards {
  width: 100%;
  height: 100%
}
@media screen and (max-width: 879px) {
  .fairSales__cards {
    margin-top: 11px;
  }
}
.fairSales__card {
  height: 100%;
  font-family: 'Inter';
  display: flex;
  flex-direction: column;
  align-items: center;
  border-left: 1px solid #E0E0E0;
  letter-spacing: -0.2px;
  text-decoration: none;
  color: #1C1C1C;
}
.fairSales__card:hover {
  box-shadow: 0 -4px 4px rgba(0,0,0,0.25);
}
@media screen and (max-width: 879px) {
  .fairSales__card {
    border: 1px solid #E0E0E0;
    border-left: none;
  }
}
.fairSales__cardImage {
  margin-top: 11px;
  width: 140px;
  height: 140px;
}
@media screen and (max-width: 879px) {
  .fairSales__cardImage {
    margin-top: 8px;
    width: 98px;
    height:98px;
  }
}
.fairSales__cardTitle {
  font-size: 16px;
  margin-top: 11px;
  line-height: 24px;
}
@media screen and (max-width: 879px) {
  .fairSales__cardTitle {
    font-size: 13px;
    line-height: 16px;
    margin-top: 4px;
  }
}
.fairSales__cardPercent {
  background-color: #FFE3E3;
  color: #EB001B;
  font-size: 14px;
  border-radius: 29px;
  line-height: 24px;
  margin-top: 7px;
  padding: 3px 13px 4px 13px;
  letter-spacing: -0.2px;
}
@media screen and (max-width: 879px) {
  .fairSales__cardPercent {
    line-height: 17px;
    padding: 5px 13px 6px;
    margin-bottom: 18px;
  }
}
</style>

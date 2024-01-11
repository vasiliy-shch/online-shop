<template>
  <section class="invitingBlock">
    <div class="invitingBlock__banner">
      <img class="invitingBlock__bannerImage" :src=bannerImage>
      <div class="invitingBlock__bannerItemsBlock">
        <h3 class="invitingBlock__bannerTitle">{{ bannerTitle }}</h3>
        <button class="invitingBlock__bannerButton">
          <a class="invitingBlock__bannerButton_text" href="#">Source now</a>
        </button>
      </div>
    </div>
    <swiper
      class="invitingBlock__cards"
      :slidesPerView="2.5"
      :breakpoints="breakpoints"
      :pagination="{
        clickable: true,
      }"
      :modules="modules"
      :grid="{
        rows: 1,
        fill: 'column'
      }"
    >
      <swiper-slide
        v-for="card in items"
        :key="card.id"
      >
        <a :class="['invitingBlock__card', card.id > 4 ?
          'invitingBlock__card_borderTop' : '']">
          <div class="invitingBlock__textBlock">
            <h3 class="invitingBlock__cardTitle">{{ card.name }}</h3>
            <span class="invitingBlock__cardSubtitle">
              <span> from&nbsp; </span>
              <span> USD {{ card.price }}</span>
            </span>
          </div>
          <img class="invitingBlock__cardImage" :src="card.image">
        </a>
      </swiper-slide>
    </swiper>
    <a class="invitingBlock__mobileLink" href="#">
      <button class="invitingBlock__mobileLink_button">
        Source now
        <img class="invitingBlock__mobileLink_buttonImage" src="~/assets/images/bodyMain/blueArrowRight.svg">
      </button>
    </a>
  </section>
</template>

<script>
import { Swiper, SwiperSlide } from 'swiper/vue';
import { Grid, Pagination } from 'swiper/modules';
export default {
  props: {
    items: Array,
    bannerTitle: String,
    bannerImage: String
  },
  components: {
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
        360: {
          slidesPerView: 2.5,
          grid: {
            rows: 1,
            fill: 'column'
          }
        },
        420: {
          slidesPerView: 3,
          grid: {
            rows: 1,
            fill: 'column'
          }
        },
        560: {
          slidesPerView: 4,
          grid: {
            rows: 1,
            fill: 'column'
          }
        },
        750: {
          slidesPerView: 5,
          grid: {
            rows: 1,
            fill: 'column'
          }
        },
        879: {
          slidesPerView: 4,
          grid: {
            rows: 2,
            fill: 'row'
          }
        }
      }
    }
  }
}
</script>

<style>
@import 'swiper/css';
@import 'swiper/css/grid';
@import 'swiper/css/pagination';
.invitingBlock {
  width: 1180px;
  height: 257px;
  display: grid;
  grid-template-columns: 280px auto;
  background-color: white;
  margin: 20px auto 0;
  border: 1px solid #E0E0E0;
  border-radius: 6px;
}
@media screen and (max-width: 879px) {
  .invitingBlock {
    width: 100%;
    height: 270px;
    margin-top: 10px;
    grid-template-columns: 100%;
    grid-template-rows: 51px 160px 58px;
    border-radius: 0;
    border-left: none;
    border-right: none;
  }
}
.invitingBlock__banner {
  display: flex;
  position: relative;
}
@media screen and (max-width: 879px) {
  .invitingBlock__banner {
    background-color: white;
    background-image: none;
  }
}
.invitingBlock__bannerItemsBlock {
  position: absolute;
}
.invitingBlock__bannerTitle {
  width: 150px;
  font-family: 'Inter';
  font-size: 20px;
  font-weight: 500;
  line-height: 26px;
  letter-spacing: -0.2px;
  padding: 0;
  margin: 20px 0 0 20px;
  z-index: 1;
}
@media screen and (max-width: 879px) {
  .invitingBlock__bannerTitle {
    white-space: nowrap;
    font-size: 18px;
    letter-spacing: 0;
    line-height: 22px;
    margin: 14px 0 0 16px;
  }
}
.invitingBlock__bannerImage {
  height: 100%;
  width: 100%;
  height: auto;
  top: 0;
  left: 0;
  z-index: 0;
}
@media screen and (max-width: 879px) {
  .invitingBlock__bannerImage {
    display: none
  }
}
.invitingBlock__bannerButton {
  font-size: 16px;
  line-height: 19px;
  padding: 10.5px 16px;
  border-radius: 6px;
  border: none;
  background-color: white;
  margin: 18px 0 0 18px;
  cursor: pointer;
}
@media screen and (max-width: 879px) {
  .invitingBlock__bannerButton {
    display: none;
  }
}
.invitingBlock__bannerButton:hover {
  opacity: 0.8;
}
.invitingBlock__bannerButton_text {
  text-decoration: none;
  color: black;
}
.invitingBlock__cards {
  width: 100%;
}
@media screen and (max-width: 879px) {
  .invitingBlock__cards {
    border-top: 1px solid #E0E0E0;
    border-bottom: 1px solid #E0E0E0;
  }
}
.invitingBlock__card {
  display: flex;
  height: 100%;
  justify-content: space-between;
  border-left: 1px solid #E0E0E0;
  cursor: pointer;
}
.invitingBlock__card:hover {
  box-shadow: 0 -4px 4px rgba(0,0,0,0.25);
}
@media screen and (max-width: 879px) {
  .invitingBlock__card {
    flex-direction: column-reverse;
    align-items: center;
    justify-content: flex-end;
    border: none;
    border-right: 1px solid #E0E0E0;
  }
}
.invitingBlock__textBlock {
  margin: 20px 0 0 16px;
  font-family: 'Inter';
}
@media screen and (max-width: 879px) {
  .invitingBlock__textBlock {
    display: flex;
    flex-direction: column;
    margin: 4px 0 0;
    align-items: center;
  }
}
.invitingBlock__cardTitle {
  margin: 0;
  font-weight: 300;
  font-size: 16px;
  line-height: 19px;
}
@media screen and (max-width: 879px) {
  .invitingBlock__cardTitle {
    font-size: 13px;
    line-height: 16px;
  }
}
.invitingBlock__cardSubtitle {
  color: #8B96A5;
  margin-top: 9px;
  display: flex;
  flex-direction: column;
  font-size: 13px;
  line-height: 16px;
}
@media screen and (max-width: 879px) {
  .invitingBlock__cardSubtitle {
    margin-top: 4px;
    flex-direction: row;
  }
}
.invitingBlock__cardImage {
  width: 82px;
  height: 82px;
  margin: 42px 1px 3px 0;
}
@media screen and (max-width: 879px) {
  .invitingBlock__cardImage {
    width: 98px;
    height: 98px;
    margin: 8px 21px 0;
  }
}
.invitingBlock__card_borderTop {
  border-top: 1px solid #E0E0E0
}
@media screen and (max-width: 879px) {
  .invitingBlock__card_borderTop {
    border-top: none;
  }
}
.invitingBlock__mobileLink {
  display: none;
}
@media screen and (max-width: 879px){
  .invitingBlock__mobileLink {
    width: 141px;
    height: 40px;
    margin: 9px 0 0 9px;
    display: flex;
    font-family: 'Inter';
    text-decoration: none;
  }
}
.invitingBlock__mobileLink_button {
  display: flex;
  padding: 11px 9px 10px 13px;
  font-size: 16px;
  line-height: 19px;
  font-weight: 600;
  border: none;
  background-color: white;
  color: #0D6EFD;
  cursor: pointer;
}
.invitingBlock__mobileLink_buttonImage {
  width: 22px;
  height: 22px;
  margin-left: 6px;
  cursor: pointer;
}
</style>

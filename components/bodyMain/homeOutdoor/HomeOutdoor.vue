<template>
  <section class="homeOutdoor">
    <div class="homeOutdoor__banner">
      <h3 class="homeOutdoor__bannerTitle">Home and outdoor</h3>
      <button class="homeOutdoor__bannerButton">
        <a class="homeOutdoor__bannerButton_text" href="#">Source now</a>
      </button>
    </div>
    <div class="homeOutdoor__cards">
      <a
        v-for="card in homeCards"
        :key="card.id"
        :class="['homeOutdoor__card', card.id > 4 ?
          'homeOutdoor__card_borderTop' : '']"
      >
        <div class="homeOutdoor__textBlock">
          <h3 class="homeOutdoor__cardTitle">{{ card.name }}</h3>
          <span class="homeOutdoor__cardSubtitle">
            <span> from&nbsp; </span>
            <span> USD {{ card.price }}</span>
          </span>
        </div>
        <img class="homeOutdoor__cardImage" :src="card.image">
      </a>
    </div>
    <a class="homeOutdoor__mobileLink" href="#">
      <button class="homeOutdoor__mobileLink_button">
        Source now
        <img class="homeOutdoor__mobileLink_buttonImage" src="~/assets/images/bodyMain/blueArrowRight.svg">
      </button>
    </a>
  </section>
</template>

<script>
export default {
  data () {
    return {
      homeCards: [
        {
          id: 1,
          name: 'Soft chairs',
          image: require('~/assets/images/bodyMain/cards/softChairs.svg'),
          price: 19,
          href: '#'
        },
        {
          id: 2,
          name: 'Sofa & chair',
          image: require('~/assets/images/bodyMain/cards/sofaChair.svg'),
          price: 19,
          href: '#'
        },
        {
          id: 3,
          name: 'Kitchen dishes',
          image: require('~/assets/images/bodyMain/cards/kitchenDishes.svg'),
          price: 19,
          href: '#'
        },
        {
          id: 4,
          name: 'Interior',
          image: require('~/assets/images/bodyMain/cards/interior.svg'),
          price: 19,
          href: '#'
        },
        {
          id: 5,
          name: 'Kitchen mixer',
          image: require('~/assets/images/bodyMain/cards/mixer.svg'),
          price: 100,
          href: '#'
        },
        {
          id: 6,
          name: 'Blenders',
          image: require('~/assets/images/bodyMain/cards/blenders.svg'),
          price: 39,
          href: '#'
        },
        {
          id: 7,
          name: 'Home appliance',
          image: require('~/assets/images/bodyMain/cards/homeAppliance.svg'),
          price: 19,
          href: '#'
        },
        {
          id: 8,
          name: 'Home plants',
          image: require('~/assets/images/bodyMain/cards/homePlants.svg'),
          price: 10,
          href: '#'
        }
      ]
    }
  }
}
</script>

<style>
.homeOutdoor {
  width: 1180px;
  height: 257px;
  display: grid;
  grid-template-columns: 280px auto;
  grid-auto-rows: 128.5px;
  background-color: white;
  margin: 20px auto 0;
  border: 1px solid #E0E0E0;
  border-radius: 6px;
}
@media screen and (max-width: 879px) {
  .homeOutdoor {
    width: 360px;
    height: 270px;
    margin-top: 10px;
    grid-template-columns: 360px;
    grid-template-rows: 51px 160px 58px;
    border-radius: 0;
    border-left: none;
    border-right: none;
  }
}
.homeOutdoor__banner {
  grid-row-start: 1;
  grid-row-end: 3;
  background-color: #FFE0B0;
  background-image: url(~/assets/images/bodyMain/homeOutdoorBanner.svg);
}
@media screen and (max-width: 879px) {
  .homeOutdoor__banner {
    grid-row-start: 1;
    grid-row-end: 2;
    background-color: white;
    background-image: none;
  }
}
.gadgetsBackground {
  background-image: url(~/assets/images/bodyMain/electronicsGadgets.svg);
}
@media screen and (max-width: 879px) {
  .gadgetsBackground {
    background-image: none;
  }
}
.homeOutdoor__bannerTitle {
  width: 130px;
  font-family: 'Inter';
  font-size: 20px;
  font-weight: 500;
  line-height: 26px;
  letter-spacing: -0.2px;
  padding: 0;
  margin: 20px 0 0 20px;
}
@media screen and (max-width: 879px) {
  .homeOutdoor__bannerTitle {
    white-space: nowrap;
    font-size: 18px;
    letter-spacing: 0;
    line-height: 22px;
    margin: 14px 0 0 16px;
  }
}
.homeOutdoor__bannerButton {
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
  .homeOutdoor__bannerButton {
    display: none;
  }
}
.homeOutdoor__bannerButton:hover {
  opacity: 0.8;
}
.homeOutdoor__bannerButton_text {
  text-decoration: none;
  color: black;
}
.homeOutdoor__cards {
  display: grid;
  grid-template-columns: repeat(4, 223px);
}
@media screen and (max-width: 879px) {
  .homeOutdoor__cards {
    grid-template-columns: repeat(8, 140px);
    grid-template-rows: 160px;
    border-top: 1px solid #E0E0E0;
    border-bottom: 1px solid #E0E0E0;
    overflow-x: scroll;
  }
}
.homeOutdoor__card {
  display: flex;
  justify-content: space-between;
  border-left: 1px solid #E0E0E0;
  cursor: pointer;
}
.homeOutdoor__card:hover {
  box-shadow: 0 -4px 4px rgba(0,0,0,0.25);
}
@media screen and (max-width: 879px) {
  .homeOutdoor__card {
    flex-direction: column-reverse;
    align-items: center;
    justify-content: flex-end;
    border: none;
    border-right: 1px solid #E0E0E0;
  }
}
.homeOutdoor__textBlock {
  margin: 20px 0 0 16px;
  font-family: 'Inter';
}
@media screen and (max-width: 879px) {
  .homeOutdoor__textBlock {
    display: flex;
    flex-direction: column;
    margin: 4px 0 0;
    align-items: center;
  }
}
.homeOutdoor__cardTitle {
  margin: 0;
  font-weight: 300;
  font-size: 16px;
  line-height: 19px;
}
@media screen and (max-width: 879px) {
  .homeOutdoor__cardTitle {
    font-size: 13px;
    line-height: 16px;
  }
}
.homeOutdoor__cardSubtitle {
  color: #8B96A5;
  margin-top: 9px;
  display: flex;
  flex-direction: column;
  font-size: 13px;
  line-height: 16px;
}
@media screen and (max-width: 879px) {
  .homeOutdoor__cardSubtitle {
    margin-top: 4px;
    flex-direction: row;
  }
}
.homeOutdoor__cardImage {
  width: 82px;
  height: 82px;
  margin: 42px 1px 3px 0;
}
@media screen and (max-width: 879px) {
  .homeOutdoor__cardImage {
    width: 98px;
    height: 98px;
    margin: 8px 21px 0;
  }
}
.homeOutdoor__card_borderTop {
  border-top: 1px solid #E0E0E0
}
@media screen and (max-width: 879px) {
  .homeOutdoor__card_borderTop {
    border-top: none;
  }
}
.homeOutdoor__mobileLink {
  display: none;
}
@media screen and (max-width: 879px){
  .homeOutdoor__mobileLink {
    width: 141px;
    height: 40px;
    margin: 9px 0 0 9px;
    display: flex;
    font-family: 'Inter';
    text-decoration: none;
  }
}
.homeOutdoor__mobileLink_button {
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
.homeOutdoor__mobileLink_buttonImage {
  width: 22px;
  height: 22px;
  margin-left: 6px;
  cursor: pointer;
}
</style>

<template>
  <section class="bigBanner">
    <div class="bigBanner__menuBlock">
      <a
        v-for="category in categories"
        :key = "category.id"
        :href = "category.href"
        :class="['bigBanner__menuItem',
          selectedCategory.id === category.id ?
          'bigBanner__menuItem_selected' : '']"
        @click="select(category)"
      >
        <span class="bigBanner__menuTitle"> {{ category.name }} </span>
      </a>
    </div>
    <div class="bigBanner__bannerImage">
      <h3 class="bigBanner__subtitle"> Latest trending </h3>
      <h3 class="bigBanner__title"> Electronic items </h3>
      <button class="bigBanner__button">
        <a class="bigBanner__buttonTitle" href="#"> Learn more </a>
      </button>
    </div>
    <div class="bigBanner__formsBlock">
      <div class="bigBanner__userForm">
        <div class="profile">
          <div class="profile__avatar"></div>
          <span class="profile__greetings">
            Hi, user let`s&nbsp;get&nbsp;stated
          </span>
        </div>
        <button class="profile__button"> Join now </button>
        <button class="profile__button profile__button_logIn"> Log in </button>
      </div>
      <div class="bigBunner__promoCoupon">
        <span class="promoCoupon__title">
          Get US $10 off
          with a new supplier
        </span>
      </div>
      <div class="bigBunner__promoCoupon bigBunner__promoCoupon_mintColor">
        <span class="promoCoupon__title">
          Send quotes with
          supplier preferences
        </span>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  data () {
    return {
      selectedCategory: {
        id: '',
        name: '',
        href: ''
      },
      categories: [
        {
          id: 1,
          name: 'Automobiles',
          href: '#'
        },
        {
          id: 2,
          name: 'Clothes and wear',
          href: '#'
        },
        {
          id: 3,
          name: 'Home interiors',
          href: '#'
        },
        {
          id: 4,
          name: 'Computer and tech',
          href: '#'
        },
        {
          id: 5,
          name: 'Tools, equipments',
          href: '#'
        },
        {
          id: 6,
          name: 'Sports and outdoor',
          href: '#'
        },
        {
          id: 7,
          name: 'Animals and pets',
          href: '#'
        },
        {
          id: 8,
          name: 'Machinery tools',
          href: '#'
        },
        {
          id: 9,
          name: 'More category',
          href: '#'
        }
      ]
    }
  },
  methods: {
    select (category) {
      this.selectedCategory = category
    }
  }
}
</script>

<style>
.bigBanner {
  display: flex;
  width: 1180px;
  height: 400px;
  background-color: white;
  margin: 20px auto 0;
  border: 1px solid #E0E0E0;
  border-radius: 6px;
}
@media screen and (max-width: 879px) {
  .bigBanner {
    width: 100%;
    height: 180px;
    margin: 14px auto 0;
    border: none;
  }
}
.bigBanner__menuBlock {
  width: 250px;
  height: 360px;
  margin: 20px 0 20px 14px;
}
@media screen and (max-width: 879px) {
  .bigBanner__menuBlock {
    display: none;
  }
}
.bigBanner__menuItem {
  display: flex;
  flex-direction: column;
  text-decoration: none;
  color: #505050;
  border-radius: 6px;
}
.bigBanner__menuItem:hover {
  opacity: 0.8;
}
.bigBanner__menuTitle {
  font-family: 'Inter';
  font-size: 16px;
  line-height: 20px;
  margin: 10px;
  width: 230px;
}
.bigBanner__menuItem_selected {
  background-color: #E5F1FF;
  color: black;
}
.bigBanner__bannerImage {
  width: 665px;
  height: 360px;
  margin: 20px 0 20px 11px;
  background-image: url(~/assets/images/bodyMain/bigBanner.svg);
  background-repeat: no-repeat;
}
@media screen and (max-width: 879px) {
  .bigBanner__bannerImage {
    width: 100%;
    height: 100%;
    margin: 0;
    background-size: 100%;
  }
}
.bigBanner__subtitle {
  margin: 53px 0 0 46px;
  font-family: 'Inter';
  font-size: 28px;
  color: #1C1C1C;
  line-height: 34px;
  font-weight: 400;
}
@media screen and (max-width: 879px) {
  .bigBanner__subtitle {
    margin: 24px 0 0 22px;
    font-size: 18px;
    line-height: 22px;
  }
}
.bigBanner__title {
  margin: 0 0 0 45px;
  font-family: 'Inter';
  font-size: 32px;
  color: #1C1C1C;
  line-height: 39px;
  font-weight: 500;
}
@media screen and (max-width: 879px) {
  .bigBanner__title {
    margin: 0 0 0 22px;
    font-size: 18px;
    line-height: 22px;
  }
}
.bigBanner__button {
  margin: 17px 0 0 46px;
  padding: 0;
  width: 119px;
  height: 40px;
  background-color: white;
  border: none;
  border-radius: 6px;
  cursor: pointer;
}
.bigBanner__button:hover {
  opacity: 0.8;
}
@media screen and (max-width: 879px) {
  .bigBanner__button {
    width: 91px;
    height: 30px;
    margin: 18px 0 0 22px;
  }
}
.bigBanner__buttonTitle {
  text-decoration: none;
  color: black;
  font-family: 'Inter';
  font-size: 16px;
  font-weight: 400;
}
@media screen and (max-width: 879px) {
  .bigBanner__buttonTitle {
    font-size: 13px;
    line-height: 16px;
    color: #0D6EFD;
  }
}
.bigBanner__formsBlock {
  margin: 20px;
}
@media screen and (max-width: 879px) {
  .bigBanner__formsBlock {
    display: none;
  }
}
.bigBanner__userForm {
  display: flex;
  flex-direction: column;
  width: 200px;
  height: 150px;
  background-color: #E3F0FF;
  border-radius: 6px;
}
.profile {
  display: flex;
  align-items: center;
  margin: 14px 0 5px 10px;
}
.profile__avatar {
  width: 44px;
  height: 44px;
  border-radius: 50%;
  background-size: contain;
  background-repeat: no-repeat;
  background-image: url(~/assets/images/bodyMain/profileAvatar.svg);
}
.profile__greetings {
  font-family: 'Inter';
  font-size: 16px;
  width: 112px;
  letter-spacing: -0.2px;
  margin-left: 9px;
}
.profile__button {
  width: 180px;
  height: 30px;
  margin: 7px 10px 0 10px;
  border: none;
  border-radius: 6px;
  background-color: #0D6EFD;
  color: white;
  font-family: 'Inter';
  font-size: 16px;
  letter-spacing: -0.2px;
  cursor: pointer;
}
.profile__button:hover {
  opacity: 0.8;
}
.profile__button_logIn {
  background-color: white;
  color: #0D6EFD;
}
.bigBunner__promoCoupon {
  display: flex;
  width: 200px;
  height: 95px;
  background-color: #F38332;
  border-radius: 6px;
  margin-top: 10px;
  color: white;
  font-family: 'Inter';
  font-size: 16px;
  line-height: auto;
}
.bigBunner__promoCoupon_mintColor {
  background-color: #55BDC3;
}
.promoCoupon__title {
  margin: 16px 0 0 16px;
  width: 144px;
}
</style>

<template>
  <section class="body__main">
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
    <section class="fairSales">
      <div class="fairSales__calendar">
        <h3 class="fairSales__title"> Deals and offers </h3>
        <span class="fairSales__subtitle"> Hygiene equipments </span>
        <div class="fairSales__counter">
          <div class="counter__element">
             <span class="counter__number"> {{ date.days }} </span>
             <span class="counter__title"> Days </span>
          </div>
          <div class="counter__element">
             <span class="counter__number"> {{ date.hours }} </span>
             <span class="counter__title"> Hour </span>
          </div>
          <div class="counter__element">
             <span class="counter__number"> {{ date.minutes }} </span>
             <span class="counter__title"> Min </span>
          </div>
          <div class="counter__element">
             <span class="counter__number"> {{ date.seconds }} </span>
             <span class="counter__title"> Sec </span>
          </div>
        </div>
      </div>
      <a class="fairSales__card"
        v-for="card in saleCards"
        :key="card.id"
        :href="card.href"
      >
        <img class="fairSales__cardImage" :src="card.image">
        <span class="fairSales__cardTitle">{{ card.name }}</span>
        <span class="fairSales__cardPercent"> -{{ card.sale }}% </span>
      </a>
    </section>
    <section class="homeOutdoor">
      <div class="homeOutdoor__banner">
        <h3 class="homeOutdoor__bannerTitle">Home and outdoor</h3>
        <button class="homeOutdoor__bannerButton">
          <a class="homeOutdoor__bannerButton_text" href="#">Source now</a>
        </button>
      </div>
      <a
        v-for="card in homeCards"
        :key="card.id"
        :class="['homeOutdoor__card', card.id > 4 ?
          'homeOutdoor__card_borderTop' : '']"
      >
        <div class="homeOutdoor__textBlock">
          <h3 class="homeOutdoor__cardTitle">{{ card.name }}</h3>
          <span class="homeOutdoor__cardSubtitle">
            <span> from </span>
            <span> USD {{ card.price }}</span>
          </span>
        </div>
        <img class="homeOutdoor__cardImage" :src="card.image">
      </a>
    </section>
    <section class="homeOutdoor">
      <div class="homeOutdoor__banner gadgetsBackground">
        <h3 class="homeOutdoor__bannerTitle">Home and outdoor</h3>
        <button class="homeOutdoor__bannerButton">
          <a class="homeOutdoor__bannerButton_text" href="#">Source now</a>
        </button>
      </div>
      <a
        v-for="card in deviceCards"
        :key="card.id"
        :class="['homeOutdoor__card', card.id > 4 ?
          'homeOutdoor__card_borderTop' : '']"
      >
        <div class="homeOutdoor__textBlock">
          <h3 class="homeOutdoor__cardTitle">{{ card.name }}</h3>
          <span class="homeOutdoor__cardSubtitle">
            <span> from </span>
            <span> USD {{ card.price }}</span>
          </span>
        </div>
        <img class="homeOutdoor__cardImage" :src="card.image">
      </a>
    </section>
    <section class="bigForm">
      <div class="bigForm__titlesBlock">
        <h3 class="bigForm__title">An easy way to send requests to all suppliers</h3>
        <p class="bigForm__subtitle">
          Lorem ipsum dolor sit amet, consectetur
          adipisicing elit, sed do eiusmod tempor incididunt.
        </p>
      </div>
      <form class="bigForm__formBlock">
        <h3 class="formBlock__titleForm">Send quote to suppliers</h3>
        <input class="formBlock__itemInput" value="What item you need?">
        <textarea
          class="formBlock__itemTextarea"
          placeholder="Type more details"
        >
        </textarea>
        <div class="formBlock__quantityBlock">
          <input class="quantityBlock__title" type="number">
          <button
            v-if="!isEdit"
            class="quantityBlock__measurement"
            @click.prevent="show"
          >
            {{ selectedMeasurement.name }}
          </button>
          <div v-else-if="isEdit">
            <button
              class="quantityBlock__measurement"
              @click.prevent="hide"
            >
              {{ selectedMeasurement.name }}
            </button>
            <ul class="quantityBlock__measurementsList">
              <li
                v-for="measurement in measurements"
                :key = 'measurement.id'
                :class="['quantityBlock__measurementInList',
                  selectedMeasurement.id === measurement.id ?
                  'quantityBlock__measurementInList_selectedMeasurement' : '']"
                @click="selectMeasurement(measurement)"
              >
                {{ measurement.name }}
              </li>
            </ul>
          </div>
        </div>
        <button @click.prevent class="formBlock__sendFormButton">Send inquiry</button>
      </form>
    </section>
    <section class="recommendedItems">
      <h2 class="recommendedItems__title">Recommended items</h2>
      <div class="recommendedItems__cards">
        <div class="recommendedItems__card"
          v-for="card in recommendedCards"
          :key='card.id'
        >
          <img class="recommendedItems__cardImage" :src="card.image">
          <h4 class="recommendedItems__cardTitle">${{ card.price }}</h4>
          <span class="recommendedItems__cardSubtitle">{{ card.name }}</span>
        </div>
      </div>
    </section>
    <section class="extraServices">
      <h3 class="extraServices__title">Our extra services</h3>
      <div class="extraServices__cards">
        <div class="extraServices__card"
          v-for="service in extraServices"
          :key="service.id"
        >
          <img
            class="extraServices__cardImage"
            :src="service.image"
          >
          <div class="extraServices__cardContext">
            <button class="extraServices__cardButton">
              <img
                class="extraServices__cardButton_image"
                :src="service.icon"
              >
            </button>
            <span :class="['extraServices__cardTitle',
              service.id === 1 ? 'extraServices__cardTitle_small' : '']"
            >
              {{ service.description }}
            </span>
          </div>
        </div>
      </div>
    </section>
    <section class="suppliers">
      <h3 class="suppliers__title">Suppliers by region</h3>
      <div class="suppliers__cards">
        <a
          v-for="supplier in suppliers"
          :key="supplier.id"
          :href="supplier.href"
          class="suppliers__card"
        >
          <img class="suppliers__cardImage" :src="supplier.image">
          <div class="suppliers__cardContext">
            <h4 class="suppliers__cardTitle">{{ supplier.name }}</h4>
            <span class="suppliers__cardSubtitle">{{ supplier.href }}</span>
          </div>
        </a>
      </div>
    </section>
    <form class="subscribeForm" @submit.prevent>
      <h3 class="subscribeForm__title">Subscribe in our newsletter</h3>
      <span class="subscribeForm__subtitle">
        Get daily news on upcoming offers
        from many suppliers all over the world
      </span>
      <div class="subscribeForm__inputBlock">
        <input class="subscribeForm__input" placeholder="Email">
        <button class="subscribeForm__button">Subscribe</button>
      </div>
    </form>
  </section>
</template>

<script>
export default {
  created () {
    setInterval(this.countDown, 1000)
  },
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
      ],
      allDate: '',
      date: {
        days: '0',
        hours: '0',
        minutes: '0',
        seconds: '0'
      },
      saleCards: [
        {
          id: 1,
          name: 'Smart watches',
          image: require('~/assets/images/bodyMain/cards/smartWatch.svg'),
          sale: 25,
          href: '#'
        },
        {
          id: 2,
          name: 'Laptops',
          image: require('~/assets/images/bodyMain/cards/laptops.svg'),
          sale: 15,
          href: '#'
        },
        {
          id: 3,
          name: 'GoPro cameras',
          image: require('~/assets/images/bodyMain/cards/goProCameras.svg'),
          sale: 40,
          href: '#'
        },
        {
          id: 4,
          name: 'Headphones',
          image: require('~/assets/images/bodyMain/cards/gamingHeadphones.svg'),
          sale: 25,
          href: '#'
        },
        {
          id: 5,
          name: 'Canon cameras',
          image: require('~/assets/images/bodyMain/cards/canonCameras.svg'),
          sale: 25,
          href: '#'
        }
      ],
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
      ],
      deviceCards: [
        {
          id: 1,
          name: 'Smart Watches',
          image: require('~/assets/images/bodyMain/cards/smartWatch.svg'),
          price: 199,
          href: '#'
        },
        {
          id: 2,
          name: 'Cameras',
          image: require('~/assets/images/bodyMain/cards/goProCameras.svg'),
          price: 19,
          href: '#'
        },
        {
          id: 3,
          name: 'Headphones',
          image: require('~/assets/images/bodyMain/cards/headphones.svg'),
          price: 19,
          href: '#'
        },
        {
          id: 4,
          name: 'Teapots',
          image: require('~/assets/images/bodyMain/cards/teapots.svg'),
          price: 19,
          href: '#'
        },
        {
          id: 5,
          name: 'Gaming set',
          image: require('~/assets/images/bodyMain/cards/gamingHeadphones.svg'),
          price: 100,
          href: '#'
        },
        {
          id: 6,
          name: 'Laptops & PC',
          image: require('~/assets/images/bodyMain/cards/laptops.svg'),
          price: 39,
          href: '#'
        },
        {
          id: 7,
          name: 'Smartphones',
          image: require('~/assets/images/bodyMain/cards/smartphones.svg'),
          price: 19,
          href: '#'
        },
        {
          id: 8,
          name: 'Iphones',
          image: require('~/assets/images/bodyMain/cards/iphones.svg'),
          price: 10,
          href: '#'
        }
      ],
      isEdit: false,
      selectedMeasurement: {
        id: 1,
        name: 'Pcs'
      },
      measurements: [
        {
          id: 1,
          name: 'Pcs'
        },
        {
          id: 2,
          name: 'kg'
        },
        {
          id: 3,
          name: 'mg'
        },
        {
          id: 4,
          name: 'meter'
        },
        {
          id: 5,
          name: 'L'
        },
        {
          id: 6,
          name: 'mL'
        },
        {
          id: 7,
          name: 'Lb'
        },
        {
          id: 8,
          name: 'ounce'
        }
      ],
      recommendedCards: [
        {
          id: 1,
          name: 'T-shirts with multiple colors, for men',
          image: require('~/assets/images/bodyMain/cards/t-shirts.svg'),
          price: 10.30,
          description: '',
          href: '#'
        },
        {
          id: 2,
          name: 'Jeans shorts for men blue color',
          image: require('~/assets/images/bodyMain/cards/jeansShorts.svg'),
          price: 10.30,
          description: '',
          href: '#'
        },
        {
          id: 3,
          name: 'Brown winter coat medium size',
          image: require('~/assets/images/bodyMain/cards/brownCoat.svg'),
          price: 12.50,
          description: '',
          href: '#'
        },
        {
          id: 4,
          name: 'Jeans bag for travel for men',
          image: require('~/assets/images/bodyMain/cards/jeansBag.svg'),
          price: 34.00,
          description: '',
          href: '#'
        },
        {
          id: 5,
          name: 'Leather wallet',
          image: require('~/assets/images/bodyMain/cards/leatherWallet.svg'),
          price: 99.00,
          description: '',
          href: '#'
        },
        {
          id: 6,
          name: 'Canon camera black, 100x zoom',
          image: require('~/assets/images/bodyMain/cards/goProCameras.svg'),
          price: 9.99,
          description: '',
          href: '#'
        },
        {
          id: 7,
          name: 'Headset for gaming with mic',
          image: require('~/assets/images/bodyMain/cards/gamingHeadphones.svg'),
          price: 8.99,
          description: '',
          href: '#'
        },
        {
          id: 8,
          name: 'Smart watch silver color modern',
          image: require('~/assets/images/bodyMain/cards/smartWatch.svg'),
          price: 10.30,
          description: '',
          href: '#'
        },
        {
          id: 9,
          name: 'Blue wallet for men leather metarfial',
          image: require('~/assets/images/bodyMain/cards/blueJacket.svg'),
          price: 10.30,
          description: '',
          href: '#'
        },
        {
          id: 10,
          name: 'Smart Jeans bag for travel for men',
          image: require('~/assets/images/bodyMain/cards/jeansBag.svg'),
          price: 80.95,
          description: '',
          href: '#'
        }
      ],
      extraServices: [
        {
          id: 1,
          description: 'Source from Industry Hubs',
          image: require('~/assets/images/bodyMain/extraServices/firstImage.svg'),
          icon: require('~/assets/images/bodyMain/extraServices/serch.svg'),
          href: '#'
        },
        {
          id: 2,
          description: 'Customize Your Products',
          image: require('~/assets/images/bodyMain/extraServices/secondImage.svg'),
          icon: require('~/assets/images/bodyMain/extraServices/box.svg'),
          href: '#'
        },
        {
          id: 3,
          description: 'Fast, reliable shipping by ocean or air',
          image: require('~/assets/images/bodyMain/extraServices/thirdImage.svg'),
          icon: require('~/assets/images/bodyMain/extraServices/ship.svg'),
          href: '#'
        },
        {
          id: 4,
          description: 'Product monitoring and inspection',
          image: require('~/assets/images/bodyMain/extraServices/fourthImage.svg'),
          icon: require('~/assets/images/bodyMain/extraServices/shield.svg'),
          href: '#'
        }
      ],
      suppliers: [
        {
          id: 1,
          name: 'Arabic Emirates',
          href: 'shopname.ae',
          image: require('~/assets/images/flags/ae.svg')
        },
        {
          id: 2,
          name: 'Australia',
          href: 'shopname.au',
          image: require('~/assets/images/flags/au.svg')
        },
        {
          id: 3,
          name: 'Unated States',
          href: 'shopname.us',
          image: require('~/assets/images/flags/us.svg')
        },
        {
          id: 4,
          name: 'Russia',
          href: 'shopname.ru',
          image: require('~/assets/images/flags/ru.svg')
        },
        {
          id: 5,
          name: 'Italy',
          href: 'shopname.it',
          image: require('~/assets/images/flags/it.svg')
        },
        {
          id: 6,
          name: 'Denmark',
          href: 'shopname.com.dk',
          image: require('~/assets/images/flags/dk.svg')
        },
        {
          id: 7,
          name: 'France',
          href: 'shopname.com.fr',
          image: require('~/assets/images/flags/fr.svg')
        },
        {
          id: 8,
          name: 'Germany',
          href: 'shopname.com.ge',
          image: require('~/assets/images/flags/ge.svg')
        },
        {
          id: 9,
          name: 'China',
          href: 'shopname.cn',
          image: require('~/assets/images/flags/cn.svg')
        },
        {
          id: 10,
          name: 'Great Britain',
          href: 'shopname.co.uk',
          image: require('~/assets/images/flags/gb.svg')
        }
      ]
    }
  },
  methods: {
    select (category) {
      this.selectedCategory = category
    },
    countDown () {
      const dateNow = new Date()
      const dateEnd = new Date('12.10.2023 00:00:00')
      this.allDate = Math.floor((dateEnd.getTime() - dateNow.getTime()) / 1000)
      let dateLeft = this.allDate
      let dateTemp = 0
      dateTemp = Math.floor(dateLeft / (24 * 60 * 60))
      dateLeft -= dateTemp * (24 * 60 * 60)
      if (dateTemp < 10) { dateTemp = '0' + dateTemp }
      this.date.days = dateTemp

      dateTemp = Math.floor(dateLeft / (60 * 60))
      dateLeft -= dateTemp * 60 * 60
      if (dateTemp < 10) { dateTemp = '0' + dateTemp }
      this.date.hours = dateTemp

      dateTemp = Math.floor(dateLeft / 60)
      dateLeft -= dateTemp * 60
      if (dateTemp < 10) { dateTemp = '0' + dateTemp }
      this.date.minutes = dateTemp

      if (dateLeft < 10) { dateLeft = '0' + dateLeft }
      this.date.seconds = dateLeft
    },
    show () {
      this.isEdit = true
    },
    hide () {
      this.isEdit = false
    },
    selectMeasurement (measurement) {
      this.selectedMeasurement = measurement
      this.isEdit = false
    }
  }
}
</script>

<style>
body {
  margin: 0;
}
.body__main {
  display: flex;
  flex-direction: column;
  max-width: 1440px;
  background-color: #F7FAFC;
}
.bigBanner {
  display: flex;
  width: 1180px;
  height: 400px;
  background-color: white;
  margin: 20px auto 0;
  border: 1px solid #E0E0E0;
  border-radius: 6px;
}
.bigBanner__menuBlock {
  width: 250px;
  height: 360px;
  margin: 20px 0 20px 14px;
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
.bigBanner__subtitle {
  margin: 53px 0 0 46px;
  font-family: 'Inter';
  font-size: 28px;
  color: #1C1C1C;
  line-height: 34px;
  font-weight: 400;
}
.bigBanner__title {
  margin: 0 0 0 45px;
  font-family: 'Inter';
  font-size: 32px;
  color: #1C1C1C;
  line-height: 39px;
  font-weight: 500;
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
.bigBanner__buttonTitle {
  text-decoration: none;
  color: black;
  font-family: 'Inter';
  font-size: 16px;
  font-weight: 400;
}
.bigBanner__formsBlock {
  margin: 20px;
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
.fairSales {
  width: 1180px;
  height: 240px;
  display: grid;
  grid-template-columns: 285px repeat(5, 179px);
  background-color: white;
  margin: 30px auto 0;
  border: 1px solid #E0E0E0;
  border-radius: 6px;
}
.fairSales__calendar {
  margin: 20px 0 0 20px;
}
.fairSales__title {
  font-family: 'Inter';
  font-size: 20px;
  line-height: 28px;
  font-weight: 500;
  margin: 0;
  letter-spacing: -0.2px;
}
.fairSales__subtitle {
  font-family: 'Inter';
  font-size: 16px;
  color: #8B96A5;
}
.fairSales__counter {
  margin-top: 18px;
  width: 198px;
  height: 50px;
  display: grid;
  grid-template-columns: repeat(4, 45px);
  column-gap: 6px;
}
.counter__element {
  display: flex;
  flex-direction: column;
  align-items: center;
  background-color: #606060;
  color: white;
  border-radius: 4px;
  font-family: 'Inter';
}
.counter__number {
  margin-top: 8px;
  font-size: 16px;
  font-weight: 600;
  line-height: 19px;
}
.counter__title {
  font-size: 12px;
  line-height: 15px;
}
.fairSales__card {
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
.fairSales__cardImage {
  margin-top: 11px;
  width: 140px;
  height: 140px;
}
.fairSales__cardTitle {
  font-size: 16px;
  margin-top: 11px;
  line-height: 24px;
}
.fairSales__cardPercent {
  background-color: #FFE3E3;
  color: #EB001B;
  font-size: 14px;
  border-radius: 29px;
  line-height: 24px;
  margin-top: 7px;
  padding: 3px 13px 4px 13px;
}
.homeOutdoor {
  width: 1180px;
  height: 257px;
  display: grid;
  grid-template-columns: 280px repeat(4, 223px);
  grid-auto-rows: 128.5px;
  background-color: white;
  margin: 20px auto 0;
  border: 1px solid #E0E0E0;
  border-radius: 6px;
}
.homeOutdoor__banner {
  grid-row-start: 1;
  grid-row-end: 3;
  background-color: #FFE0B0;
  background-image: url(~/assets/images/bodyMain/homeOutdoorBanner.svg);
}
.gadgetsBackground {
  background-image: url(~/assets/images/bodyMain/electronicsGadgets.svg);
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
.homeOutdoor__bannerButton:hover {
  opacity: 0.8;
}
.homeOutdoor__bannerButton_text {
  text-decoration: none;
  color: black;
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
.homeOutdoor__textBlock {
  margin: 20px 0 0 16px;
  font-family: 'Inter';
}
.homeOutdoor__cardTitle {
  margin: 0;
  font-weight: 300;
  font-size: 16px;
  line-height: 19px;
}
.homeOutdoor__cardSubtitle {
  color: #8B96A5;
  margin-top: 9px;
  display: flex;
  flex-direction: column;
  font-size: 13px;
  line-height: 16px;
}
.homeOutdoor__cardImage {
  width: 82px;
  height: 82px;
  margin: 42px 1px 3px 0;
}
.homeOutdoor__card_borderTop {
  border-top: 1px solid #E0E0E0
}
.bigForm {
 width: 1180px;
 height: 420px;
 margin: 20px auto 0;
 display: flex;
 justify-content: space-between;
 background-image: url(~/assets/images/bodyMain/bigBlueForm.svg);
}
.bigForm__titlesBlock {
  display: flex;
  flex-direction: column;
  width: 440px;
  height: 139px;
  margin: 40px 0 0 40px;
  color: white;
  font-family: 'Inter';
  text-align: left;
}
.bigForm__title {
  margin: 0;
  font-size: 32px;
  line-height: 39px;
  font-weight: 500;
  font-style: bold;
}
.bigForm__subtitle {
  width: 390px;
  text-align: left;
  margin-top: 13px;
  font-size: 16px;
  line-height: 24px;
}
.bigForm__formBlock {
  display: flex;
  flex-direction: column;
  width: 491px;
  height: 346px;
  margin: 30px 31px 0 0;
  border-radius: 6px;
  background-color: white;
  font-family: 'Inter';
}
.formBlock__titleForm {
  font-size: 20px;
  line-height: 28px;
  margin: 22px 0 0 20px;
  font-weight: 500;
}
.formBlock__itemInput {
  font-size: 16px;
  line-height: 19px;
  padding: 10px 0 9px 9px;
  border: 1px solid #DEE2E7;
  border-radius: 6px;
  width: 429px;
  margin: 18px 0 0 20px;
  outline: none;
}
.formBlock__itemTextarea {
  font-family: 'Inter';
  font-size: 16px;
  line-height: 19px;
  padding: 10px 36px 9px 9px;
  border: 1px solid #DEE2E7;
  border-radius: 6px;
  width: 393px;
  height: 52px;
  margin: 20px 0 0 20px;
  outline: none;
  resize: none;
  background-image: url(~/assets/images/bodyMain/triangleTextarea.svg);
  background-repeat: no-repeat;
  background-position: 425px 59px;
}
.formBlock__quantityBlock {
  display: flex;
  margin: 20px 0 0 20px;
  height: 40px;
  z-index: 1;
}
.quantityBlock__title {
  font-size: 16px;
  line-height: 19px;
  padding: 10px 0 9px 9px;
  border: 1px solid #DEE2E7;
  border-radius: 6px;
  width: 196px;
  outline: none;
  appearance: none;
}
.quantityBlock__measurement {
  width: 111px;
  height: 40px;
  margin-left: 8px;
  border: 1px solid #DEE2E7;
  border-radius: 6px;
  background-image: url(~/assets/images/apperance.svg);
  background-position: 79px 8px;
  background-repeat: no-repeat;
  background-color: white;
  cursor: pointer;
  text-align: start;
  padding-left: 10px;
  font-size: 16px;
  line-height: 19px;
}
.quantityBlock__measurementsList {
  width: 111px;
  margin: 0 0 0 8px;
  padding: 0 0 0 0px;
  list-style-type: none;
  border: 1px solid #DEE2E7;
  box-shadow: 0 4px 4px rgba(0,0,0,0.25);
  background-color: white;
}
.quantityBlock__measurementInList {
  font-size: 16px;
  line-height: 19px;
  padding: 5px 0 5px 10px;
  cursor: pointer;
}
.quantityBlock__measurementInList:hover {
  background-color: #E5F1FF;
}
.quantityBlock__measurementInList_selectedMeasurement {
  color: #0D6EFD;
}
.formBlock__sendFormButton {
  margin: 20px 0 0 20px;
  background-color: #0D6EFD;
  color: white;
  border: none;
  border-radius: 6px;
  cursor: pointer;
  height: 40px;
  width: 128px;
  padding: 10.5px 16px;
  font-size: 16px;
  line-height: 19px;
}
.formBlock__sendFormButton:hover {
  opacity: 0.8;
}
.recommendedItems {
  height: 696px;
  width: 1180px;
  display: flex;
  margin: 30px auto 0;
  font-family: 'Inter';
  flex-direction: column;
}
.recommendedItems__title {
  font-size: 24px;
  line-height: 32px;
  font-weight: 500;
  margin: 0;
}
.recommendedItems__cards {
  margin-top: 24px;
  display: grid;
  grid-template-columns: repeat(5, 220px);
  grid-template-rows: repeat(2, 310px);
  column-gap: 20px;
  row-gap: 20px;
}
.recommendedItems__card {
  background-color: white;
  border: 1px solid #DEE2E7;
  border-radius: 6px;
  display: flex;
  flex-direction: column;
}
.recommendedItems__card:hover {
  box-shadow: 0 4px 4px rgba(0,0,0,0.25);
}
.recommendedItems__cardImage {
  width: 200px;
  height: 200px;
  margin: 9px 10px 0 10px;
  cursor: pointer;
}
.recommendedItems__cardTitle {
  font-size: 16px;
  line-height: 22px;
  font-weight: 500;
  margin: 14px 0 0 16px;
}
.recommendedItems__cardSubtitle {
  text-align: left;
  letter-spacing: -0.2px;
  max-width: 186px;
  margin: 4px 0 0 16px;
  color: #8B96A5;
  font-size: 16px;
  line-height: 24px;
}
.extraServices {
  display: flex;
  flex-direction: column;
  width: 1180px;
  margin: 30px auto 0;
  font-family: 'Inter';
}
.extraServices__title {
  font-size: 24px;
  line-height: 32px;
  margin: 0;
  letter-spacing: -0.2px;
  font-weight: 500;
}
.extraServices__cards {
  display: grid;
  grid-template-columns: repeat(4, 280px);
  grid-template-rows: repeat(1, 200px);
  column-gap: 20px;
  margin-top: 24px;
}
.extraServices__card {
  display: flex;
  flex-direction: column;
  height: 200px;
  background-color: white;
  border: 1px solid #DEE2E7;
  border-radius: 6px;
}
.extraServices__card:hover {
  opacity: 0.8;
}
.extraServices__cardImage {
  background-color: #1C1C1C;
  height: 120px;
  max-width: 280px;
  border-radius: 6px 6px 0 0;
  cursor: pointer;
}
.extraServices__cardContext {
  display: flex;
  flex-direction: row-reverse;
  justify-content: space-between;
}
.extraServices__cardButton {
  padding: 0;
  background-color: #D1E7FF;
  border: 2px solid white;
  border-radius: 50%;
  width: 55px;
  height: 55px;
  position: relative;
  top: -24px;
  left: -21px;
  cursor: pointer;
}
.extraServices__cardButton_image {
  width: 24px;
  height: 24px;
  margin: auto;
}
.extraServices__cardTitle {
  width: 175px;
  font-size: 16px;
  line-height: 22px;
  margin: 16px 9px 0 20px;
  text-align: left;
}
.extraServices__cardTitle_small {
  width: 140px;
}
.suppliers {
  width: 1180px;
  margin: 30px auto 46px;
  display: flex;
  flex-direction: column;
  font-family: 'Inter'
}
.suppliers__title {
  margin: 0;
  font-size: 24px;
  line-height: 32px;
  letter-spacing: -0.2px;
  font-weight: 500;
}
.suppliers__cards {
  margin-top: 24px;
  display: grid;
  grid-template-columns: repeat(5, 221px);
  grid-template-rows: repeat(2, 36px);
  column-gap: 18px;
  row-gap: 10px;
}
.suppliers__card {
  display: flex;
  text-decoration: none;
  align-items: center;
}
.suppliers__card:hover {
  border: 1px solid #DEE2E7;
  border-radius: 6px;
  opacity: 0.8;
}
.suppliers__cardImage {
  width: 28px;
  height: 20px;
}
.suppliers__cardContext {
  margin-left: 11px;
}
.suppliers__cardTitle {
  margin: 0;
  font-size: 16px;
  letter-spacing: -0.2px;
  color: black;
  font-weight: 400;
  line-height: 20px;
}
.suppliers__cardSubtitle {
  display: flex;
  font-size: 13px;
  color: #8B96A5;
  text-align: top;
  line-height: 12px;
}
.subscribeForm {
  font-family: 'Inter';
  display: flex;
  flex-direction: column;
  align-items: center;
  background-color: #EFF2F4;
}
.subscribeForm__title {
  margin: 38px 0 0 0;
  font-size: 20px;
  line-height: 28px;
  letter-spacing: -0.2px;
  font-weight: 500;
}
.subscribeForm__subtitle {
  font-size: 16px;
  line-height: 24px;
  color: #606060;
}
.subscribeForm__inputBlock {
  margin: 21px 0 39px 0;
}
.subscribeForm__input{
  max-width: 274px;
  border: 1px solid #DEE2E7;
  border-radius: 6px;
  outline: none;
  font-size: 16px;
  line-height: 19px;
  padding: 11px 0 10px 36px;
  background-image: url(~/assets/images/bodyMain/subscribeInputMail.svg);
  background-repeat: no-repeat;
  background-position: 8px 9px;
}
.subscribeForm__button {
  width: 110px;
  text-align: center;
  font-size: 16px;
  line-height: 19px;
  padding: 10.5px 16px;
  border: none;
  border-radius: 6px;
  color: white;
  background-color: #0D6EFD;
  cursor: pointer;
}
.subscribeForm__button:hover {
  opacity: 0.8;
}
</style>

<template>
  <section class="fairSales">
    <div class="fairSales__calendar">
      <div class="fairSales__calendarTextBlock">
        <h3 class="fairSales__title"> Deals and offers </h3>
        <span class="fairSales__subtitle"> Hygiene equipments </span>
      </div>
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
          <div class="counter__element counter__element_mobileDisplayNone">
            <span class="counter__number"> {{ date.seconds }} </span>
            <span class="counter__title"> Sec </span>
          </div>
      </div>
    </div>
      <div class="fairSales__cards">
        <a class="fairSales__card"
          v-for="card in saleCards"
          :key="card.id"
          :href="card.href"
        >
          <img class="fairSales__cardImage" :src="card.image">
          <span class="fairSales__cardTitle">{{ card.name }}</span>
          <span class="fairSales__cardPercent"> -{{ card.sale }}% </span>
        </a>
      </div>
  </section>
</template>

<script>
export default {
  created () {
    setInterval(this.countDown, 1000)
  },
  data () {
    return {
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
      ]
    }
  },
  methods: {
    countDown () {
      const dateNow = new Date()
      const dateEnd = new Date('12.31.2023 00:00:00')
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
    }
  }
}
</script>

<style>
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
    width: 360px;
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
.fairSales__counter {
  margin-top: 18px;
  width: 198px;
  height: 50px;
  display: grid;
  grid-template-columns: repeat(4, 45px);
  column-gap: 6px;
}
@media screen and (max-width: 879px) {
  .fairSales__counter {
    width: 143px;
    height: 44px;
    grid-template-columns: repeat(3, 45px);
    margin: 10px 10px 0 0;
    column-gap: 4px;
  }
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
@media screen and (max-width: 879px) {
  .counter__element {
    background-color: #EFF2F4;
    color: #8B96A5;
    border-radius: 0;
  }
}
@media screen and (max-width: 879px) {
  .counter__element_mobileDisplayNone {
    display: none;
  }
}
.counter__number {
  margin-top: 8px;
  font-size: 16px;
  font-weight: 600;
  line-height: 19px;
}
@media screen and (max-width: 879px) {
  .counter__number {
    margin-top: 6px;
  }
}
.counter__title {
  font-size: 12px;
  line-height: 15px;
}
@media screen and (max-width: 879px) {
  .counter__title {
    font-size: 11px;
    line-height: 13px;
  }
}
.fairSales__cards {
  display: grid;
  grid-template-columns: repeat(5, 179px);
}
@media screen and (max-width: 879px) {
  .fairSales__cards {
    grid-template-columns: repeat(5, 140px);
    margin-top: 11px;
    overflow-x: scroll;
  }
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

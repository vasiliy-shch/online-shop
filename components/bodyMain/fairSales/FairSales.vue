<template>
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
    }
  }
}
</script>

<style>
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
</style>

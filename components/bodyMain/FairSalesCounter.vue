<template>
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
      }
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
</style>

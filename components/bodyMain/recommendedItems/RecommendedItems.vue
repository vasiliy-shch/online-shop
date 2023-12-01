<template>
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
</template>

<script>
export default {
  data () {
    return {
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
      ]
    }
  }
}
</script>

<style>
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
</style>

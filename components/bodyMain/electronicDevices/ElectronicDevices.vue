<template>
  <section class="homeOutdoor">
    <div class="homeOutdoor__banner gadgetsBackground">
      <h3 class="homeOutdoor__bannerTitle electronicsBanner__title">Consumer electronics and gadgets</h3>
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
</template>

<script>
export default {
  data () {
    return {
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
      ]
    }
  }
}
</script>

<style>
.electronicsBanner__title {
  width: 154px;
}
</style>

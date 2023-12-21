<template>
  <section class="invitingBlock">
    <div class="invitingBlock__banner gadgetsBackground">
      <h3 class="invitingBlock__bannerTitle electronicsBanner__title">Consumer electronics and gadgets</h3>
      <button class="invitingBlock__bannerButton">
        <a class="invitingBlock__bannerButton_text" href="#">Source now</a>
      </button>
    </div>
    <div class="invitingBlock__cards">
      <a
        v-for="card in deviceCards"
        :key="card.id"
        :class="['invitingBlock__card', card.id > 4 ?
          'invitingBlock__card_borderTop' : '']"
      >
        <div class="invitingBlock__textBlock">
          <h3 class="invitingBlock__cardTitle">{{ card.name }}</h3>
          <span class="invitingBlock__cardSubtitle">
            <span> from&nbsp; </span>
            <span> USD {{ card.price }}</span>
          </span>
        </div>
        <img class="invitingBlock__cardImage" :src="card.image">
      </a>
    </div>
    <a class="invitingBlock__mobileLink" href="#">
      <button class="invitingBlock__mobileLink_button">
        Source now
        <img class="invitingBlock__mobileLink_buttonImage" src="~/assets/images/bodyMain/blueArrowRight.svg">
      </button>
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

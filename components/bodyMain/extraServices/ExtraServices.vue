<template>
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
</template>

<script>
export default {
  data () {
    return {
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
      ]
    }
  }
}
</script>

<style>
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
</style>

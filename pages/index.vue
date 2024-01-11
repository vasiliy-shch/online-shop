<template>
  <section class="body__main">
    <MobileCategory/>
    <BigBanner/>
    <FairSales/>
    <InvitingBlock :items="homeList" :bannerTitle="homeListTitle" :bannerImage="homeBannerImage"/>
    <InvitingBlock :items="devicesList" :bannerTitle="devicesListTitle" :bannerImage="devicesBannerImage"/>
    <BigForm/>
    <RecommendedItems/>
    <ExtraServices/>
    <SuppliersShop/>
    <SubscribeForm/>
  </section>
</template>

<script>
import BigBanner from '~/components/bodyMain/BigBanner.vue'
import FairSales from '~/components/bodyMain/FairSales.vue'
import InvitingBlock from '~/components/bodyMain/invitingBlock/InvitingBlock.vue'
import BigForm from '~/components/bodyMain/BigForm.vue'
import RecommendedItems from '~/components/bodyMain/RecommendedItems.vue'
import ExtraServices from '~/components/bodyMain/ExtraServices.vue'
import SuppliersShop from '~/components/bodyMain/SuppliersShop.vue'
import SubscribeForm from '~/components/bodyMain/SubscribeForm.vue'
import MobileCategory from '~/components/bodyMain/MobileCategory.vue'
import { homeCards, HomeCardsTitle, HomeOutdoorBannerImage } from '~/components/bodyMain/invitingBlock/homeOutdoorsItems.js'
import { devicesCards, DevicesCardsTitle, ElectronicDevicesBannerImage } from '~/components/bodyMain/invitingBlock/electronicDevicesItems.js'
export default {
  components: {
    BigBanner,
    FairSales,
    InvitingBlock,
    BigForm,
    RecommendedItems,
    ExtraServices,
    SuppliersShop,
    SubscribeForm,
    MobileCategory
  },
  data () {
    return {
      homeList: homeCards,
      homeListTitle: HomeCardsTitle,
      homeBannerImage: HomeOutdoorBannerImage,
      devicesList: devicesCards,
      devicesListTitle: DevicesCardsTitle,
      devicesBannerImage: ElectronicDevicesBannerImage
    }
  }
}
console.log('1')
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
@media screen and (max-width: 879px) {
  .body__main {
    width: 100%;
    margin: 0 auto;
  }
}
</style>

<template>
  <section class="body__main">
    <MobileCategory/>
    <BigBanner/>
    <FairSales/>
    <HomeOutdoor/>
    <ElectronicDevices/>
    <BigForm/>
    <RecommendedItems/>
    <ExtraServices/>
    <SuppliersShop/>
    <SubscribeForm/>
  </section>
</template>

<script>
import BigBanner from '~/components/bodyMain/bigBanner/BigBanner.vue'
import FairSales from '~/components/bodyMain/fairSales/FairSales.vue'
import HomeOutdoor from '~/components/bodyMain/homeOutdoor/HomeOutdoor.vue'
import ElectronicDevices from '~/components/bodyMain/electronicDevices/ElectronicDevices.vue'
import BigForm from '~/components/bodyMain/bigForm/BigForm.vue'
import RecommendedItems from '~/components/bodyMain/recommendedItems/RecommendedItems.vue'
import ExtraServices from '~/components/bodyMain/extraServices/ExtraServices.vue'
import SuppliersShop from '~/components/bodyMain/suppliers/SuppliersShop.vue'
import SubscribeForm from '~/components/bodyMain/subscribeForm/SubscribeForm.vue'
import MobileCategory from '~/components/bodyMain/mobileCategory/MobileCategory.vue'
export default {
  components: {
    BigBanner,
    FairSales,
    HomeOutdoor,
    ElectronicDevices,
    BigForm,
    RecommendedItems,
    ExtraServices,
    SuppliersShop,
    SubscribeForm,
    MobileCategory
  }
}
</script>

<style>
.body__main {
  display: flex;
  flex-direction: column;
  max-width: 1440px;
  background-color: #F7FAFC;
}
@media screen and (max-width: 879px) {
  .body__main {
    width: 360px;
    margin: 0 auto;
  }
}
</style>

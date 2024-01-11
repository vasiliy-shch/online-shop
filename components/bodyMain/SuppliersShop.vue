<template>
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
</template>

<script>
import russiaFlag from '~/assets/images/flags/ru.svg'
import usaFlag from '~/assets/images/flags/us.svg'
import italiaFlag from '~/assets/images/flags/it.svg'
import germanyFlag from '~/assets/images/flags/ge.svg'
import greatBritainFlag from '~/assets/images/flags/gb.svg'
import franceFlag from '~/assets/images/flags/fr.svg'
import denmarkFlag from '~/assets/images/flags/dk.svg'
import cninaFlag from '~/assets/images/flags/cn.svg'
import australiaFlag from '~/assets/images/flags/au.svg'
import emiratesFlag from '~/assets/images/flags/ae.svg'
export default {
  data () {
    return {
      suppliers: [
        {
          id: 1,
          name: 'Arabic Emirates',
          href: 'shopname.ae',
          image: emiratesFlag
        },
        {
          id: 2,
          name: 'Australia',
          href: 'shopname.au',
          image: australiaFlag
        },
        {
          id: 3,
          name: 'Unated States',
          href: 'shopname.us',
          image: usaFlag
        },
        {
          id: 4,
          name: 'Russia',
          href: 'shopname.ru',
          image: russiaFlag
        },
        {
          id: 5,
          name: 'Italy',
          href: 'shopname.it',
          image: italiaFlag
        },
        {
          id: 6,
          name: 'Denmark',
          href: 'shopname.com.dk',
          image: denmarkFlag
        },
        {
          id: 7,
          name: 'France',
          href: 'shopname.com.fr',
          image: franceFlag
        },
        {
          id: 8,
          name: 'Germany',
          href: 'shopname.com.ge',
          image: germanyFlag
        },
        {
          id: 9,
          name: 'China',
          href: 'shopname.cn',
          image: cninaFlag
        },
        {
          id: 10,
          name: 'Great Britain',
          href: 'shopname.co.uk',
          image: greatBritainFlag
        }
      ]
    }
  }
}
</script>

<style>
.suppliers {
  width: 1180px;
  margin: 30px auto 46px;
  display: flex;
  flex-direction: column;
  font-family: 'Inter'
}
@media screen and (max-width: 879px) {
  .suppliers {
    display: none;
  }
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
</style>

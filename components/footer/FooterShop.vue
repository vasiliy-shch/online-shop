<template>
  <div class="footer">
    <div class="footer__main">
      <div class="footer__logoSection">
        <FooterLogo/>
        <p class="footer__logoSection_title">
          Best information about the
          company <nbsp></nbsp> gies here but now lorem ipsum is
        </p>
        <SocialIcons/>
      </div>
        <FooterMoreUseSection/>
    </div>
    <div class="footer__rest">
      <div class="footer__rest_contentBox">
        <span class="rest__contentBox_span"> &copy; 2023 Ecommerce. </span>
        <FooterLanguages/>
      </div>
    </div>
  </div>
</template>

<script>
import FooterLogo from '~/components/footer/logoSection/logo/FooterLogo.vue'
import SocialIcons from '~/components/footer/logoSection/SocialIcons.vue'
import FooterMoreUseSection from '~/components/footer/moreUseSection/FooterMoreUseSection.vue'
import FooterLanguages from '~/components/footer/footerRest/FooterLanguages.vue'
export default {
  components: {
    FooterLogo,
    SocialIcons,
    FooterMoreUseSection,
    FooterLanguages
  }
}
</script>

<style>
.footer {
  height: 324px;
  margin-top: 100px;
}
@media screen and (max-width: 879px) {
  .footer {
    display: none;
  }
}
.footer__main {
  display: flex;
  height: 256px;
}
.footer__logoSection {
  width: 276px;
  height: 167px;
  margin: 40px 0 0 129px;
}
.footer__logoSection_title {
  color: #505050;
  font-family: 'Inter';
  line-height: 24px;
}
.footer__rest {
  height: 68px;
  background-color: #EFF2F4;
  box-sizing: border-box;
}
.footer__rest_contentBox {
  max-width: 1176px;
  display: flex;
  justify-content: space-between;
  height: 24px;
  margin: 0 auto;
  padding-top: 23px;
}
.rest__contentBox_span {
  color: #606060;
  font-size: 16px;
  line-height: 24px;
  letter-spacing: -0.2px;
}
</style>

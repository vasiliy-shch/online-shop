<template>
  <div class="footer">
    <div class="footer__logoSection">
      <FooterLogo/>
      <p class="footer__logoSection_title">
        Best information about the
        company <nbsp></nbsp> gies here but now lorem ipsum is
      </p>
      <SocialIcons/>
    </div>
  </div>
</template>

<script>
import FooterLogo from '~/components/footer/logo/FooterLogo.vue'
import SocialIcons from '~/components/footer/SocialIcons.vue'
export default {
  components: {
    FooterLogo,
    SocialIcons
  }
}
</script>

<style>
.footer {
  height: 324px;
}
.footer__logoSection {
  width: 276px;
  height: 167px;
  margin: 40px 0 0 129px;
}
.footer__logoSection_title {
  color: #505050;
  font-family: 'Inter';
}
</style>

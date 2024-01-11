<template>
  <div class = "footer__socialIcons">
    <a v-for = "icon in icons"
      class = "footer__socialIcons_icon"
      :key = "icon.id"
      :href = "icon.href"
      target = "_blank"
    >
      <img
        :src = "icon.url"
      >
    </a>
  </div>
</template>

<script>
export default {
  data () {
    return {
      icons: [
        {
          id: 1,
          url: import('~/assets/images/footerSocialIcons/facebook.svg'),
          href: 'https://www.facebook.com/?locale=ru_RU'
        },
        {
          id: 2,
          url: import('~/assets/images/footerSocialIcons/twitter.svg'),
          href: 'https://twitter.com/?lang=ru'
        },
        {
          id: 3,
          url: import('~/assets/images/footerSocialIcons/linkedin.svg'),
          href: 'https://ru.linkedin.com/'
        },
        {
          id: 4,
          url: import('~/assets/images/footerSocialIcons/instagram.svg'),
          href: 'https://www.instagram.com/'
        },
        {
          id: 5,
          url: import('~/assets/images/footerSocialIcons/youtube.svg'),
          href: 'https://www.youtube.com/?gl=RU&hl=ru'
        }
      ]
    }
  }
}
</script>

<style>
.footer__socialIcons {
  height: 32px;
  display: flex;
  margin-top: 15px;
}
.footer__socialIcons_icon {
  margin-right: 10px;
  cursor: pointer;
}
.footer__socialIcons_icon:hover {
  opacity: 0.8;
}
</style>

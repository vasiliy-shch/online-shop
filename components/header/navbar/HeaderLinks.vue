<template>
  <div class="header__links">
    <a
      v-for="link in links"
      :key="link.id"
      :href="link.href"
      :class="link.style"
      >
      {{ link.name }}
    </a>
  </div>
</template>

<script>
export default {
  data () {
    return {
      links: [
        {
          id: 1,
          name: 'All category',
          href: '#',
          style: 'header__links_link header__links_allCategory'
        },
        {
          id: 2,
          name: 'Hot offers',
          href: '#',
          style: 'header__links_link'
        },
        {
          id: 3,
          name: 'Gift boxes',
          href: '#',
          style: 'header__links_link'
        },
        {
          id: 4,
          name: 'Projects',
          href: '#',
          style: 'header__links_link'
        },
        {
          id: 5,
          name: 'Menu item',
          href: '#',
          style: 'header__links_link'
        },
        {
          id: 6,
          name: 'Help',
          href: '#',
          style: 'header__links_link header__links_help'
        }
      ]
    }
  }
}
</script>

<style>
.header__links {
    display: flex;
    width: 586px;
    height: 24px;
    margin: 16px 0;
}
.header__links_link {
    font-size: 16px;
    text-decoration: none;
    color: black;
    margin-right: 28px;
    text-align: center;
    line-height: 22px;
    font-family: "Inter";
}
.header__links_link:hover {
    opacity: 0.6;
}
.header__links_allCategory {
    margin-right: 25px;
}
.header__links_help {
    width: 61px;
    text-align: left;
    background-image: url(~/images/apperance.svg);
    background-repeat: no-repeat;
    background-size: 24px 24px;
    background-position-x: 33px;
}
</style>

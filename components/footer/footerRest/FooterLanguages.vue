<template>
  <div class="footer__languages">
    <div v-if="!isEdit">
      <div class="footer__language" @click = "show">
        <img class="footer__language_image" :src="selectedLanguage.url">
        <span class="footer__language_title">
          {{ selectedLanguage.name }}
        </span>
        <div class="footer__languages_button"></div>
      </div>
    </div>
    <div v-else-if="isEdit">
      <div class="footer__language_list">
        <div
          v-for="language in languages"
          :key ="language.id"
          :class = "['footer__language_inList',
            selectedLanguage.id === language.id ?
            'footer__language_selected' : '']"
          @click="select(language)"
        >
        <img class="footer__language_image" :src="language.url">
        <span class="footer__language_titleInList">{{ language.name }}</span>
        </div>
      </div>
      <div class="footer__language" @click="hide">
        <img class="footer__language_image" :src="selectedLanguage.url">
        <span class="footer__language_title">
          {{ selectedLanguage.name }}
        </span>
        <div class="footer__languages_button"></div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data () {
    return {
      isEdit: false,
      selectedLanguage: {
        id: 1,
        name: 'Russian',
        styles: '',
        url: require('~/assets/images/flags/ru.svg')
      },
      languages: [
        {
          id: 1,
          name: 'Russian',
          styles: 'ship__country_selected',
          url: require('~/assets/images/flags/ru.svg')
        },
        {
          id: 2,
          name: 'English',
          styles: '',
          url: require('~/assets/images/flags/us.svg')
        },
        {
          id: 3,
          name: 'Italian',
          styles: '',
          url: require('~/assets/images/flags/it.svg')
        },
        {
          id: 4,
          name: 'German',
          styles: '',
          url: require('~/assets/images/flags/ge.svg')
        },
        {
          id: 5,
          name: 'British',
          styles: '',
          url: require('~/assets/images/flags/gb.svg')
        },
        {
          id: 6,
          name: 'French',
          styles: '',
          url: require('~/assets/images/flags/fr.svg')
        },
        {
          id: 7,
          name: 'Danish',
          styles: '',
          url: require('~/assets/images/flags/dk.svg')
        },
        {
          id: 8,
          name: 'Chinese',
          styles: '',
          url: require('~/assets/images/flags/cn.svg')
        },
        {
          id: 9,
          name: 'Australian',
          styles: '',
          url: require('~/assets/images/flags/au.svg')
        },
        {
          id: 10,
          name: 'Arab',
          styles: 'ship__country_borderBottom',
          url: require('~/assets/images/flags/ae.svg')
        }
      ]
    }
  },
  methods: {
    show () {
      this.isEdit = true
    },
    hide () {
      this.isEdit = false
    },
    select (language) {
      this.selectedLanguage = language
      this.isEdit = false
    }
  }
}
</script>

<style>
.footer__languages {
  display: flex;
  flex-direction: column-reverse;
  width: 131px;
}
.footer__languages_button {
padding: 0;
border: none;
background-image: url(~/assets/images/apperanceTop.svg);
width: 24px;
height: 24px;
background-repeat: no-repeat;
}
.footer__language {
  display: flex;
  height: 24px;
  align-items: center;
}
.footer__language_title {
  color: #606060;
  font-family: 'Inter';
  font-size: 16px;
  letter-spacing: -0.2px;
  line-height: 24px;
}
.footer__language_image {
  width: 24px;
  height: 24px;
  margin-right: 6px;
}
.footer__language_list {
  border: 1px solid #EFF2F4;
  box-shadow: 0 -4px 4px rgba(0,0,0,0.25);
  margin-bottom: 24px;
  z-index: 1;
  background-color: white;
}
.footer__language_inList {
  display: flex;
  padding-top: 5px;
  font-size: 16px;
}
.footer__language_inList:hover {
  background-color: #E5F1FF;
}
.footer__language_titleInList {
  font-family: 'Inter';
  font-size: 16px;
  letter-spacing: -0.2px;
  line-height: 24px;
}
.footer__language_selected {
  color: #0D6EFD;
}
</style>

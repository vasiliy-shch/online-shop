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
      isEdit: false,
      selectedLanguage: {
        id: 1,
        name: 'Russian',
        styles: '',
        url: russiaFlag
      },
      languages: [
        {
          id: 1,
          name: 'Russian',
          styles: 'ship__country_selected',
          url: russiaFlag
        },
        {
          id: 2,
          name: 'English',
          styles: '',
          url: usaFlag
        },
        {
          id: 3,
          name: 'Italian',
          styles: '',
          url: italiaFlag
        },
        {
          id: 4,
          name: 'German',
          styles: '',
          url: germanyFlag
        },
        {
          id: 5,
          name: 'British',
          styles: '',
          url: greatBritainFlag
        },
        {
          id: 6,
          name: 'French',
          styles: '',
          url: franceFlag
        },
        {
          id: 7,
          name: 'Danish',
          styles: '',
          url: denmarkFlag
        },
        {
          id: 8,
          name: 'Chinese',
          styles: '',
          url: cninaFlag
        },
        {
          id: 9,
          name: 'Australian',
          styles: '',
          url: australiaFlag
        },
        {
          id: 10,
          name: 'Arab',
          styles: 'ship__country_borderBottom',
          url: emiratesFlag
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
  cursor: pointer;
}
.footer__language:hover {
  opacity: 0.8;
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
  cursor: pointer;
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

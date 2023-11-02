<template>
  <div class="header__languages">
    <div v-if="!isEdit">
      <div class="header__language">
        <p
        class="header__language_title"
        @click="show"
        >
          {{ selectedLanguage.name }}, {{ selectedLanguage.currency }}
        <button class="header__language_button"></button>
        </p>
      </div>
    </div>
    <div v-else-if="isEdit">
      <div class="header__language">
      <p
      class="header__language_title"
      @click="hide">
        {{ selectedLanguage.name }}, {{ selectedLanguage.currency }}
      <button class="header__language_button"></button>
      </p>
      </div>
      <div class="header__language_list">
      <div
        v-for="language in languages"
        :key="language.id"
        :id="language.id"
        :class='[language.styles, "header__languageInList"]'
        @click="select(language.id)"
      >
      <p class="header__languageInList_title">
        {{ language.name }}, {{ language.currency }}
      </p>
      </div>
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
        name: 'Russian',
        currency: 'RUB'
      },
      languages: [
        {
          id: 1,
          name: 'English',
          currency: 'USD',
          styles: ''
        },
        {
          id: 2,
          name: 'Russian',
          currency: 'RUB',
          styles: 'header__language_selected'
        },
        {
          id: 3,
          name: 'German',
          currency: 'EU',
          styles: ''
        },
        {
          id: 4,
          name: 'Chinese',
          currency: 'CNY',
          styles: ''
        },
        {
          id: 5,
          name: 'Indian',
          currency: 'INR',
          styles: ''
        },
        {
          id: 6,
          name: 'English',
          currency: 'GBP',
          styles: ''
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
    select (id) {
      this.languages = this.languages.map((language) => {
        if (language.id === id) {
          language.styles = 'header__language_selected'
          this.selectedLanguage.name = language.name
          this.selectedLanguage.currency = language.currency
          this.isEdit = false
        } else {
          language.styles = ''
        }
        return language
      })
    }
  }
}
</script>

<style>
.header__languages {
    width: 132px;
    margin-left: 270px;
    font-size: 16px;
    font-family: 'Inter';
    display: flex;
    cursor: pointer;
}
.header__language {
  display: flex;
  align-items: center;
  width: 132px;
  height: 24px;
  margin: 16px 0;
}
.header__language_title {
    font-size: 16px;
    display: flex;
}
.header__language_title:hover {
  opacity: 0.6;
}
.header__language_list {
  border: 1px solid #EFF2F4;
  box-shadow: 0 4px 4px rgba(0,0,0,0.25)
}
.header__languageInList {
  height: 36px;
  display: flex;
  justify-content: flex-start;
}
.header__languageInList_title {
  margin: 8px 0 8px 8px;
}
.header__language_selected {
  color: #0D6EFD;
}
.header__languageInList:hover {
  background-color: #E5F1FF;
}
.header__language_button {
  background-color: white;
  border: none;
  background-image: url(~/assets/images/apperance.svg);
  width: 24px;
  height: 24px;
  background-repeat: no-repeat;
  margin-left: 2px;
  cursor: pointer;
}
</style>

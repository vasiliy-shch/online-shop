<template>
  <select class="header__languages">
    <option
    class="header__language"
    v-for="language in languages"
    :key="language.id"
    >
        {{ language.name }}, {{ language.currency }}
    </option>
  </select>
</template>

<script>
export default {
  data () {
    return {
      languages: [
        {
          id: 1,
          name: 'English',
          currency: 'USD'
        },
        {
          id: 2,
          name: 'Russian',
          currency: 'RUB'
        },
        {
          id: 3,
          name: 'German',
          currency: 'EU'
        },
        {
          id: 4,
          name: 'Chinese',
          currency: 'CNY'
        },
        {
          id: 5,
          name: 'Indian',
          currency: 'INR'
        },
        {
          id: 6,
          name: 'English',
          currency: 'GBP'
        }
      ]
    }
  }
}
</script>

<style>
.header__languages {
    width: 124px;
    margin-left: 300px;
    font-size: 16;
    border: 0;
    background-color: white;
    outline: none;
    appearance: none;
    background-image: url(~/images/apperance.svg);
    background-repeat: no-repeat;
    background-size: 24px 24px;
    background-position: 96px 50%;
}
.header__language {
    font-size: 16px;
}
</style>

<template>
  <div>
  <div v-if=selected>
    <img :src=src>
  </div>
  <div v-else class="ship__country" @click="$emit('check', id)">
    <div :class=styles>
      {{ name }}
    </div>
    <img :src=src>
  </div>
  </div>
</template>

<script>
export default {
  emits: ['check', 'filter'],
  props: {
    id: Number,
    name: String,
    styles: String,
    src: String,
    selected: Boolean
  },
  methods: {
  }
}
</script>

<style scoped>
/* остановились тут, пишем стили для селектов, убираем из родителя */
.ship__country {
  display: flex;
  justify-content: space-between;
  text-align: center;
  align-items: center;
  width: 200px;
  height: 40px;
  border-top: 1px solid #EFF2F4;
}
.ship__country:hover {
  background-color: #E5F1FF;
}
.ship__country_selected {
  color: #0D6EFD;
}
</style>

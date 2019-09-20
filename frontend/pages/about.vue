<template>
  <div class="about">
    <div v-for="list in lists" :key="list.id" class="lists__item">
      {{ list.title }}
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      lists: []
    }
  },
  async asyncData({ $axios }) {
    const data = await $axios.$get('/api/v1/lists')
    return { lists: data }
  }
}
</script>

<style lang="scss" scoped>
.flex {
  margin-bottom: 2rem;
}
</style>

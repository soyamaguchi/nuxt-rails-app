<template>
  <div class="container">
    <header class="container__header">
      <h1 class="container__title">Hello World</h1>
    </header>
    <ListsContainer />
    <!-- <div v-for="list in lists" :key="list.title">
      {{ list }}
    </div> -->
  </div>
</template>

<script>
import ListsContainer from '~/components/ListsContainer.vue'

export default {
  components: {
    ListsContainer
  }
  // data() {
  //   return {
  //     lists: []
  //   }
  // },
  // mounted() {
  //   this.getLists()
  // },
  // methods: {
  //   async getLists() {
  //     const { data } = await this.$axios.$get('/lists')
  //     return { lists: data }
  //   }
  // }
  // async asyncData({ app }) {
  //   const { data } = await app.$axios.$get('/lists')
  //   return { lists: data }
  // }
}
</script>

<style>
.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.title {
  font-family: 'Quicksand', 'Source Sans Pro', -apple-system, BlinkMacSystemFont,
    'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
  display: block;
  font-weight: 300;
  font-size: 100px;
  color: #35495e;
  letter-spacing: 1px;
}

.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}

.links {
  padding-top: 15px;
}
</style>

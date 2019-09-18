<template>
  <div class="home">
    <ListsContainer />
  </div>
</template>

<script>
import ListsContainer from '~/components/ListsContainer.vue'

export default {
  components: {
    ListsContainer
  },
  data() {
    return {}
  }
}
</script>

<style lang="scss" scoped>
.flex {
  margin-bottom: 2rem;
}
</style>

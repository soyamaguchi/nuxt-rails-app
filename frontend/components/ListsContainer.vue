<template>
  <div class="lists">
    <div v-for="list in lists" :key="list.id" class="lists__item">
      {{ list.title }}
    </div>
    <NewListForm />
  </div>
</template>

<script>
import NewListForm from './NewListForm.vue'

export default {
  components: {
    NewListForm
  },  
  data() {
    return {
      lists: []
    }
  },
  mounted() {
    this.getLists()
  },
  methods: {
    async getLists() {
      this.lists = await this.$axios.$get('/lists')
    }
  }
}
</script>

<style lang="scss" scoped></style>

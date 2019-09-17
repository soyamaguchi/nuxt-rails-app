<template>
  <div class="lists">
    <!-- <div v-for="list in lists" :key="list.id"> -->
    {{ lists.title }}
    <!-- </div> -->
  </div>
</template>

<script>
export default {
  data() {
    return {
      lists: {}
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

<style></style>

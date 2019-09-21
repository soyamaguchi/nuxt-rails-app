<template>
  <div class="home">
    <ListsContainer @set="editList" />
    <NewListForm />
  </div>
</template>

<script>
import ListsContainer from '~/components/ListsContainer.vue'
import NewListForm from '~/components/NewListForm.vue'

export default {
  components: {
    ListsContainer,
    NewListForm
  },
  data() {
    return {
      lists: [],
      editingList: ''
    }
  },
  async asyncData({ $axios }) {
    const data = await $axios.$get('/api/v1/lists')
    return { lists: data }
  },
  methods: {
    editList(list) {
      this.editingList = list
    }
  }
}
</script>

<style lang="scss" scoped>
.flex {
  margin-bottom: 2rem;
}
</style>

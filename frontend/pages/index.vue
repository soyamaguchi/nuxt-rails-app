<template>
  <div class="home">
    <template v-if="editTargetList">
      <EditListForm :list="editTargetList" @set="editingList" />
    </template>
    <template v-else>
      <ListsContainer @set="editingList" />
      <NewListForm />
    </template>
  </div>
</template>

<script>
import ListsContainer from '~/components/ListsContainer.vue'
import NewListForm from '~/components/NewListForm.vue'
import EditListForm from '~/components/EditListForm.vue'

export default {
  components: {
    ListsContainer,
    NewListForm,
    EditListForm
  },
  data() {
    return {
      lists: [],
      editTargetList: ''
    }
  },
  async asyncData({ $axios }) {
    const data = await $axios.$get('/api/v1/lists')
    return { lists: data }
  },
  methods: {
    editingList(list = '') {
      this.editTargetList = list
    }
  }
}
</script>

<style lang="scss" scoped>
.flex {
  margin-bottom: 2rem;
}
</style>

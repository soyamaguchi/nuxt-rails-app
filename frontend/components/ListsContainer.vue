<template>
  <div class="lists">
    <div v-for="list in lists" :key="list.id" class="lists__item">
      <h2>{{ list.title }}</h2>
      <v-btn class="mx-2" fab dark color="pink" @click="removeList(list.id)">
        <v-icon dark>mdi-minus</v-icon>
      </v-btn>
    </div>
    <NewListForm :lists="lists" />
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
      lists: this.$parent.lists
    }
  },
  mounted() {},
  methods: {
    removeList(id) {
      this.$axios
        .delete(`/api/v1/lists/${id}`)
        .then((res) => {
          // const lists = this.$parent.lists.filter((l) => l.id !== id)
          this.$parent.lists.splice(0, 1)
          // this.$set(this.$parent.lists, 0, lists)
        })
        .catch((err) => {
          console.log(err)
        })
    }
  }
}
</script>

<style lang="scss" scoped>
.lists {
  &__item {
    display: flex;
  }
}
</style>

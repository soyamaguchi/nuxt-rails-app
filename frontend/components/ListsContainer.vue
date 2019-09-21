<template>
  <div class="lists">
    <div v-for="list in this.$parent.lists" :key="list.id" class="lists__item">
      <h2>{{ list.title }}</h2>
      <v-btn class="mx-2" fab dark color="pink" @click="removeList(list.id)">
        <v-icon dark>mdi-minus</v-icon>
      </v-btn>
      <v-btn class="mx-2" fab dark color="cyan" @click="$emit('set', list)">
        <v-icon dark>mdi-pencil</v-icon>
      </v-btn>
    </div>
  </div>
</template>

<script>
export default {
  components: {},
  data() {
    return {}
  },
  mounted() {},
  methods: {
    removeList(id) {
      this.$axios
        .delete(`/api/v1/lists/${id}`)
        .then((res) => {
          const lists = this.$parent.lists.filter((l) => l.id !== id)
          this.$parent.lists = lists
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

<template>
  <v-flex>
    <v-card>
      <v-card-text>
        <v-form>
          <v-text-field v-model="title" label="title" />
          <v-text-field v-model="excerpt" label="excerpt" type="text" />
        </v-form>
        <v-card-actions>
          <v-btn @click="addList">Add List</v-btn>
        </v-card-actions>
      </v-card-text>
    </v-card>
  </v-flex>
</template>

<script>
export default {
  data() {
    return {
      title: '',
      excerpt: ''
    }
  },
  methods: {
    addList() {
      this.$axios
        .$post('/lists', { title: this.title, excerpt: this.excerpt })
        .then((res) => {
          this.$router.push({ path: '/' })
        })
    }
  }
}
</script>

<style lang="scss" scoped></style>

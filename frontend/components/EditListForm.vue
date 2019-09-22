<template>
  <v-flex>
    <v-card>
      <v-card-text>
        <v-form>
          <v-text-field label="title" v-model="title" />
          <v-text-field label="excerpt" v-model="excerpt" />
        </v-form>
        <v-card-actions>
          <v-btn class="mx-2" fab dark color="teal" @click="editList">
            <v-icon dark>mdi-pencil</v-icon>
          </v-btn>
        </v-card-actions>
      </v-card-text>
    </v-card>
  </v-flex>
</template>

<script>
export default {
  props: ['list'],
  data() {
    return {
      id: this.list.id,
      title: this.list.title,
      excerpt: this.list.excerpt
    }
  },
  methods: {
    editList() {
      this.$axios
        .$put(`/api/v1/lists/${this.id}`, {
          title: this.title,
          excerpt: this.excerpt
        })
        .then((res) => {
          const lists = this.$parent.lists.map((l) => {
            return l.id === this.id ? res : l
          })
          this.$parent.lists = lists
          this.$emit('set')
        })
        .catch((err) => {
          console.log(err)
        })
    }
  }
}
</script>

<style lang="scss" scoped></style>

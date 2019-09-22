<template>
  <div id="app">
    <v-app>
      <v-toolbar>
        <n-link id="top" to="/">Separate Sample</n-link>
      </v-toolbar>
      <v-content>
        <v-container fluid>
          <nuxt />
        </v-container>
      </v-content>
    </v-app>
  </div>
</template>

<style lang="scss">
body {
  margin: 0 auto;
  a#top {
    text-decoration: none;
    color: #616161;
    font-weight: bold;
    font-size: 1.5rem;
  }
  .container {
    margin: 0 auto;
    min-height: 100vh;
    display: flex;
    justify-content: center;
    align-items: center;
    text-align: center;
  }
}
</style>

<template>
  <v-app dark>
    <Navbar />
    <v-main>
      <v-container>
        <nuxt  id="h1" />
      </v-container>
    </v-main>

  </v-app>
</template>


<script>
import Navbar from '../components/Navbar.vue'

export default {
  components: { Navbar },
}
</script>

<style scoped>
#h1 h1{
  font-family: 'Potta One', cursive;
}
</style>

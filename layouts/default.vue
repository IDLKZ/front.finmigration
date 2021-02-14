<template>
  <v-app class="px-2">
    <Header></Header>
    <v-main>
      <Nuxt/>
    </v-main>

    <Footer></Footer>

  </v-app>
</template>
<script>
import Header from "../components/Header";
import Footer from "../components/Footer";
export default {
  components: {Footer, Header}
}

</script>
<style>

</style>

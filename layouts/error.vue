<template>

    <v-container>
      <v-row>
        <v-col cols="12" md="8" offset-md="2" class="text-center">
          <lottie :width="'100%'" :height="450" :options="lottieOptions" v-on:animCreated="handleAnimation" />
        </v-col>
        <v-col cols="12" md="8" offset-md="2" class="text-center">
          <h3 class="text-red-100">Упс, кажись вы ошиблись</h3>
          <v-btn link to="/" color="primary">
            <v-icon>mdi-home</v-icon>
            Главная
          </v-btn>
        </v-col>

      </v-row>
    </v-container>
</template>

<script>
  import lottie from 'vue-lottie/src/lottie.vue';
  import * as animationData from "static/animation/404.json";
export default {
  layout: 'default',
  props: {
    error: {
      type: Object,
      default: null
    }
  },
  components:{
    lottie
  },

  data () {
    return {
      anim: null, // for saving the reference to the animation
      lottieOptions: { animationData: animationData.default },
      pageNotFound: '404 Not Found',
      otherError: 'An error occurred'
    }
  },
  head () {
    const title =
      this.error.statusCode === 404 ? this.pageNotFound : this.otherError
    return {
      title
    }
  },
  methods: {
    handleAnimation: function (anim) {
      this.anim = anim;
    }
  }
}
</script>

<style scoped>
h1 {
  font-size: 20px;
}
</style>

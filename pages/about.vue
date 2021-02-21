<template>
  <div>
    <v-container fluid>
      <v-row class="my-5 py-5">
        <v-col cols="12" md="6" >
          <lottie :options="lottieOptions.social" v-on:animCreated="handleAnimation"></lottie>
        </v-col>
        <v-col cols="12" md="6">
          <div class="text-h4 mb-5">Немного о нас</div>
          <div class="text-subheading">
            Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.
          </div>
        </v-col>
      </v-row>
    </v-container>
  </div>
</template>

<script>
import lottie from "vue-lottie/src/lottie.vue";
import  * as social from "/static/animation/social.json";
export default {
  name: "about",
  components:{
    lottie
  },
  data: () => ({
    items: [
      {
        text: 'Главная',
        disabled: false,
        to: '/',
      },
      {
        text: 'О нас',
        disabled: false,
        href: '/about',
        to: '/about',
      },
    ],
    lottieOptions:{
      social:{animationData:social.default}
    }
  }),
  methods: {
    handleAnimation: function (anim) {
      this.anim = anim;
    }
  },
}
</script>

<style scoped>

</style>

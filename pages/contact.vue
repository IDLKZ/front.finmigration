<template>
  <div>
    <!-- width and height are optional -->
    <v-container>
      <v-row class="my-5 py-5">
        <v-col cols="12" md="12" style="padding: 0!important;">
          <v-breadcrumbs :items="items" divider=">" class="pl-0">
            <template v-slot:item="{ item }">
              <v-breadcrumbs-item
                :href="item.href"
                :disabled="item.disabled"
              >
                {{ item.text.toUpperCase() }}
              </v-breadcrumbs-item>
            </template>
          </v-breadcrumbs>
        </v-col>
        <v-col cols="12" md="6" class="px-5">
          <div class="text-h3 mb-5 pb-5">
            Напишите нам
          </div>
          <v-form>
            <v-text-field
              outlined
              required
              prepend-icon="mdi-account-circle"
              label="Ваше ФИО"
            ></v-text-field>
            <v-text-field
              outlined
              required
              prepend-icon="mdi-phone"
              label="Номер телефона"
            ></v-text-field>
            <v-text-field
              type="email"
              outlined
              required
              label="Ваша почта"
              prepend-icon="mdi-email"
            ></v-text-field>
            <v-textarea
              outlined
              prepend-icon="mdi-message"
              label="Ваше сообщение"
            >
            </v-textarea>
            <div class="text-right">
              <v-btn
                depressed
                color="primary"
              >
                Отправить
              </v-btn>

            </div>


          </v-form>


        </v-col>
        <v-col cols="12" md="6">
          <lottie :width="'100%'" :height="450" :options="lottieOptions" v-on:animCreated="handleAnimation" />

        </v-col>
      </v-row>
    </v-container>


  </div>
</template>

<script>
import lottie from 'vue-lottie/src/lottie.vue';
import * as animationData from "static/animation/contact.json";
export default {
  name: "contact",
  components: {
    lottie
  },
  data() {
    return {
      anim: null, // for saving the reference to the animation
      lottieOptions: { animationData: animationData.default },
      items: [
        {
          text: 'Главная',
          disabled: false,
          to: '/',
        },
        {
          text: 'Контакты',
          disabled: false,
          href: '/contact',
          to: '/contact',
        },

      ],
    };
  },
  methods: {
    handleAnimation: function (anim) {
      this.anim = anim;
    }
  }
}
</script>

<style scoped>

</style>

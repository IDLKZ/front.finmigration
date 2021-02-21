<template>
  <section>
    <v-container fluid v-if="conference">
      <v-col cols="12">
        <template>
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
        </template>
      </v-col>
          <v-img
            gradient="to top right, rgba(100,115,201,.33), rgba(25,32,72,.7)" class="d-flex justify-center align-center"
            :src="$store.state.image + conference.img"
          >
           <v-row>
             <v-col cols="12" md="4" class="pa-5 mx-md-5">
              <v-card  class="pa-5">
                <div class="my-2">
                  <h1 class="text-uppercase" style="color: #5168E1">Хочу участвовать!</h1>
                </div>
                <v-form
                  ref="form"
                  lazy-validation
                >
                  <v-text-field
                    label="ФИО"
                    required
                    outlined
                    color="#5168E1"
                  ></v-text-field>
                  <v-text-field
                    label="Номер телефона"
                    required
                    outlined
                    color="#5168E1"
                  ></v-text-field>
                  <v-text-field
                    label="Email"
                    required
                    outlined
                    color="#5168E1"
                  ></v-text-field>
                  <div class="text-center">
                    <v-btn
                      color="#5168E1"
                      x-large
                      dark
                    >
                      Участвовать!
                    </v-btn>
                  </div>
                </v-form>
              </v-card>
             </v-col>
             <v-col cols="12" md="6" class="d-flex justify-center align-center border-white">
               <div class="text-md-h3 text-sm-h4 white--text font-weight-bold text-center">
                 {{conference.title}}
                 <br>
                 <div class="text-md-h4 text-sm-h5 my-2 py-2">
                   <v-icon dark class="text-md-4 text-sm-h5">mdi-clock-outline</v-icon>{{$moment.utc(conference.start).format("LLL")}} - {{$moment.utc(conference.end).format("LLL")}}
                 </div>
               </div>
             </v-col>
           </v-row>
          </v-img>
          <v-row class="my-5">
            <v-col cols="12" md="10" offset-md="1" class="py-5">
              <div class="my-3 d-flex justify-end">
                Поделиться:
                <yandex-share :services="['vkontakte','facebook','twitter','whatsapp','telegram']" counter />
              </div>
              <div class="my-5 " v-html="conference.content"></div>
              <hr>
              <div class="my-5 " v-html="conference.advantages"></div>
            </v-col>
          </v-row>
    </v-container>
  </section>
</template>

<script>
import YandexShare from '@cookieseater/vue-yandex-share';
export default {
  name: "alias",
  components:{
    YandexShare
  },
  async asyncData({$axios,route}){
    let items =  [{text: 'Главная', disabled: false, to: '/',href:"/"}, {text: 'Конференции', disabled: false, to: '/conference',href: '/conference',},];
    const conference = await $axios.$get("/conference-show/" + route.params.alias);
    if(conference){
      items.push({text: conference.title,disabled: true,to: "/conference" + conference.alias, href: "/conference" + conference.alias,})
    }
    return {conference,items};
  }


}
</script>

<style scoped>
.border-white{
  border-top: 2px double white;
  border-bottom: 2px double white;
}
</style>

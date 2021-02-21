<template>
  <v-container>
    <v-row>
      <v-col cols="12" md="9">
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

        <h1 class="mt-3">{{news.title}}</h1>
        <div class="my-2">
          <p class="text-muted">{{news.subtitle}}</p>
        </div>
        <div class="my-5">
          <v-avatar color="primary" class="white--text" size="34">А</v-avatar> ADMIN  - {{$moment(news.created_at).format('LLL')}}
        </div>
        <v-img max-height="500px" :src="$store.state.image + news.img"></v-img>
        <small>{{news.img_description}}</small>
        <div class="my-3 d-flex justify-end">
          Поделиться:
          <yandex-share :services="['vkontakte','facebook','twitter','whatsapp','telegram']" counter />
        </div>
        <div class="my-5 " v-html="news.content"></div>
        <div class="my-5">
          <v-btn
            v-for="(item,index) in news.tags"
            :key="item.title"
            class="ma-2"
            outlined
            color="indigo"
            link
            :to="'/tag/' + item.title"
          >
            {{item.title}}
          </v-btn>
        </div>


      </v-col>
      <v-col cols="12" md="3">
        <h3 class="mt-3">Социальные сети</h3>
        <template>
          <v-progress-linear value="15" background-color="#eeeeee"></v-progress-linear>
        </template>

        <div class="pt-md-2 text-center text-md-left mt-4">
          <v-btn color="error" class="px-2 white--text social" v-for="(item,index) in social" :key="index">
            <v-icon style="margin: 0 auto!important;">{{item.icon}}</v-icon>
          </v-btn>
        </div>
        <v-sheet class="my-2" color="yellow" height="345">Ads</v-sheet>
        <template v-if="latestNews.length > 0">
          <h3 class="mt-3">Последние вести</h3>
          <template >
            <v-progress-linear value="15" background-color="#eeeeee"></v-progress-linear>
          </template>

          <v-card v-for="(item, index) in latestNews" :key="item.title"
                  class="mx-auto mt-3"
                  max-width="400"
                  link :to="'/news/' + item.alias"
          >
            <v-img
              class="white--text align-end"
              height="160px"
              :src="$store.state.image + item.img"
            >
            </v-img>

            <v-card-text class="text--primary">
              <div><strong>{{item.title}}</strong></div>
            </v-card-text>

            <v-card-actions class="pl-4">
              <div class="text-muted">{{$moment(Date.parse(item.created_at)).format('LLL')}}</div>
            </v-card-actions>
          </v-card>
        </template>

      </v-col>
    </v-row>
  </v-container>
</template>

<script>
import YandexShare from '@cookieseater/vue-yandex-share';
export default {
  name: "article",
  components:{
    YandexShare
  },
  async validate({$axios, route}){
    const news = await $axios.$get("/news/" + route.params.alias);
    if(news.id !== undefined){
      return true;
    }
    else{
      return  false;
    }
  },

  data() {
    return {
      items: [
        {
          text: 'Home',
          disabled: false,
          href: 'breadcrumbs_dashboard',
        },
        {
          text: 'Category',
          disabled: false,
          href: 'breadcrumbs_link_1',
        },
        {
          text: 'Business',
          disabled: true,
          href: 'breadcrumbs_link_2',
        },
      ],
      social:[
        {url:"",icon:"mdi-facebook"},
        {url:"",icon:"mdi-twitter"},
        {url:"",icon:"mdi-instagram"},
        {url:"",icon:"mdi-pinterest"},
        {url:"",icon:"mdi-youtube"},
        {url:"",icon:"mdi-linkedin"},
      ],
      page: 1
    }
  },

  async asyncData({$axios,route}){
    const news = await $axios.$get("/news/" + route.params.alias);
    const latestNews = await $axios.$get("/latest-news/3");
    return {news,latestNews};
  }
}
</script>

<style scoped>
.p-0 {
  padding: 0!important;
}
.m-0 {
  margin: 0!important;
}
.v-card {
  border-bottom: 1px white solid;
  border-right: 1px white solid;
  border-radius: 0;
}
.text-muted {
  color: #53585c;
}
.social {
  width: 88px!important;
  height: 88px!important;
  border-radius: 0;
  background-color: transparent!important;
  color: black!important;
}
.trend {
  font-size: 13px;
  line-height: normal;
}
</style>

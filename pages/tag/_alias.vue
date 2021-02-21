<template>
<section>
<v-container>
  <v-row v-if="news.length">
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
    <v-col cols="12" md="8">
      <template>
        <strong class="text-uppercase">Новости по тегу - {{$route.params.alias}}</strong>
        <v-progress-linear value="7" background-color="#ececec" color="#5168E1" height="2"></v-progress-linear>
      </template>
      <v-row class="my-5">
        <v-col cols="12" md="6" v-for="(item,index) in news" :key="index">
          <v-card
            link
            :to="'/news/' + item.alias"
            class="mx-auto"
            max-width="344"
            elevation="0"
          >
            <v-img
              :src="$store.state.image + item.img"
              height="200px"
            ></v-img>
            <v-card-title>
              {{item.title}}
            </v-card-title>
            <v-card-subtitle class="mt-2">
              <v-icon small color="#2E9FFF">mdi-clock-outline</v-icon>{{$moment(item.created_at).format('LLL')}}
            </v-card-subtitle>
          </v-card>
        </v-col>
        <template v-if="last_page>1">
          <div class="text-center mt-4">
            <v-pagination
              v-model="current_page"
              :length="last_page"
            ></v-pagination>
          </div>
        </template>
      </v-row>
    </v-col>
    <v-col cols="12" md="4">
      <template>
        <strong class="text-uppercase">Последние новости</strong>
        <v-progress-linear value="7" background-color="#ececec" color="#5168E1" height="2"></v-progress-linear>
      </template>
      <v-row class="my-5">
        <v-card v-for="(item, index) in latestNews" :key="index" color="white" light link :to="'/news/' + item.alias" class="mb-2">
          <div class="d-flex flex-no-wrap justify-space-between">
            <v-avatar class="ma-3" size="125" tile>
              <v-img
                :src="$store.state.image + item.img"></v-img>
            </v-avatar>
            <div>
              <v-card-title class="text-subtitle-2 text-wrap">
                {{item.title}}
              </v-card-title>
              <v-card-subtitle class="mt-2">
                <v-icon small color="#2E9FFF">mdi-clock-outline</v-icon>{{$moment(item.created_at).format('LLL')}}
              </v-card-subtitle>
            </div>
          </div>
        </v-card>
      </v-row>
    </v-col>
  </v-row>
  <v-row v-else>
    <v-col cols="12">
      <h1 class="red--text text-uppercase">Новости по тегу {{$route.params.alias}} не найден</h1>
    </v-col>
  </v-row>
</v-container>
</section>
</template>

<script>
export default {
  name: "_alias",
  data(){
    return{
      current_page: 1,
      last_page: 1,
      news:[],
    }
  },
  watch:{
    current_page(){
      this.loadPage();
    }
  },
  methods:{
    async loadPage(){
      let data = await this.$axios.$get("/news-by-tag/" + this.$route.params.alias + "?page=" + this.current_page);
      this.news = data["data"];
      this.current_page = data["current_page"];
      this.last_page = data["last_page"];
    }
  },
  async asyncData({$axios,route}){
    const items = [{text: 'Главная', disabled: false, href: '/',}, {text: 'Теги', disabled: true, href: '/',},];
    items.push({text:route.params.alias,disabled: true,href: "/tag/" + route.params.alias});
    let data = await $axios.$get("/news-by-tag/" + route.params.alias);
    let latestNews = await $axios.$get("/latest-news/" + 5);
    let current_page,last_page = 1;
    let news = [];
    if(data["data"].length > 0){
      current_page = data["current_page"];
      last_page = data["last_page"];
      news = data["data"];
    }
    return {news,last_page,current_page,latestNews,items}



  }




}
</script>

<style scoped>

</style>

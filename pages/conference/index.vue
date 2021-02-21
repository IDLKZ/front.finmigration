<template>
<section>
  <v-container v-if="news.length">
    <v-row>
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
    </v-row>
    <v-row v-if="latestNews.length">
      <v-col cols="12" md="6" v-for="(item,index) in latestNews.slice(0,2)" :key="index">
        <v-card
        link
        :to="'/conference/' + item.alias"
        >
          <v-img
            :src="$store.state.image + item.img"
            class="white--text align-end"
            gradient="to bottom, rgba(0,0,0,.1), rgba(0,0,0,.5)"
            height="420px"
          >
            <v-card-title>{{item.title}}</v-card-title>
            <v-card-title>
              <v-icon dark>mdi-clock-outline</v-icon>{{$moment.utc(item.start).format("LLL")}} - {{$moment.utc(item.end).format("LLL")}}
            </v-card-title>
          </v-img>
        </v-card>
      </v-col>
    </v-row>
    <v-row>
      <v-col cols="12">
        <h3 class="mt-3">Активные конференции</h3>
        <template>
          <v-progress-linear value="15" background-color="#eeeeee"></v-progress-linear>
        </template>
      </v-col>
      <v-col cols="12" v-for="(item,index) in news" :key="index">
        <v-row>
          <v-col cols="12" md="4">
            <v-img :src="$store.state.image + item.img"></v-img>
          </v-col>
          <v-col cols="12" md="8" class="pt-0">
            <v-card-title>
              {{item.title}}
            </v-card-title>
            <small class="s_title my-2 ml-3">Автор: <strong><span class="color_blue">Админ</span></strong></small>
            <v-card-subtitle>
              Начало и конец конференции<v-icon color="primary">mdi-clock-outline</v-icon>{{$moment.utc(item.start).format("LLL")}} - {{$moment.utc(item.end).format("LLL")}}
            </v-card-subtitle>
              <v-btn link :to="'/conference/' + item.alias">Читать далее</v-btn>

          </v-col>
        </v-row>
      </v-col>
      <v-col cols="12">
        <template v-if="last_page>1">
          <div class="text-center mt-4">
            <v-pagination
              v-model="current_page"
              :length="last_page"
            ></v-pagination>
          </div>
        </template>
      </v-col>



    </v-row>
  </v-container>
</section>
</template>

<script>
export default {
name: "index",
  data(){
  return{
    items:[{text: 'Главная', disabled: false, href: '/',}, {text: 'Конференции', disabled: true, href: '/',},],
  }
  },
  watch:{
    current_page(){
      this.loadPage();
    }
  },
  methods:{
    async loadPage(){
      let data = await this.$axios.$get("/conference?page=" + this.current_page);
      this.current_page = data["current_page"];
      this.last_page = data["last_page"];
      this.news = data["data"];
    }
  },
  async asyncData({$axios}){
    let data = await $axios.$get("/conference");
    let latestNews =  await $axios.$get("/present-conference");
    let news = [];
    let current_page = 1;
    let last_page = 1;
    if(data["data"].length){
      news = data["data"];
      current_page = data["current_page"];
      last_page = data["last_page"];
    }
    return {news,current_page,last_page,latestNews}


  }
}
</script>

<style scoped>

</style>

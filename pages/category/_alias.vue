<template>
  <section>
  <v-container v-if="news['count'] > 0">
    <section>

      <v-container>
        <v-row>
<!--          Трендовая последняя новость-->
          <v-col cols="12" md="6" class="p-0" v-if="news['trend']" >
            <v-card link :to="'/news/' + news['trend'].alias">
              <v-img
                :src="$store.state.image + news['trend'].img"
                class="white--text align-end"
                gradient="to bottom, rgba(0,0,0,.1), rgba(0,0,0,.5)"
                height="420px"
              >
                <v-card-title class="text-h4 text-wrap">{{news['trend'].title}}</v-card-title>
              </v-img>
            </v-card>
          </v-col>
<!--          Конец трендовой последней новости-->
<!--          Актуальная новость 1-->
          <v-col cols="12" md="6" class="p-0" v-if="news['actual'].length > 0">
            <v-card link :to="'/news/' + news['actual'][0].alias">
              <v-img
                :src="$store.state.image + news['actual'][0].img"
                class="white--text align-end"
                gradient="to bottom, rgba(0,0,0,.1), rgba(0,0,0,.5)"
                height="210px"
              >
                <v-card-title class='text-wrap'>{{news['actual'][0].title}}</v-card-title>
              </v-img>
            </v-card>
            <!--          Актуальная новость 2 шт-->
            <v-row class="p-0 m-0" v-if="news['actual'].length > 2">
              <v-col cols="12" md="6" class="p-0">
                <v-card link :to="'/news/' + news['actual'][1].alias">
                  <v-img
                    :src="$store.state.image + news['actual'][1].img"
                    class="white--text align-end"
                    gradient="to bottom, rgba(0,0,0,.1), rgba(0,0,0,.5)"
                    height="209px"
                  >
                    <v-card-title class = 'text-wrap'>{{news['actual'][1].title}}</v-card-title>
                  </v-img>
                </v-card>
              </v-col>
              <v-col cols="12" md="6" class="p-0">
                <v-card link :to="'/news/' + news['actual'][2].alias">
                  <v-img
                    :src="$store.state.image + news['actual'][2].img"
                    class="white--text align-end"
                    gradient="to bottom, rgba(0,0,0,.1), rgba(0,0,0,.5)"
                    height="209px"
                  >
                    <v-card-title class = 'text-wrap'>{{news['actual'][2].title}}</v-card-title>
                  </v-img>
                </v-card>
              </v-col>
            </v-row>
          </v-col>
        </v-row>
      </v-container>
      <!--      Конец 5 новостей-->
    </section>
<!--    Основные вести-->
    <section class="mt-3">
      <v-container>
        <v-row>
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
          <v-col cols="12" md="9" class="pl-0">
            <h1 class="mb-3">{{news["category"]}}</h1>
            <v-row v-for="(item,index) in news['news'].data" :key="index + item.title" class="mt-4">
              <v-col cols="12" md="6" >
                <v-img
                  :src="$store.state.image + item.img"
                ></v-img>
              </v-col>
              <v-col cols="12" md="6">
                <v-card-title class="pt-0">
                  {{item.title}}
                </v-card-title>
                <v-card-subtitle class="text-subtitle-1 font-weight-regular">Автор:{{item.user.name}}  <v-icon>mdi-clock-outline</v-icon>{{$moment(Date.parse(item.created_at)).format('LLL')}}</v-card-subtitle>
                <p class="text-subtitle-1 px-3 text-muted text-wrap">
                    {{item.subtitle.length > 125 ? item.subtitle.slice(0,125) + "..." :item.subtitle}}
                </p>
                <v-btn link :to="'/news/' +item.alias">Читать далее</v-btn>
              </v-col>
            </v-row>
            <template v-if="last_page>1">
              <div class="text-center mt-4">
                <v-pagination
                  v-model="current_page"
                  :length="last_page"
                ></v-pagination>
              </div>
            </template>
          </v-col>
<!--          Боковая лента-->
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

            <template v-if="news['all_trend'].length > 0">
            <h3 class="mt-3">В тренде</h3>
            <template>
              <v-progress-linear value="15" background-color="#eeeeee"></v-progress-linear>
            </template>

            <v-card color="white" light v-for="(item, index) in news['all_trend']" :key="item.title" class="mt-2" link :to="'/news/' + item.alias">
              <div class="d-flex flex-no-wrap justify-space-between">
                <v-avatar class="ma-3" size="50" tile>
                  <v-img
                    :src="$store.state.image + item.img"
                  ></v-img>
                </v-avatar>
                <div>
                  <v-card-title class="trend">
                    {{item.title}}
                  </v-card-title>
                </div>
              </div>
            </v-card>
            </template>

            <template v-if="news['all_actual'].length > 0">
            <h3 class="mt-3">Актуальное</h3>
            <template >
              <v-progress-linear value="15" background-color="#eeeeee"></v-progress-linear>
            </template>

            <v-card v-for="(item, index) in news['all_actual']" :key="item.title"
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
    </section>

  </v-container>
    <v-container v-else>
      <v-row>
        <v-col>
          <h3 class="red--text">К сожалению новостей в этой категории еще нет....</h3>
        </v-col>
      </v-row>
    </v-container>
  </section>
</template>

<script>
export default {
  async validate({$axios, route}){
      if(route.params.alias == null){
        return false;
      }
      else{
        return true;
      }
  },
  name: "category",
  data() {
    return {

      current_page:1,
      last_page:1,
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
  watch:{
    current_page(){
      this.loadPage();
    }
  },
  methods:{
   async loadPage(){
       this.news = await this.$axios.$get("/category/" + this.$route.params.alias + "?page=" + this.current_page);
       this.current_page = this.news["news"]["current_page"];
       this.last_page = this.news["news"]["last_page"];
    }
  },

  async asyncData({$axios,route}){
    const news = await $axios.$get("/category/" + route.params.alias);
    const current_page = news["news"]["current_page"];
    const last_page = news["news"]["last_page"];
    const items = [{text: 'Главная', disabled: false, href: '/',}, {text: 'Категории', disabled: true, href: '/',},];
    items.push({text: news["category"],disabled: true})
    return {news,current_page,last_page,items}
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

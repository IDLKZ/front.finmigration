<template>
<div style="background-color: #212121">
<v-container>
  <v-row class="py-5 mt-5">
    <v-col cols="12" md="4" class="py-5 text-md-left text-center">
      <h1 class="text-weight-bold white--text">FINMIGRATION</h1>
      <div class="text-body-2 text-md-left text-center white--text my-2">
        We bring you the best Premium WordPress Themes that perfect for news, magazine, personal blog, etc. Check our landing page for details.
      </div>
      <br>
      <div class="text-body-1 text-md-left text-center white--text my-2 text-uppercase my-2">
        Follow Us:
      </div>
      <div class="pt-md-2 text-center text-md-left">
        <v-btn color="transparent" class="px-2 white--text" v-for="(item,index) in social" :key="index">
          <v-icon style="margin: 0 auto!important;">{{item.icon}}</v-icon>
        </v-btn>
      </div>
    </v-col>
    <v-col cols="12" md="4" class="text-md-left text-center">
      <h3 class="text-weight-bold pl-3" style="color: #2E9FFF">Категории:</h3>
      <br>
      <v-tabs background-color="transparent" height="300" show-arrows vertical>
        <v-tab class="white--text justify-md-start justify-center" dark v-for="(link,index) in header_links" :key="index" link :to="link.url">{{link.title}}</v-tab>
      </v-tabs>
    </v-col>
    <v-col cols="12" md="4" class="text-md-left text-center">
      <h3 class="text-weight-bold pl-3" style="color: #2E9FFF">Подписывайтесь:</h3>
      <br>
      <div class="text-body-2 text-md-left text-center white--text pl-2">
        To stay on top of the ever-changing world of business, subscribe now to our newsletters.
      </div>
      <br>
      <v-text-field class="pl-2 mt-5"
        outlined
        clearable
        dense
        dark
        background-color="#424242"
        label="Ваша почта"
        type="text"
        append-icon="mdi-send"
        hint="Подписываясь, вы соглашаетсь в политикой конфиденциальности"
      ></v-text-field>
    </v-col>
  </v-row>

    <hr>

  <v-row class="my-5">
    <v-col cols="12" md="8">
      <div class="subheader white--text text-md-left text-center">
        FINMIGRATION - 2021. ALL RIGHT RESERVED
      </div>
    </v-col>
    <v-col cols="12" md="4">
      <v-tabs show-arrows background-color="transparent">
        <v-tab v-for="(link, index) in system_links" :key="index" link :to="link.url" class="system_link">{{link.title}}</v-tab>
      </v-tabs>
    </v-col>

  </v-row>

</v-container>
</div>
</template>

<script>
export default {
  name: "Footer",
  data(){
    return{
      social:[
        {url:"",icon:"mdi-facebook"},
        {url:"",icon:"mdi-twitter"},
        {url:"",icon:"mdi-instagram"},
        {url:"",icon:"mdi-pinterest"},
        {url:"",icon:"mdi-youtube"}
      ],
      header_links:[
        {url:"",title:"Главная"},
        {url:"",title:"Жизнь"},
        {url:"",title:"Бизнес"},
        {url:"",title:"Техно"},
        {url:"",title:"Конференции"},
        {url:"",title:"Предстоящие конференции"},
        {url:"",title:"Справочник"},
        {url:"",title:"Спецпроекты"},
        {url:"",title:"О нас"},
      ],
      system_links:[
        {url:"",title:"О нас"},
        {url:"",title:"Реклама"},
        {url:"",title:"Карьера"},
        {url:"",title:"Контакты"},
      ],
    }
  }
}
</script>

<style scoped>
.system_link{
  font-size: 12px!important;
  color: white!important;
}
</style>

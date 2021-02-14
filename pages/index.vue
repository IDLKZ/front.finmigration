<template>
  <div class="my-5 py-5">
    <section>
      <v-container>
        <!--      Главные вести-->
        <v-row class="my-2">
          <!--        Главная трендовая новость-->
          <v-col cols="12" md="8">
            <v-btn class="btn btn-primary mb-2" color="error"> <v-icon dark>
              mdi-new-box
            </v-icon>В тренде</v-btn>
            <v-card link to="/">
              <v-img
                height="350"
                src="https://cdn.vuetifyjs.com/images/cards/cooking.png"
                gradient="to top right, rgba(100,115,201,.33), rgba(25,32,72,.7)"
              >
                <div class="main-news px-2">
                  <v-btn depressed class="btn btn-primary mb-2" color="primary">
                    Политика
                  </v-btn>
                  <div class="text-h4 white--text font-weight-medium">President Obama Holds his Final Press Conference</div>
                  <div class="text-subtitle-1 white--text font-weight-regular">Автор:Админ  <v-icon class="white--text">mdi-clock-outline</v-icon>DECEMBER 30, 2016</div>
                </div>

              </v-img>
            </v-card>
          </v-col>
          <!--        Актуальные главные-->
          <v-col cols="12" md="4">
            <v-btn class="btn btn-primary mb-2" color="primary"> <v-icon dark>
              mdi-new-box
            </v-icon>Актуальные</v-btn>
            <v-col v-for="(item, i) in 2" :key="i" cols="12">
              <v-card color="white" light link to="/">
                <div class="d-flex flex-no-wrap justify-space-between">
                  <v-avatar class="ma-3" size="125" tile>
                    <v-img  src="https://cdn.vuetifyjs.com/images/cards/cooking.png"></v-img>
                  </v-avatar>
                  <div>
                    <v-card-title class="text-h-6">
                      President Obama Holds his Final Press Conference
                    </v-card-title>
                  </div>
                </div>
              </v-card>
            </v-col>
          </v-col>
        </v-row>
        <!--      Конец главных вестей-->
        <hr>
        <!--      Начало последних новостей-->
        <v-row class="my-2">
          <v-col cols="12" md="8">
            <h3 class="text-weight-bold pl-3" style="color: #2E9FFF">Последние новости:</h3>
            <v-row>
              <v-col cols="12" md="6">
                <v-img src="https://cdn.vuetifyjs.com/images/cards/cooking.png"></v-img>
              </v-col>
              <v-col cols="12" md="6">
                <v-card-title>
                  President Obama Holds his Final Press Conference
                </v-card-title>
                <v-card-subtitle class="text-subtitle-1 font-weight-regular">Автор:Админ  <v-icon>mdi-clock-outline</v-icon>DECEMBER 30, 2016</v-card-subtitle>
                <p class="text-subtitle-1 px-3">
                  It is a paradisematic country, in which roasted parts of sentences fly into your mouth. Even the all-powerful Pointing has...
                </p>
                <v-btn>Читать далее</v-btn>
              </v-col>
            </v-row>

            <v-row>
              <v-col cols="12" md="4" v-for="i in 3" :key="i">
                <v-card
                  link
                  to="/"
                  class="mx-auto"
                  max-width="344"
                >
                  <v-img
                    src="https://cdn.vuetifyjs.com/images/cards/sunshine.jpg"
                    height="200px"
                  ></v-img>

                  <v-card-title>
                    Top western road trips
                  </v-card-title>

                  <v-card-subtitle>
                    1,000 miles of wonder
                  </v-card-subtitle>

                  <v-card-actions>
                    <v-btn>
                      Читать далее
                    </v-btn>

                  </v-card-actions>
                </v-card>


              </v-col>
            </v-row>



          </v-col>
          <v-col cols="12" md="4">
            <h3 class="text-weight-bold pl-3" style="color: #2E9FFF">Новости в тренде:</h3>
            <v-col cols="12" md="12" >
              <v-card link to="/" class="mx-auto" max-width="344">
                <v-img src="https://cdn.vuetifyjs.com/images/cards/sunshine.jpg" height="200px"></v-img>
                <v-card-title>
                  Top western road trips
                </v-card-title>
                <v-card-subtitle>
                  1,000 miles of wonder
                </v-card-subtitle>
                <v-card-actions>
                  <v-btn>
                    Читать далее
                  </v-btn>
                </v-card-actions>
              </v-card>
            </v-col>
            <v-col v-for="(item, i) in 2" :key="i" cols="12">
              <v-card color="white" light link to="/">
                <div class="d-flex flex-no-wrap justify-space-between">
                  <v-avatar class="ma-3" size="125" tile>
                    <v-img  src="https://cdn.vuetifyjs.com/images/cards/cooking.png"></v-img>
                  </v-avatar>
                  <div>
                    <v-card-title class="text-h-6">
                      President Obama Holds his Final Press Conference
                    </v-card-title>
                  </div>
                </div>
              </v-card>
            </v-col>
          </v-col>
          <v-col cols="12" class="text-center">
            <v-btn color="primary">Все последние новости</v-btn>
          </v-col>
        </v-row>
        <!--      Конец последних новостей-->
        <hr>
        <!--Новости в категории 1-->
        <v-row class="my-2">
          <v-col cols="12" md="8">
            <h3 class="text-weight-bold pl-3" style="color: #2E9FFF">Новости категории 1:</h3>
            <v-row>
              <v-col cols="12" md="6">
                <v-card>
                  <v-img
                    src="https://cdn.vuetifyjs.com/images/cards/cooking.png"
                    class="white--text align-end"
                    gradient="to bottom, rgba(0,0,0,.1), rgba(0,0,0,.5)"
                    height="200px"
                  >
                    <v-card-title>Новости категории 1</v-card-title>
                  </v-img>
                </v-card>
                <v-card v-for="i in 2" :key="i" class="my-2" color="white" light link to="/">
                  <div class="d-flex flex-no-wrap justify-space-between">
                    <v-avatar class="ma-3" size="125" tile>
                      <v-img  src="https://cdn.vuetifyjs.com/images/cards/cooking.png"></v-img>
                    </v-avatar>
                    <div>
                      <v-card-title class="text-subtitle-1 font-weight-bold">
                        President Obama Holds his Final Press Conference
                      </v-card-title>
                    </div>
                  </div>
                </v-card>
              </v-col>
              <v-col cols="12" md="6">
                <v-card>
                  <v-img
                    src="https://cdn.vuetifyjs.com/images/cards/cooking.png"
                    class="white--text align-end"
                    gradient="to bottom, rgba(0,0,0,.1), rgba(0,0,0,.5)"
                    height="200px"
                  >
                    <v-card-title>Новости категории 1</v-card-title>
                  </v-img>
                </v-card>
                <v-card v-for="i in 2" :key="i" class="my-2" color="white" light link to="/">
                  <div class="d-flex flex-no-wrap justify-space-between">
                    <v-avatar class="ma-3" size="125" tile>
                      <v-img  src="https://cdn.vuetifyjs.com/images/cards/cooking.png"></v-img>
                    </v-avatar>
                    <div>
                      <v-card-title class="text-subtitle-1 font-weight-bold">
                        President Obama Holds his Final Press Conference
                      </v-card-title>
                    </div>
                  </div>
                </v-card>
              </v-col>
            </v-row>
          </v-col>
          <v-col cols="12" md="4">
            <h3 class="text-weight-bold pl-3" style="color: #2E9FFF">Новости в тренде:</h3>
            <v-col cols="12" md="12" v-for="i in 2 " :key="i">
              <v-card>
                <v-img
                  src="https://cdn.vuetifyjs.com/images/cards/cooking.png"
                  class="white--text align-end"
                  gradient="to bottom, rgba(0,0,0,.1), rgba(0,0,0,.5)"
                  height="200px"
                >
                  <v-card-title>Новости категории 1</v-card-title>
                </v-img>
              </v-card>
            </v-col>
          </v-col>
          <v-col cols="12" class="text-center">
            <v-btn color="primary">Все новости Категории 1</v-btn>
          </v-col>
        </v-row>
        <!--Конец в новости в категории 1-->
        <hr>
        <!--Начало новостей в категории 2-->
        <v-row class="my-2">
          <v-col cols="12" md="8">
            <h3 class="text-weight-bold pl-3" style="color: #2E9FFF">Новости категории 2:</h3>
            <v-row>
              <v-col cols="12" md="6">
                <v-card
                  link
                  to="/"
                  class="mx-auto"
                  max-width="344"
                >
                  <v-img
                    src="https://cdn.vuetifyjs.com/images/cards/sunshine.jpg"
                    height="200px"
                  ></v-img>

                  <v-card-title>
                    Top western road trips
                  </v-card-title>

                  <v-card-subtitle>
                    1,000 miles of wonder
                  </v-card-subtitle>

                  <v-card-actions>
                    <v-btn>
                      Читать далее
                    </v-btn>

                  </v-card-actions>
                </v-card>
              </v-col>
              <v-col cols="12" md="6">
                <v-card v-for="i in 3" :key="i" class="my-2" color="white" light link to="/">
                  <div class="d-flex flex-no-wrap justify-space-between">
                    <v-avatar class="ma-3" size="125" tile>
                      <v-img  src="https://cdn.vuetifyjs.com/images/cards/cooking.png"></v-img>
                    </v-avatar>
                    <div>
                      <v-card-title class="text-subtitle-1 font-weight-bold">
                        President Obama Holds his Final Press Conference
                      </v-card-title>
                    </div>
                  </div>
                </v-card>
              </v-col>
            </v-row>
          </v-col>
          <v-col cols="12" md="4">
            <h3 class="text-weight-bold pl-3" style="color: #2E9FFF">Новости в тренде:</h3>
            <v-col cols="12" md="12" v-for="i in 2 " :key="i">
              <v-card>
                <v-img
                  src="https://cdn.vuetifyjs.com/images/cards/cooking.png"
                  class="white--text align-end"
                  gradient="to bottom, rgba(0,0,0,.1), rgba(0,0,0,.5)"
                  height="200px"
                >
                  <v-card-title>Новости категории 2</v-card-title>
                </v-img>
              </v-card>
            </v-col>
          </v-col>
          <v-col cols="12" class="text-center">
            <v-btn color="primary">Все новости Категории 2</v-btn>
          </v-col>
        </v-row>
        <!--Конец в новости в категории 2-->
        <!--      Начало 5 новостей-->
      </v-container>
    </section>
    <section style="background-color: #212121">
      <v-container>
      <v-row class="py-5" >
        <v-col cols="12" md="4">
          <v-card>
            <v-img
              src="https://cdn.vuetifyjs.com/images/cards/cooking.png"
              class="white--text align-end"
              gradient="to bottom, rgba(0,0,0,.1), rgba(0,0,0,.5)"
              height="420px"
            >
              <v-card-title>Новости категории 2</v-card-title>
            </v-img>
          </v-card>
        </v-col>
        <v-col cols="12" md="4">
          <v-card class="my-2 mx-2" v-for="i in 2" :key="i">
            <v-img
              src="https://cdn.vuetifyjs.com/images/cards/cooking.png"
              class="white--text align-end"
              gradient="to bottom, rgba(0,0,0,.1), rgba(0,0,0,.5)"
              height="200px"
            >
              <v-card-title>Новости категории 2</v-card-title>
            </v-img>
          </v-card>
        </v-col>
        <v-col cols="12" md="4">
          <v-card class="my-2 mx-2" v-for="i in 2" :key="i">
            <v-img
              src="https://cdn.vuetifyjs.com/images/cards/cooking.png"
              class="white--text align-end"
              gradient="to bottom, rgba(0,0,0,.1), rgba(0,0,0,.5)"
              height="200px"
            >
              <v-card-title>Новости категории 2</v-card-title>
            </v-img>
          </v-card>
        </v-col>
      </v-row>
      </v-container>
      <!--      Конец 5 новостей-->
    </section>

    <section>
      <v-container>
        <v-row>
        <v-col cols="12" md="8">
          <h3 class="text-weight-bold pl-3" style="color: #2E9FFF">Новости в категории 3:</h3>
          <v-row>
            <v-col cols="12" md="6">
              <v-img src="https://cdn.vuetifyjs.com/images/cards/cooking.png"></v-img>
            </v-col>
            <v-col cols="12" md="6">
              <v-card-title>
                President Obama Holds his Final Press Conference
              </v-card-title>
              <v-card-subtitle class="text-subtitle-1 font-weight-regular">Автор:Админ  <v-icon>mdi-clock-outline</v-icon>DECEMBER 30, 2016</v-card-subtitle>
              <p class="text-subtitle-1 px-3">
                It is a paradisematic country, in which roasted parts of sentences fly into your mouth. Even the all-powerful Pointing has...
              </p>
              <v-btn>Читать далее</v-btn>
            </v-col>
            <v-col cols="12" md="6" v-for="i in 2" :key="i">
              <v-card v-for="i in 2" :key="i" class="my-2" color="white" light link to="/">
                <div class="d-flex flex-no-wrap justify-space-between">
                  <v-avatar class="ma-3" size="125" tile>
                    <v-img  src="https://cdn.vuetifyjs.com/images/cards/cooking.png"></v-img>
                  </v-avatar>
                  <div>
                    <v-card-title class="text-subtitle-1 font-weight-bold">
                      President Obama Holds his Final Press Conference
                    </v-card-title>
                  </div>
                </div>
              </v-card>
            </v-col>
          </v-row>
        </v-col>
        <v-col cols="12" md="4">
            <h3 class="text-weight-bold pl-3" style="color: #2E9FFF">Новости в тренде:</h3>
            <v-col cols="12" md="12" v-for="i in 2" :key="i">
              <v-card link to="/" class="mx-auto" max-width="344">
                <v-img src="https://cdn.vuetifyjs.com/images/cards/sunshine.jpg" height="200px"></v-img>
                <v-card-title>
                  Top western road trips
                </v-card-title>
                <v-card-subtitle>
                  1,000 miles of wonder
                </v-card-subtitle>
                <v-card-actions>
                  <v-btn>
                    Читать далее
                  </v-btn>
                </v-card-actions>
              </v-card>
            </v-col>
          </v-col>
          <v-col cols="12" class="text-center">
            <v-btn color="primary">Все новости Категории 3</v-btn>
          </v-col>
        </v-row>
      </v-container>
    </section>

    <section style="background-color: #F5F5F5">
      <v-container>
        <v-row>
          <v-col cols="12">
            <svg width="100%" height="120" viewBox="0 0 970 90" fill="none" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink">
              <rect width="970" height="90" fill="url(#pattern0)"/>
              <defs>
                <pattern id="pattern0" patternContentUnits="objectBoundingBox" width="1" height="1">
                  <use xlink:href="#image0" transform="scale(0.00103093 0.0111111)"/>
                </pattern>
                <image id="image0" width="970" height="90" xlink:href="data:image/png;base64,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"/>
              </defs>
            </svg>

          </v-col>
        </v-row>
      </v-container>
    </section>

    <section>
      <v-container>
        <v-row>
          <v-col cols="12" md="8">
            <h3 class="text-weight-bold pl-3" style="color: #2E9FFF">Конференции</h3>
            <v-row v-for="i in 5" :key="i">
              <v-col cols="12" md="6">
                <v-img src="https://cdn.vuetifyjs.com/images/cards/cooking.png"></v-img>
              </v-col>
              <v-col cols="12" md="6">
                <v-card-title>
                  President Obama Holds his Final Press Conference
                </v-card-title>
                <v-card-subtitle class="text-subtitle-1 font-weight-regular">Автор:Админ  <v-icon>mdi-clock-outline</v-icon>DECEMBER 30, 2016</v-card-subtitle>
                <p class="text-subtitle-1 px-3">
                  It is a paradisematic country, in which roasted parts of sentences fly into your mouth. Even the all-powerful Pointing has...
                </p>
                <v-btn>Читать далее</v-btn>
              </v-col>
            </v-row>
          </v-col>
          <v-col cols="12" md="4">
            <h3 class="text-weight-bold pl-3" style="color: #2E9FFF">Мы в соц сетях:</h3>
            <div class="pt-md-2 text-center text-md-left">
              <v-btn color="error" class="px-2 white--text" v-for="(item,index) in social" :key="index">
                <v-icon style="margin: 0 auto!important;">{{item.icon}}</v-icon>
              </v-btn>
            </div>
            <v-col v-for="(item, i) in 3" :key="i" cols="12">
              <v-card color="white" light link to="/">
                <div class="d-flex flex-no-wrap justify-space-between">
                  <v-avatar class="ma-3" size="125" tile>
                    <v-img  src="https://cdn.vuetifyjs.com/images/cards/cooking.png"></v-img>
                  </v-avatar>
                  <div>
                    <v-card-title class="text-h-6">
                      President Obama Holds his Final Press Conference
                    </v-card-title>
                  </div>
                </div>
              </v-card>
            </v-col>
            <v-col cols="12">
                <v-sheet height="340px" color="yellow">Ads</v-sheet>
            </v-col>
            <v-col cols="12" md="12" v-for="i in 2 " :key="i">
              <v-card>
                <v-img
                  src="https://cdn.vuetifyjs.com/images/cards/cooking.png"
                  class="white--text align-end"
                  gradient="to bottom, rgba(0,0,0,.1), rgba(0,0,0,.5)"
                  height="200px"
                >
                  <v-card-title>Новости категории 1</v-card-title>
                </v-img>
              </v-card>
            </v-col>
          </v-col>
        </v-row>
      </v-container>


    </section>



  </div>

</template>

<script>
import Logo from '~/components/Logo.vue'
import VuetifyLogo from '~/components/VuetifyLogo.vue'

export default {
  components: {
    Logo,
    VuetifyLogo,
  },
  data(){
    return{
      social:[
        {url:"",icon:"mdi-facebook"},
        {url:"",icon:"mdi-twitter"},
        {url:"",icon:"mdi-instagram"},
        {url:"",icon:"mdi-pinterest"},
        {url:"",icon:"mdi-youtube"}
      ],
    }
  }
}
</script>
<style scoped>
.main-news{
  position: absolute;
  bottom: 20px;
}

</style>

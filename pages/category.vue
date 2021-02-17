<template>
  <v-container>
    <section>
      <v-container>
        <v-row>
          <v-col cols="12" md="6" class="p-0">
            <v-card>
              <v-img
                src="https://i.ytimg.com/vi/Z4qMFy2BzNo/maxresdefault.jpg"
                class="white--text align-end"
                gradient="to bottom, rgba(0,0,0,.1), rgba(0,0,0,.5)"
                height="420px"
              >
                <v-card-title>Новости категории 2</v-card-title>
              </v-img>
            </v-card>
          </v-col>
          <v-col cols="12" md="6" class="p-0">
            <v-card>
              <v-img
                src="https://i.ytimg.com/vi/Z4qMFy2BzNo/maxresdefault.jpg"
                class="white--text align-end"
                gradient="to bottom, rgba(0,0,0,.1), rgba(0,0,0,.5)"
                height="210px"
              >
                <v-card-title>Новости категории 2</v-card-title>
              </v-img>
            </v-card>
            <v-row class="p-0 m-0">
              <v-col cols="12" md="6" class="p-0">
                <v-card>
                  <v-img
                    src="https://i.ytimg.com/vi/Z4qMFy2BzNo/maxresdefault.jpg"
                    class="white--text align-end"
                    gradient="to bottom, rgba(0,0,0,.1), rgba(0,0,0,.5)"
                    height="209px"
                  >
                    <v-card-title>Новости категории 2</v-card-title>
                  </v-img>
                </v-card>
              </v-col>
              <v-col cols="12" md="6" class="p-0">
                <v-card>
                  <v-img
                    src="https://i.ytimg.com/vi/Z4qMFy2BzNo/maxresdefault.jpg"
                    class="white--text align-end"
                    gradient="to bottom, rgba(0,0,0,.1), rgba(0,0,0,.5)"
                    height="209px"
                  >
                    <v-card-title>Новости категории 2</v-card-title>
                  </v-img>
                </v-card>
              </v-col>
            </v-row>
          </v-col>
        </v-row>
      </v-container>
      <!--      Конец 5 новостей-->
    </section>

    <section class="mt-3">
      <v-container>
        <v-row>
          <v-col cols="12" md="9" class="pl-0">
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
            <h1 class="mb-3">Бизнес</h1>
            <span class="text-muted">A wonderful serenity has taken possession of my entire soul, like these sweet mornings of spring which I enjoy with my whole heart.</span>
            <v-row v-for="i in 5" :key="i" class="mt-4">
              <v-col cols="12" md="6">
                <v-img src="https://yandex-images.naydex.net/Q5ksr1214/47185b9X6/lVX4yJPuFKmG-3n-_eJ2I_4-z_xi9C2RWswUvBlOm9H4Q6mmBz7GtBl6eC-RUOZF9aHgRL5HSaGsguKNqwq075Rw5bW_s0Gxi_N1uk2OWie6Rr_xPu18rHu9QaU9S8OM3U78w54StrUgDy2ztUTuOUkJbD1io-FtHX8DcKpvzbrRdI2Nxi7t8c5vNZrY3lpvP27LEIIkUdTGoBi5NW4bTMQXJT5__u4RNI-F1kzdA2EB4dht5js5Zd2zL6DuZ1GKBc0FvRa6dM3q_81erMrWV1syT1gOqJWYaqSQxTHGw9isN4ECczriPRD7fVa0Eeu1ETVk5WaPSa2JW48M0le1ko1RhT32dnA9FudN7hhWDm8LGmtwZrDx6EIsuPUdwt8QSMupDtty0pF4561aoGkPvYXtMKEyP1WZ-cfzHOozqY5JuRWpxooEtQ7zqSZ4Fg7XP9azNMoAvVwmnKhpTYaTLNybgY7b4nJ1MKNxQkhZm6kdefzd1kvVCbG_m1SaA1EeQSUtpb5mWFHmkyGy0FZ677smJ5jm6J3YuqDkjQWGWwzo-5min6puEfQjCS741TvN1a0oifIHha0BO0fsCrcl8hW9aWW-algp4k9JbrR6xgMLxqfQYmxRVNbQ2DXhMlfQqG9xQlOWyg1EFzXK9JV33Qk1eK3m5-EFXdt_8GLn0TpdvZWxdnawfdLrsXJkgpqf72KfYEa4kTSieCQpYZJT6PhvkbYrcjqRMA91rmjlz8kJsTAp9nuZaV13z1zaD6Em1VWhFfLq-C3aG7W-EFJ-p-9aw-zqAH24gqSEzWnWX1AcT93K6zrWffyPEV6g3YvZga14japT9R1toxvkjrORQpm1jQXmgpitumchhtSanoNjFmt8dvi1MNZ8iA1x_kMM4L91liuGyl2EI2kmpFULxemRqBk2D_Wx_UMLEMpTOUpxNdUZGtaIoUIPbep8CgYn4wIXTPpIlXQGICgpNQYI"></v-img>
              </v-col>
              <v-col cols="12" md="6">
                <v-card-title class="pt-0">
                  President Obama Holds his Final Press Conference
                </v-card-title>
                <v-card-subtitle class="text-subtitle-1 font-weight-regular">Автор:Админ  <v-icon>mdi-clock-outline</v-icon>DECEMBER 30, 2016</v-card-subtitle>
                <p class="text-subtitle-1 px-3 text-muted">
                  It is a paradisematic country, in which roasted parts of sentences fly into your mouth. Even the all-powerful Pointing has...
                </p>
                <v-btn>Читать далее</v-btn>
              </v-col>
            </v-row>
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

            <h3 class="mt-3">В тренде</h3>
            <template>
              <v-progress-linear value="15" background-color="#eeeeee"></v-progress-linear>
            </template>

            <v-card color="white" light link to="/" v-for="(item, i) in 3" :key="i" class="mt-2">
              <div class="d-flex flex-no-wrap justify-space-between">
                <v-avatar class="ma-3" size="50" tile>
                  <v-img  src="https://cdn.vuetifyjs.com/images/cards/cooking.png"></v-img>
                </v-avatar>
                <div>
                  <v-card-title class="trend">
                    President Obama Holds his Final Press Conference
                  </v-card-title>
                </div>
              </div>
            </v-card>

            <h3 class="mt-3">Интересно</h3>
            <template>
              <v-progress-linear value="15" background-color="#eeeeee"></v-progress-linear>
            </template>

            <v-card v-for="(item, i) in 3" :key="i"
              class="mx-auto mt-3"
              max-width="400"
            >
              <v-img
                class="white--text align-end"
                height="160px"
                src="https://images.pexels.com/photos/6166288/pexels-photo-6166288.jpeg?auto=compress&cs=tinysrgb&dpr=1&w=500"
              >
              </v-img>

              <v-card-text class="text--primary">
                <div><strong>Choosing The Best Audio Player Software For Your Computer</strong></div>
              </v-card-text>

              <v-card-actions class="pl-4">
                <div class="text-muted">DECEMBER 30, 2020</div>
              </v-card-actions>
            </v-card>
          </v-col>
        </v-row>
        <template>
          <div class="text-center mt-4">
            <v-pagination
              v-model="page"
              :length="6"
            ></v-pagination>
          </div>
        </template>
      </v-container>
    </section>

  </v-container>
</template>

<script>
    export default {

        name: "category",
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

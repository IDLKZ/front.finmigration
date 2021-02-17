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

        <h1 class="mt-3">Евросоюз до Нового года начнет массовую вакцинацию от COVID-19</h1>
        <p class="text-muted">Kindness And Motivation Tips Challenge Groups To Make A Difference.</p>
      </v-col>
      <v-col cols="12" md="3">

      </v-col>
    </v-row>
  </v-container>
</template>

<script>
    export default {
        name: "article",
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

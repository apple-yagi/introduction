<template>
  <v-card style="background-color: #424242;">
    <v-row>
      <v-col align="center" cols="12" sm="8">
        <v-card-subtitle class="title">Other</v-card-subtitle>
        <v-card-text>
          <span class="mx-10" v-for="(item, i) in items" :key="i">
            <div class="my-3" style="display: inline-block;">
              <img :src="img(item)" width="30" alt="item-img" style="vertical-align: middle;" />
              <span class="item-name ml-2" style="vertical-align: middle;">{{ item }}</span>
            </div>
          </span>
        </v-card-text>
      </v-col>

      <v-col align="center" cols="12" sm="4">
        <v-img class="db" src="img/database.png" alt="database" width="100" />
      </v-col>
    </v-row>
  </v-card>
</template>

<script lang="ts">
import Vue from 'vue'
const img_url = 'https://cdn.svgporn.com/logos/'

export default Vue.extend({
  data: () => ({
    items: ['Google Cloud Platform', 'Firebase', 'Heroku', 'CircleCI', 'GitHub']
  }),

  computed: {
    img: function() {
      return function(item: String) {
        item =
          item == 'Google Cloud Platform'
            ? 'google-cloud-platform'
            : item.toLowerCase().replace('.', '')
        return img_url + item + '.svg'
      }
    }
  }
})
</script>

<style scoped>
.item-name {
  font-size: 16px;
  color: #b0bec5;
}

@media screen and (min-width: 630px) {
  .item-name {
    font-size: 20px;
  }
}

@media screen and (min-width: 600px) {
  .db {
    margin-top: 75px;
  }
}

@media screen and (min-width: 1264px) {
  .db {
    margin-top: 50px;
  }
}
</style>